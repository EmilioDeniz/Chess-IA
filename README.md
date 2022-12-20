# Chess-IA

- El conjunto de datos contiene imagenes de piezas de ajedrez, todas de la misma resolución con un total de 5 clases con 119, 95, 62,154 y 121 imagenes, correspondiendo al alfil,caballo,peón,reina y torre respectivamente. 

- El conjunto de validación contiene 20 imagenes cada una.

 Enlace al dataset : https://www.kaggle.com/datasets/niteshfre/chessman-image-dataset

- Para mejorar los resultados, hemos usado data augmentation.

- El método que hemos seguido es random search, cambiando el dropout y el MaxPooling primero. La precisión que apuntamos es la que da en la última línea antes de que haga el early stopping.

