---
title: Calibración
layout: default
filename: 07_calibracion.md
--- 
# Calibración del equipo

La calibración general de la impresora 3D está dividida en dos partes: calibración de la cama y ajuste de altura Z.

Para hacer la calibración integral del equipo se entiende que las verificaciones explicadas en la [Puesta en marcha](./06_puesta_marcha.html) fueron realizadas con éxito.

## Calibración de la cama

1. Presionar el encoder. Ir a _Configuración -> Calibración Delta -> Auto Calibración_. Al elegir esta opción, cada brazo asociado a cada columna buscará su origen. Luego, descenderá hasta aproximadamente 4mm del centro de la cama caliente.

    ![cal1](./assets/img/cal1.jpg)
    ![cal2](./assets/img/cal2.jpg)
    ![cal3](./assets/img/cal3.jpg)

2. A partir de acá, el proceso de **Auto Calibración** consiste en generar un mapa de la cama caliente mediante la navegación de ```16pts``` por toda la superficie de la cama. A continuación, se detalla el mapa de los puntos, por que punto comienza el proceso y por cual termina.

    ![mapa_puntos_cama](./assets/img/mapa_puntos_cama.jpg)

Cada punto recorrido se ubicará en ```Z = 004.000mm``` y requiere determinar la altura correcta entre la cama caliente y el pico. Para esto, con la ayuda de un papel, voy rotando el encoder hasta lograr que el papel se mueva debajo del pico con una leve resistencia. Los saltos en Z serán de ```0.25mm```.

    ![cal4](./assets/img/cal4.jpg)
    ![cal5](./assets/img/cal5.jpg)

3. Al terminar la recorrida por los ```16pts```, en la pantalla aparecerá una leyenda que dice _Calibration sd: N_. **N** es el [desvío standard](https://es.wikipedia.org/wiki/Desviaci%C3%B3n_t%C3%ADpica), un valor que representa cuán dispares están los puntos de la cama caliente. Si el valor es mayor a ```0.5```, se recomienda repetir el proceso.

    ![cal6](./assets/img/cal6.jpg)

4. Como ultimo paso, ir a _Configuración -> Guardar EEPROM_

    ![cal7](./assets/img/cal7.jpg)
    ![cal8](./assets/img/cal8.jpg)    

## Ajuste de altura en Z

1. Presionar el encoder. Ir a _Configuración -> Movimiento -> Llevar al origen_. Al elegir esta opción, cada brazo asociado a cada columna buscará su origen.

    ![cal9](./assets/img/cal9.jpg)
    ![cal10](./assets/img/cal10.jpg)  

2. Ahora, se debe corregir la altura en Z. Para esto ir a _Configuración -> Movimiento -> Mover ejes -> Mover Z_. Con el encoder, bajar el pico hasta que se llegue a una distancia óptima entre el pico y la cama caliente.

    ![cal11](./assets/img/cal11.jpg)
    ![cal12](./assets/img/cal12.jpg) 
    ![cal13](./assets/img/cal13.jpg)
    ![cal14](./assets/img/cal14.jpg)

3. Cuando se logre una distancia óptima entre el pico y la cama caliente, la pantalla marcará _Mover Z:     VALOR_. **Anotar este valor!**

    ![cal15](./assets/img/cal15.jpg)

4. Con el valor de Z anterior, debemos corregir la altura de Z que se encuentra guardada en el sistema. Para esto ir a _Configuración -> Calibración Delta -> Configuración Delta -> Altura_.
    + Si el **VALOR** registrado en el punto anterior es **positivo** se debe hacer este cálculo: **(Z actual - VALOR)** y guardar el resultado.
    + Si el **VALOR** registrado en el punto anterior es **negativo** se debe hacer **(Z actual + VALOR)** y guardar el resultado.

5. Como último paso, ir a  _Configuración -> Guardar EEPROM_

    ![cal16](./assets/img/cal16.jpg)
    ![cal17](./assets/img/cal17.jpg)

### _"¿Cuándo tengo que hacer estos procedimientos?"_

Se recomienda hacerlos luego de que se haya manipulado la impresora para cambiar alguna parte, luego de varias impresiones o si la impresora se movió de lugar.

[![Puesta en marcha](./assets/img/boton6.jpg)](./06_puesta_marcha.html) [![Primera impresión](./assets/img/boton8.jpg)](./08_primera_impresion.html)