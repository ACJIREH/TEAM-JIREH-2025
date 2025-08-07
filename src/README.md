Software de control
====

Este directorio contiene el código del software de control utilizado por el vehículo para participar en la competencia, desarrollado por los participantes.

Todos los archivos necesarios para resolver dependencias y compilar el proyecto también deben incluirse en este directorio..

#include <Ultrasonic.h>

#include <Servo.h>

//sensor de distancia//


Ultrasonic Der(9,10); //sensor Derecha//

Ultrasonic Izq(12,13); //sensor Izquierdo//

Ultrasonic Cen(4,6);//sensor Frontal//

//Direcciones//


int Centro = 118;

int Izquierda  = Centro - 9; //alineamiento Derecho//

int Derecha = Centro + 8; //alineamiento Izquierdo//

int EsquinaIzq = Centro - 45;

int EsquinaDer = Centro + 45;


int LogDerecha;

int LogIzquierda;

int LogFrontal;

//definir cosas variadas//

int DSegura = 35;

int TiempoAli = 80;

int TiempoEsqI = 745;//735

int TiempoEsqD = 710;//710

int velocrecta = 185;

int DEsquina = 125;

//Motor DC//

int in1 = 7;

int in2 = 8;

int ena = 5;

//Definir Servmotor//

Servo Direc;

//definir Vueltas//

int vueltas = 0;


void setup() {

  // put your setup code here, to run once:
  
  Serial.begin(9600);
  
  //Motor DC//
  
  pinMode(in1, OUTPUT);
  
  pinMode(in2, OUTPUT);
  
  pinMode(ena, OUTPUT);
  
  //Velocidad//
  
  analogWrite(ena, velocrecta);
  
  //Servo//
  
  Direc.attach(2);
  
  Direc.write(Centro);
  
  delay(1500);
  vueltas = 0;

//Iniciador//

  digitalWrite(in1,HIGH);
  
  digitalWrite(in2,LOW);
  
}

void mostrar()
{
    Serial.print("Distancia Izq: ");
    
    Serial.println(LogIzquierda);
    
    //sensor derecho//
    
    Serial.print("Distancia Der: ");
    
    Serial.println(LogDerecha);
    
    //sensor Frontal//
    
    Serial.print("Distancia Frontal: ");
    
    Serial.println(LogFrontal);
}
void loop() {

  // put your main code here, to run repeatedly:

//sensor izquierdo//

  LogIzquierda = Izq.read();
  
  LogDerecha = Der.read();
  
  LogFrontal = Cen.read();
  
  mostrar();
  
  digitalWrite(in1,HIGH);
  
  digitalWrite(in2,LOW);
  
  analogWrite(ena, velocrecta);

//alinear//

if(LogDerecha <= DSegura && LogIzquierda >= DSegura){  //Alineamiento Derecho//

    Direc.write(Izquierda);
    
    delay(TiempoAli);
    
    Direc.write(Centro);
    
  } else if(LogIzquierda <= DSegura && LogDerecha >= DSegura){  //Alineamiento Izquierdo//
  
      Direc.write(Derecha);
      
      delay(TiempoAli);
      
      Direc.write(Centro);
      
    }else{
    
      Direc.write(Centro);
      
    }
  


//Esquinas//

if(LogFrontal <= DEsquina && LogIzquierda >= 125 && LogDerecha < 125){  //Esquina Izquierda//

      Direc.write(EsquinaIzq);
      
      delay(TiempoEsqI);
      
      Direc.write(Centro);
      
      analogWrite(ena, velocrecta);
      
      vueltas = vueltas+1;
      
}
else if(LogFrontal <= DEsquina && LogDerecha >= 125 && LogIzquierda < 125){  //Esquina Derecha//

    Direc.write(EsquinaDer);
    
    delay(TiempoEsqD);
    
      Direc.write(Centro);
      
      analogWrite(ena, velocrecta);
      
      vueltas = vueltas+1;
      
}else{

     Direc.write(Centro);
         
}


if(vueltas >= 12){

  digitalWrite(in1,LOW);
  
  digitalWrite(in2,LOW);
  
  delay(8000);
  
}


}

