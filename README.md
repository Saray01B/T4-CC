# 🍔 Tarea4_BigData_ComidaRapida

## Descripción del caso de uso

En esta actividad se utiliza el conjunto de datos sobre Pedidos de Comida Rápida. Contiene información como el id, hora y valor del pedido, ciudad, tipo de cocina, tiempo de entrega en minutos, método de pago y cantidad de artículos.

Se busca llevar a cabo un análisis sobre los pedidos de comida rápida, con el objetivo de realizar consultas que permitan identificar patrones de comportamiento de los usuarios, preferencias gastronómica y tendencias relacionadas con los tiempo de entrega, obteniendo infomación util para la toma de decisiones y la optimización del proceso de entrega.

**LINK:** https://www.kaggle.com/datasets/prince7489/fast-food-ordering-pattern-dataset

## Diseño de la base de datos

**Nombre de la base de datos:** ComidaRapida

**Colección:** Pedidos

El dataset utilizado contiene información sobre los pedidos de comida rápida:

| Campo                   |  Tipo        | Descripción |
|-------------------------|--------------|-------------|
| id_pedido               |  String      | Identificador único del pedido. |
| hora_pedido             |  String      | Hora en la que se realizó el pedido. |
| ciudad                  |  String      | Ciudad donde se hizo el pedido. |
| tipo_cocina             |  String      | Tipo de cocina solicitada. |
| valor_pedido            |  float       | Valor total del pedidio. |
| tiempo_entrega_minutos  |  Number      | Tiempo transcurrido desde que se realiza el pedido hasta su entrega |
| metodo_pago             |  String      | Método de pago elegido por el cliente. |
| cantidad_arículos       |  Number      | Número total de artículos que componen el pedido. |

## Autor

**Leonardo Favio García Virguez**  
Grupo: 32
