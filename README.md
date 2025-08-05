# Información de la Configuración del Vehículo
## Olimpiadas Mundiales de Robotica 2025 ( WRO 2025 )
### CATEGORIA : FUTUROS INGENIEROS *****

====
## RETO DEL VEHÍCULO AUTÓNOMO.
#### EQUIPO : TEAM JIREH I
### INTEGRANTES 
1.- CHRISTOPHER J TUÑON CABRERA    LIDER/PROGRAMADOR

2.- JOHAN ARANDA G SANCHEZ         SOPORTE

3.- KEVIN EDGARDO SMITH            SOPORTE

## UBICACIÓN DEL REPOSITORIO **  : **https://github.com/ACJIREH/TEAM-JIREH-2025**
## ENLACE DEL VIDEO DE YOUTUBE ** https://youtu.be/WBnumYfBWfk

Este repositorio tiene toda la información necesaria para la configuración y conducción del vehículo autónomo para participar en la competencia de las Olimpiadas Mundiales de Robotica del año 2025 (WRO 2025.)

# RESUMEN DEL PROYECTO
El proyecto consiste en el desarrollo de un robot que navegue de forma autónoma, alrrededor de una pista cuadrada de 300 cm por lado y en cuyo centro tambien hay un cuadrado de 100 cm de madera negra. El vehículo se desplazará por toda esta pista, en ella se encontrará objetos de color rojo y verde para se convertiran en obstáculos que el vehíulo deberá esquivar por la izquiera o derecha, segun sea el color. Para finalizar el recorrido deberá dar tres vueltas en las pistas sin chocar con las paredes o con objetos de colores ubicados dentro de la pista. 

El desplazamiento es controlado por tres sensores: dos laterales y uno frontal. Estos sensores son los que realizarán las lecturas de las distancias laterales y frontales, segun las cuales deberá tomar la desicicón de esquivarlo o mantnerse en ruta. Para la detección de los colores se colocará un camará huskylens a través de la cual usando el reconocimkiento de colores permitirá diferencia los cubos de colores y poder descidir hacia donde dirirgirse.



•	`t-photos` contiene 2 fotos del equipo (una oficial y una divertida con todos sus miembros).
•	`v-photos` contiene 6 fotos del vehículo (de cada lado, desde arriba y desde abajo).
•	`video` contiene el archivo video.md con el enlace a un vídeo de demostración de conducción.
•	`schemes` contiene uno o varios diagramas esquemáticos en formato JPEG de los componentes electromecánicos, que ilustran todos los elementos (componentes electrónicos y motores) utilizados en el vehículo y cómo se conectan entre sí.
•	`src` contiene el código del software de control de todos los componentes programados para participar en la competición.
•	`models` contiene los archivos de los modelos utilizados por impresoras 3D para producir los elementos del vehículo. Si no hay nada que añadir a esta ubicación, se puede eliminar el directorio.
•	`other` contiene otros archivos que pueden utilizarse para comprender cómo preparar el vehículo para la competición. Puede incluir documentación sobre cómo conectarse a un SBC/SBM y cargar archivos allí, conjuntos de datos, especificaciones de hardware, descripciones de protocolos de comunicación, etc. Si no hay nada que agregar a esta ubicación, se puede eliminar el directorio


## Introduction

_This part must be filled by participants with the technical clarifications about the code: which modules the code consists of, how they are related to the electromechanical components of the vehicle, and what is the process to build/compile/upload the code to the vehicle’s controllers._

## How to prepare the repo based on the template

_Remove this section before the first commit to the repository_

1. Clone this repo by using the `git clone` functionality.
2. Remove `.git` directory
3. [Initialize a new public repository on GitHub](https://github.com/new) by following instructions from "create a new repository on the command line" section (appeared after pressing "Create repository" button).
