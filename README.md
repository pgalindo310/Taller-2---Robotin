# Proyecto final Robotin-Baboni-Chueco 🤖

Este repositorio presenta la implementación de un robot diferencial.

## Introducción
### Primeros pasos
1. Instalar rosserial y la librería ros_lib en Arduino, siguiendo el siguiente tutorial: [ROSSERIAL](http://wiki.ros.org/rosserial_arduino/Tutorials/Arduino%20IDE%20Setup).
2. Correr: `roscore`
3. Correr: `rosrun rosserial_python serial_node.py /dev/ttyACM0` para establecer la conexión con el Arduino.
4. Ir al workspace: `cd robot_ws && source devel/setup.bash`

NOTA: Todos los nodos se encuentran en el paquete robotin_pkg

## INFORMACIÓN GENERAL DEL ROBOT
# Lista de materiales

* Puente H: [Ver producto](https://naylampmechatronics.com/drivers/11-driver-puente-h-l298n.html)
* Raspberry Pi 4: [Ver producto](https://static.raspberrypi.org/files/product-briefs/Raspberry-Pi-4-Product-Brief.pdf)
* Arduino Uno: [Ver producto](https://www.farnell.com/datasheets/1682209.pdf)
* Regulador de voltaje: [Ver producto](https://www.ti.com/lit/gpn/lm2596)

## Punto 1  ⌨️ OPERAR EL TURTLEBOT 🐢️ MEDIANTE EL TECLADO ⌨️ 
* Cargar el archivo `teleop_arduino` al Arduino.
* Correr `rosrun rosserial_python serial_node.py /dev/ttyACM0`.
* Correr `rosrun robotin_pkg turtebot_teleop.py`.
* Al momento de ejecutarlo, se solicitará si desea guardar el archivo con las trayectorias. Si selecciona "Y", se le pedirá un nombre para el archivo, el cual se guardará en la carpeta "talleres_ws/src/turtle_bot_10/results/". Si selecciona "N", no se guardarán las trayectorias. En ambos casos se solicitará la velocidad lineal y angular para TurtleBot.

## Punto 2  📈️ GRAFICAR LA TRAYECTORIA QUE RECORRE TURTLEBOT 🐢️ 📈️ 

1. Ejecutar "⌨️ OPERAR EL TURTLEBOT 🐢️ MEDIANTE EL TECLADO ⌨️" (El usuario decide si quiere guardar el recorrido o no).
2. Abrir un nuevo terminal y entrar a la carpeta "robot_ws" con el comando: `cd robot_ws/`
3. Realizar un `setup.bash` con el siguiente comando: `source devel/setup.bash`
4. Ejecutar el archivo `.py` "turtle_bot_interface" con el siguiente comando: `rosrun robotin_pkg turtle_bot_interface.py`

Se desplegará una interfaz que contendrá una gráfica y un botón. La gráfica se actualizará en tiempo real a medida que el usuario mueva al TurtleBot en el mapa. Si el usuario desea guardar dicha gráfica, debe hacer clic en el botón "GUARDAR", el cual le solicitará la carpeta donde deseará guardar la gráfica. Esta se guardará en formato `.png`.

## Punto 4  🚶️ REPLICAR UNA TRAYECTORIA YA DEFINIDA CON TURTLEBOT 🐢️ 🚶️ 

*NO SE DEBE EJECUTAR PREVIAMENTE "⌨️ OPERAR EL TURTLEBOT 🐢️ MEDIANTE EL TECLADO ⌨️" YA QUE PUEDE ALTERAR LA TRAYECTORIA DEFINIDA DEL TURTLEBOT.

1. Abrir un nuevo terminal y entrar a la carpeta "robot_ws" con el comando: `cd robot_ws/`
2. Realizar un `setup.bash` con el siguiente comando: `source devel/setup.bash`
3. Ejecutar el archivo `.py` "turtle_bot_interface" con el siguiente comando: `rosrun robotin_pkg turtle_bot_player.py`

Se solicitará el nombre del archivo de texto `.txt` donde se contienen las velocidades y la trayectoria. El archivo `.txt` será buscado en la carpeta "robot_ws/src/robotin_pkg/results/", por lo que previamente deberá estar ubicado en ese directorio. Una vez que el usuario escriba el nombre del archivo de texto (SIN `.txt`), Turtlebot replicará el recorrido allí contenido.
