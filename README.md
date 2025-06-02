# Avalon dragones, hechiceras, hadas y la Dama del Lago

Proyecto enfocado en utilizar los Hilos y Mecanismos de Sincronización de Java. Se realizará una vez con Semáforos y después se usarán únicamente Monitores.

La legendaria isla de Avalon es un lugar magico donde habitan diversos seres fantásticos. Pese a las leyendas, la isla no es un lugar idílico, sino un lugar lleno de peligros y misterios.

Es de todos sabido que la isla de Avalon es la guarida de varios dragones
(un total de totalDragons dragones), concretamente: Drogon, Fujur, Saphira,
Desdentao, Temerario, Rhaegal y Viserion entre otros. Sin embargo, no todos
los dragones pueden estar en la isla al mismo tiempo, pues cada dragon añade su magia a la de la isla y esta tiene un límite. Para evitar que la isla colapse, se ha establecido que el número máximo de dragones, de maxDragonsInIsland
dragones. Si el número de dragones en la isla supera este límite, la isla se hundiría
en el río de la vida y todos sus habitantes perecerían.
Pese a los peligros que entraña una visita a esta isla, hay una hermandad de hechiceras que tiene como rito de iniciacion que sus novicias vayan a Avalon y vuelvan con una escama de dragon. Se dice que las escamas de dragón son un poderoso talisman que protege a la futura hechicera de los peligros inherentes al uso de la magia, pero deberan pedir la escama de dragón a la Dama del Lago, Nimue, que es la guardiana de la isla. El número de novicias que deben pasar este rito es totalNovices.
Para la magia de la isla, la presencia de hechiceras es un peligro, incluso mayor
que la de los dragones. Así pues, Avalon solo permite la presencia de un número limitado de hechiceras en la isla, maxHechicerasIsla hechiceras. Pero este
numero varía en funcion de los dragones presentes en la isla:
• Si un solo dragon se encuentra dentro de la isla, no hay problema. El máximo permitido no cambia.
• Si hay dos dragones en la isla, solo se permite la presencia de la mitad de maxHechicerasIsla hechiceras.
• Si hay tres o mas dragones en la isla, sólo se permite la presencia de un cuarto de maxHechicerasIsla hechiceras.

