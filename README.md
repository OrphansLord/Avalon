/**
 * Avalon.java
 * 
 * Solucion al problema de la Isla Avalon utilizando semáforos como mecanismo de sincronización.
 * Se modelan los siguientes participantes como hilos:
 *    - Dragon: cada uno repite su bucle un numero repetido de veces:
 *         1. Vuelo (aleatorio < 1 s).
 *         2. Expresa deseo de entrar en la isla (solo entra cuando el número de hechiceras en la isla es el permitido, según la cantidad de dragones que haya en la               isla por el momento).
 *         3. Una vez dentro, descansa (<200 ms), deposita una escama en el lago (esperando si es necesario), y permanece un tiempo (<200 ms) antes de salir.
 *
 *    - Novicia (hechicera): viaja en el barco de Caronte, desembarca en Avalon, entra en la isla, espera un tiempo, solicita una escama a Nimue, espera un tiempo y         regresa en barco a la ciudad de Ankh-Morpork de nuevo.
 *
 *    - Caronte: controla el barco que tiene un límite máximo de tripulantes, transporta a las hechiceras de Ankh-Morpork a Avalon y viceversa.
 *
 *    - Nimue: es la Dama del Lago, duerme hasta que es despertada por una petición (novicia) o por la entrega de escamas por parte de las Reinas de las Hadas.
 *
 *    - Reina de las Hadas: hay tres reinas (Titania, Morgana y Mab) que se dedican a recoger escamas del lago; cada una “colecciona” 2 escamas mínimo y espera a sus
        compañeras para entregar conjuntamente a Nimue.
 *
      - Existe una clase "Island" encargada de controlar la entrada de dragones y hechiceras según el acuerdo (la presencia de dragones reduce el máximo de
        hechiceras permitidas):
 *        - Si hay 1 dragón: se permite hasta maxHechicerasIsla.
 *        - Si hay 2 dragones: se permite la mitad de maxHechicerasIsla.
 *        - Si hay 3 o más dragones: se permite un cuarto de maxHechicerasIsla.
 *
      - El numero total de escamas depositadas por los dragones sea >= el número de hechiceras y sea múltiplo de 6;
        dicho cálculo se hace en main y se utiliza para definir:
 *        - El número de veces que cada dragón entra en la isla (dragonIterations).
 *        - El número de “colecciones” que debe realizar cada Reina (queenCollections), de modo que entre las tres se recojan (dragonIterations*totalDragons)
 *          todas las escamas.
 *
 * Por último para destacar, en el código se ha cuidado la Exclusión Mutua, la Ausencia de DeadLock y de Inanición utilizando semáforos para cada coordinación.
 *
 */
