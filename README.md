# Proyecto de Electrónica Digital I
# Proyecto

Como proyecto final y dando cumplimiento con los requisitos planteados en el transcurso de la asignatura se plantearon los siguientes puntos: El sistema debe estar constituido de dos señales de entrada y dos de saliida diferentes. Para el procesamiento de las señales de entrada, se debe implementar las instrucciones en lenguaje Verilog con el fin de ingresar esta descripción de hardware a una tarjeta FPGA (Para nuestro proyecto una Altera Cyclone IV) y esta a su vez se encargue enviar las señales de control a los componentes del sistema para que ejecuten los procesos establecidos de manera articulada.

## Planteamiento del problema: 
Se decidió resolver un problema de automatización en una planta de llenado y almacenamiento de empaques; donde la dispensación de producto para llenado de envases y desplazamiento al lugar de almacenamiento se realiza de manera manual. 
## Descripción del Proyecto
El objetivo de este proyecto es implementar un sistema de automatización en una planta de llenado y almacenamiento de empaques. Por lo tanto se prpopne implementar una banda transportadora con dispensación y llenado automático por conteo determinado, con señalización de etapa de progreso y censado con la presencia de un depósito listo para ser llenado.   Para ello, se propone diseñar y desarrollar un modelo en lenguaje Verilog que cumpla con los siguientes requisitos:
### Requisitos del Modelo
  - Entradas:

    - Entrada 1 : Señal que indica la presencia de un empaque en la banda transportadora. Esta señal será recibida por medio de un modulo infra-rojo que enviará una señal de alto o bajo según sea el caso de la presencia de un depósito. 
    - Entrada 2 : Señal que indica la cantidad de producto a ser dispensado en el depósito. Esta cantidad deberá ser proporcionada por el usuario por medio de un teclado matricial. 
  - Salidas:

    - Salida 1 : Señal que controla el mecanismo de dispensación para llenar el empaque. Se envía una señal a un motor paso a paso sincronizado para tener un máximo de 9 pasos por ciclo. 
    - Salida 2 : Señal que señaliza la etapa de progreso del proceso de llenado. Esta señalización se realizará por medio de 3 LED's que indicarán que el proceso está en la etapa de llenado, de transporte o ha llegado al final. 
    - Salida 3 : Señal que controla el mecanismo de movimiento de la banda transportadora. El movimiento de la banda se controla a través de un motor que ayuda a la rotación de los rodillos de la banda y así transportar los depósitos. 
### Funcionamiento del modelo: 
  - Detección de empaque:
    - Cuando se detecta un empaque en la banda (Entrada 1), el sistema activa el proceso de llenado.
  - Especificación de cantidad:
    - El sistema solo inicia el proceso de llenado cuando hay un depósito listo para ser llenado y se ha especificado la cantidad de producto con la que se desea llenar el depósito (Entrada 2).
  - Dispensación Automática:
    - La salida 1 controla el mecanismo de dispensación, permitiendo el llenado automático hasta llegar al conteo determinado.
  - Señalización de Progreso:
    - La salida 2 señaliza las diferentes etapas del proceso de llenado, indicando el progreso del sistema.
  - Transporte de depósitos:
    - El sistema activa el movimiento de la banda transportadora cuando se ha cumplido el ciclo de llenado, enviando los contenedores a la zona de almacenado idealmente.

## Periféricos utilizados: 
  - Entrada1: Módulo de Proximidad Infrarrojo Evasor de Obstáculos FC-51.
    ![Infrarojo](images/)
  - Entrada 2: Teclado matricial de membrana 4x4.
    ![Teclado](images/)
  - Salida 1: Motor Paso a Paso 28BYJ-48 + Módulo Driver Controlador
    ![PasoaPaso](images/)
  - Salida 2: Diodos LED Rojo, Amarillo, Verde
    ![Led](images/)
  - Salida 3: Motor DC 