Como redunda en beneficio de todos que la magia de la isla no colapse, los
dragones y las hechiceras han llegado a un acuerdo: antes de entrar en la isla,
los dragones expresaran su deseo de entrar en la isla, y una vez el número de hechiceras en la isla sea el nuevo maximo permitido (las hechiceras no pueden seguir entrando si ya se ha alcanzado el nuevo maximo),
los dragones entrarán de facto en la misma.
El numero de escamas necesarias para terminar la ejecución del programa debe ser igual o superior al numero de hechiceras y que ese número sea múltiplo de 6 para que las Reinas de las Hadas puedan recogerlas. Forma parte del diseño
de tu programa calcular cuantas escamas debe perder cada dragón (o lo que es lo mismo: cuantas veces entra en la isla). Indica en tu informe cómo has realizado este calculo.
Así, cada dragon repite las siguientes acciones tantas veces como se le haya indicado:
1. Vuela durante un tiempo aleatorio (menor de 1 segundo).
2. Expresa su deseo de entrar en la isla.
3. Una vez el numero de hechiceras en la isla es el m ´ aximo permitido por el ´
numero de dragones que habr ´ ´ıa realmente en la isla de entrar este dragc¸on,
entra en la isla.
4. Esta descansando un tiempo aleatorio (menor de 200 ms). ´
5. Deja una de sus escamas en el lago (si tiene sitio, si no, debe esperar a poder
dejarla).
6. Se queda en la isla un tiempo aleatorio (menor de 200ms).
7. Vuelve al paso 1.
El lago del centro de la isla es el hogar de la Dama del Lago y de las tres
Reinas de las Hadas, Titania, Morgana y Mab. Son las reinas de las hadas las encargadas de recoger las escamas de los dragones, ya que el lago tiene una capacidad limitada de escamas de dragon, ´ maxEscamasLago escamas. Cada Reina
de las Hadas va recogiendo las escamas de los dragones y una vez ha recogido
dos escamas, espera a las otras reinas para que todas juntas puedan entregar las
escamas recogidas a Nimue. Para simplificarlo, se asume que las reinas de las ´
hadas entregaran todas juntas a Nimu ´ e las escamas recogidas el n ´ umero que sea ´
necesario. Este numero debe ser mayor o igual al n ´ umero de escamas que nece- ´
sitan las hechiceras. Podeis usar como punto de partida la mitad del n ´ umero de ´
hechiceras. En todo caso, se debe indicar en la memoria cuantas veces cada una ´
de las hadas debera recoger escamas en el lago, ´
Mientras nadie la molesta, Nimue est ´ a meditando en la orilla del lago. S ´ olo la ´
pueden interrumpir o bien las tres reinas de las hadas, trayendole escamas; o bien, ´
una hechicera que pidiendole una escama de drag ´ on. En el caso de las hechiceras, ´
si tiene escamas de dragon, Nimu ´ e se las entrega y vuelve a meditar. En el caso ´
de las reinas de las hadas, Nimue recibe las escamas y si hubiese alguna hechicera ´
esperando, entrega las que fuesen necesarias. Si no, vuelve a meditar. El numero ´
de escamas que posee Nimue inicialmente es ´ numEscamasDama (este numero ´
puede ser 0).
Hay muchas suposiciones erroneas sobre la isla de Avalon, pero la m ´ as ex- ´
tendida es que la isla esta cerca de las costas de Breta ´ na. Nada m ˜ as lejos de la ´
realidad. A Avalon solo se puede llegar a trav ´ es de un barco m ´ agico que navega ´
por el r´ıo de la vida. Caronte es el barquero que lleva a los viajeros, ya solo ´
ese dato deber´ıa ser suficiente para hacernos reflexionar sobre la conveniencia de
visitar la isla.
El barco de Caronte tiene capacidad para maxPersonasCaronte personas.
El comportamiento de Caronte es el siguiente:
1. En el muelle de Ankh-Morpork, Caronte abre la puerta del barco.
2. Espera 100 ms.
3. Caronte cierra la puerta del barco (independientemente de si se han subido
personas o no).
4. Caronte zarpa hacia la isla. El viaje dura 200 ms.
5. En la isla, Caronte abre la barrera para que las hechiceras desembarquen del
barco.
6. Una vez todas las hechiceras han desembarcado (y no antes, debe esperar
a que todas hayan desembarcado), Caronte abre la barrera para que las
hechiceras embarquen hacia Ankh-Morpork.
7. Espera 100 ms.
8. Caronte cierra la puerta del barco (independientemente de si se han subido
personas o no).
9. Caronte zarpa hacia Ankh-Morpork. El viaje dura 200 ms.
10. En el muelle de la ciudad, Caronte abre la barrera para que las hechiceras
desembarquen del barco.
11. Una vez todas las hechiceras han desembarcado (y no antes, debe esperar a
que todas hayan desembarcado), Caronte vuelve al paso 1.
Caronte terminara su ejecuci ´ on una vez todas las novicias hayan comple- ´
tado el ritual de Avalon y hayan vuelto a Ankh-Morpork sanas y salvas, y con
una escama de dragon en su poder. ´
Cada novicia ira a Avalon en el barco de Caronte, se quedar ´ a un tiempo aleato- ´
rio en la isla (menor de 200 ms), pedira una escama de drag ´ on a la Dama del ´
Lago, estara por la isla otro tiempo aleatorio (menor de 100ms) y volver ´ a a Ankh- ´
Morpork en el barco de Caronte.
Implementa todo el sistema utilizando el mecanismo de sincronizacion indi- ´
cado en cada ejercicio. Nimue, Caronte, las hechiceras, los dragones y las hadas ´
deben ser hilos. Debes implementar el codigo de todas las clases involucradas, ´
y el codigo del programa principal que genera a todos los participantes. Puedes ´
entregar todas las clases en el mismo fichero o en ficheros separados.
El programa principal invocarse de la siguiente manera:
java Avalon opciones
Donde las opciones, todas obligatorias, son:
• -d totalDragons: numero total de dragones. ´
• -mD maxDragonsInIsland: numero m ´ aximo de dragones en la isla. ´
• -n totalNovices: numero total de novicias.
• -mN maxHechicerasIsla: numero m ´ aximo de hechiceras en la isla. ´
• -e numEscamasDama: numero de escamas que posee la Dama del Lago. ´
• -mE maxEscamasLago: numero m ´ aximo de escamas en el lago. ´
• -b maxBarco: numero m ´ aximo de personas en el barco de Caronte. ´
Recuerda que el programa debe finalizar una vez todas las novicias han vuelto
a Ankh-Morpork. Para que el sistema termine, se ha de calcular el numero de ´
veces que cada dragon entra en la isla y el número de escamas que cada Reina de las Hadas recogera (estos dos números deben ser iguales o superiores al número de hechiceras).
Para que pueda terminar Nimue, este hilo (y sólo este hilo) puede usar los métodos acquire para semaforos y wait para la parte de monitores
con temporizador.
