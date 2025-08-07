# Esquema de Conexión 

## Configuración General 

El vehículo autónomo utiliza un Arduino UNO como cerebro principal que coordina todos los componentes mediante una red de conexiones específicas. 

## 1.	Componentes Principales Sensores Ultrasónicos (3 unidades) 
     ** Función:**  
	Detectar obstáculos y mantener distancia de las paredes 
      	Conexión: Cada sensor usa 2 pines (Trigger y Echo) conectados a pines digitales diferentes del Arduino 

      Ubicación: Uno frontal, uno lateral izquierdo, uno lateral derecho 

## 2.	Cámara HuskyLens 

      Función: Reconocer cubos rojos y verdes para estrategias de evitación 

      Conexión: Comunicación serial (RX/TX) a través de los pines 11 y 12 

      Alimentación: 5V directos del Arduino 

## 3.	Sistema de Movimiento 

      Motor DC: Propulsión principal del vehículo

      Servomotor: Control de dirección (giros izquierda/derecha) 

      Conexión: Motor controlado por pines 9, 10 y 6; servo por pin A5 

      Distribución de Energía 5V: Todos los sensores, cámara y servo se alimentan del Arduino 

      Voltaje externo: Motor DC requiere fuente separada (6-12V) por su alto consumo

## 4.	 Flujo de Información 

      Entrada: Sensores y cámara envían datos al Arduino 

      Procesamiento: Arduino ejecuta algoritmos de navegación 

      Salida: Arduino controla motores y servo para mover el vehículo 

## 5.	Ventajas del Diseño 

      Modular: Cada componente tiene conexiones independientes Escalable: Fácil de expandir con más sensores 

      Seguro: Separación de voltajes para proteger componentes sensibles 

      Este esquema permite al vehículo navegar autónomamente, evitar obstáculos físicos y esquivar cubos de color según la estrategia programada.
