# Chess-IA
Trabajo 2 de FSI: entrenar una Inteligencia Artificial de reconocimiento de imágenes

- El conjunto de datos contiene imagenes de piezas de ajedrez, todas de la misma resolución con un total de 5 clases con 139, 115, 82,174 y 141 imagenes, correspondiendo al alfil,caballo,peón,reina y torre respectivamente.

- Para mejorar los resultados, hemos usado data augmentation.

- El método que hemos seguido es grid search pero un poco diferente, cambiando el dropout y el MaxPooling primero. La precisión que apuntamos es la que da en la última línea antes de que haga el early stopping.

*Capas de convolución: 32,64,128*
*Dropout 0,25*
*MP 2*

-Primer intento: se atascaba en el 94% (paré antes de tiempo y no pude obtener una gráfica)

-Segundo intento 96,64%

![image](https://user-images.githubusercontent.com/113598358/208484590-2ba6741f-2647-42c3-b7be-f23010a60b1a.png)

![image](https://user-images.githubusercontent.com/113598358/208484618-2b9ec7c9-17fa-46bc-9999-076a03b9c00e.png)

![image](https://user-images.githubusercontent.com/113598358/208484643-c6c5824f-408c-487c-8af8-16cb0d04b558.png)

Tras cambiar el Dropout a 0,15 y 0,35 se notaba que a la máquina le costaba mucho avanzar así que lo mejor por lo que se ve es no cambiar excesivamente este hiperparámetro.

*Dropout a 0,20*

97,13 % de precisión 

![image](https://user-images.githubusercontent.com/113598358/208484683-257b9695-7c1c-4c0a-bb50-78676dc7fbc0.png)

![image](https://user-images.githubusercontent.com/113598358/208484705-90a14b35-5ed0-4117-bcb6-32b692fd0e39.png)

![image](https://user-images.githubusercontent.com/113598358/208484730-2db7f025-8e69-4c9d-88bf-fb5da9b456f7.png)

*Dropout a 0,30*

96,64% de precisión

![image](https://user-images.githubusercontent.com/113598358/208484794-88bdbabb-cc9e-4cc5-bac5-8a9405870d28.png)

![image](https://user-images.githubusercontent.com/113598358/208484816-68f2ab80-2832-4b87-988c-e88d09d70cf8.png)

![image](https://user-images.githubusercontent.com/113598358/208484839-6daba45d-e343-4646-9a3e-37d402469708.png)

A raíz de estos resultados, la solución más óptima creemos que es 0,25.

*Capas de convolución: 32,64,128*
*Dropout 0,25*
*MP 4*

Precisión: 94,47% 

![image](https://user-images.githubusercontent.com/113598358/208484911-02209c62-363d-445e-8c21-7570df60569e.png)

![image](https://user-images.githubusercontent.com/113598358/208484929-80e2cc98-a3dd-4790-94c7-c22b7769708c.png)

![image](https://user-images.githubusercontent.com/113598358/208484952-854cc9e8-f6d3-4c05-915a-a99c7f35f88a.png)


Se aprecia una mejoría al usar 4 en el Max Pooling, así que lo que faltaría por comprobar es si hay una mejoría al cambiar las capas de convolución.

*Capas de convolución: 64,128,256*
*Dropout 0,25*
*MP 4*

Precisión 96,14% La mejora más notable está en el tiempo por época, reducido en unos 100 segundos.

![image](https://user-images.githubusercontent.com/113598358/208485001-272981b9-34d9-4a2a-a471-83eabbacbd76.png)

![image](https://user-images.githubusercontent.com/113598358/208485023-16203236-cd52-4a60-b75b-b130df99c737.png)

![image](https://user-images.githubusercontent.com/113598358/208485035-831bb364-eb44-43e2-8c53-91d670c0bf96.png)




