# Código de consultas para el Dataset Pedidos de Comida Rápida

## Consultas básicas

### Inserción

### Código

- InsertOne()

```python
db.Pedidos.insertOne({
  id_pedido: "p10001",
  hora_pedido: "14:35",
  ciudad: "Bogotá",
  tipo_cocina: "Italian",
  valor_pedido: 45000,
  tiempo_entrega_minutos: 35,
  metodo_pago: "Credit Card",
  cantidad_articulos: 3
})
```
- InsertMany()

```python
db.Pedidos.insertMany([
{
  id_pedido: "p10002",
  hora_pedido: "14:20",
  ciudad: "Cali",
  tipo_cocina: "Mexican",
  valor_pedido: 38000,
  tiempo_entrega_minutos: 30,
  metodo_pago: "Wallet",
  cantidad_articulos: 4
},
{
  id_pedido: "p10003",
  hora_pedido: "21:05",
  ciudad: "Barranquilla",
  tipo_cocina: "Chinese",
  valor_pedido: 52000,
  tiempo_entrega_minutos: 42,
  metodo_pago: "Credit Card",
  cantidad_articulos: 3
}
])
```
### _MongoDB_ 

Mediante "insertOne()" para agregar un pedido y "inserMany" para agregar múltiples pedidos a la vez. Facilita la gestión eficiente de los pedidos y  permite detallar de forma organizada cada pedido.

- InsertOne()

Cuando se realiza un solo pedido, se utilliza "insertOne()" para insertar ese documento en la colección "Pedidos".

<p align="center"><img width="818" height="420" alt="image" src="https://github.com/user-attachments/assets/c451122b-3898-492f-a0e5-d81ac8bb7e8b" /></p>

- InsertMany()

Cuando se realiza varios pedidos a la vez, se utiliza "insertMany()" para insetar múltiples documentos en la colección de forma simultánea.

<p align="center"><img width="818" height="420" alt="image" src="https://github.com/user-attachments/assets/8c6cb36b-55aa-458e-9954-53664a1aab8b" /></p>

### Selección

### Código

- Seleccionar pedidos por ciudad

```python
db.Pedidos.find({
  ciudad: "Chennai"
})
```
- Seleccionar pedidos por tipo de comida

```python
db.Pedidos.find({
  tipo_cocina: "Mexican"
})
```
### _MongoDB_ 

Se realizaron consultas para obtener información específica de los pedidos según la ciudad y el tipo de cocina, utilizando el método "find()" para identificar y filtran los pedidos con base a los criterios definidos.

- Seleccionar pedidos por ciudad

Muestran los pedidos que se han realizado en la ciudad de "Chennai".

<p align="center"><img width="818" height="420" alt="image" src="https://github.com/user-attachments/assets/ee25dc00-78a8-452c-a500-003bc9385b63" /></p>

- Seleccionar pedidos por tipo de comida

Muestra los pedido en los que el tipo de comida corresponde a "Mexican".

<p align="center"><img width="818" height="420" alt="image" src="https://github.com/user-attachments/assets/4be2d6e7-31f6-4d6c-a4dd-db9b69c448a1" />></p>

### Actualización

### Código

- Actualiza ciudad de un pedido

```python
db.Pedidos.updateOne(
  {id_pedido: "p10001"},
  {$set: {ciudad: "Medellín"}}
)
```
- Actualizar la cantidad de artículos por id

```python
db.Pedidos.updateOne(
  {id_pedido: "p10002"},
  {$set: {cantidad_articulos: "2"}}
)
```
### _MongoDB_ 

Se actualizó la información de los pedidos por medio de "updateOne()", modificando la ciudad y cantidad de articulos de acuerdo con el id seleccionado. Permitiendo tener la información correcta en la colección "Pedidos".

- Actualiza ciudad de un pedido

Se cambio la ciudad del pedido "p1001" a "Medellín"

<p align="center"><img width="818" height="420" alt="image" src="https://github.com/user-attachments/assets/4638f135-856a-466e-9a84-24f17cb606fa" /></p>

- Actualizar la cantidad de artículos por id

En el pedido con id "p10002"se modificó la cantidad a "2"

<p align="center"><img width="818" height="420" alt="image" src="https://github.com/user-attachments/assets/d74c82f0-3737-492f-80fe-08ec741d8819" /></p>

### Eliminación

### Código

- deleteOne()

```python
db.Pedidos.deleteOne({
  id_pedido: "p10001"
})
```
- deleteMany()

```python
db.Pedidos.deleteMany({
  tiempo_entrega_minutos: 61
})
```
### _MongoDB_ 

Se eliminaron los pedidos utilizando los método "deleteOne()" y "deleteMany()", permitiendo quitar registros que cumplen con los criterios establecidos.

- deleteOne()

Se eliminó el pedido con el id_pedido correspondiente a "p1001", quitando unicamente este documento.

<p align="center"><img width="818" height="420" alt="image" src="https://github.com/user-attachments/assets/5b1537d3-769d-4416-afc1-38dfc1f75abe" /></p>

- deleteMany()

Se eliminaron todos los pedidos en el que el tiempo de entrega era exactamente 611 minutos, quitando los 9 registros que cumplían esta condición.

<p align="center"><img width="818" height="420" alt="image" src="https://github.com/user-attachments/assets/505ee1e0-8ae1-40fd-a207-c06139e21d71" /></p>

## Consultas con filtros y operadores

### Consultas con filtros

### Código

- Seleccionar pedidos pagados con targeta de crédito

```python
db.Pedidos.find({
  metodo_pago: "Credit Card"
})
```

- Seleccionar los pedidos con un valor mayor a "30000"

```python
db.Pedidos.find({
  valor_pedido: {$gt: 30000}
})
```

### MongoDB

Mediante el método "find()" se realizaron consultas utilizando filtro en el método de pago y valor de los pedidos. Permitiendo identificar patrones de compra y analizar el comportamiento de los usuarios.

- Seleccionar pedidos pagados con targeta de crédito

Se seleccionan los pedidos en los que el método de pago es "Credit Card".

<p align="center"><img width="818" height="420" alt="image" src="https://github.com/user-attachments/assets/2d19beb0-1487-435b-aad4-e5909c9b791c" /></p>

- Seleccionar los pedidos con un valor mayor a "30000"

Con el operador $gt se seleccionan los pedido en los que el precio del pedido es mayor a "30000"

<p align="center"><img width="818" height="420" alt="image" src="https://github.com/user-attachments/assets/2a7a61f4-bee8-4d9d-81fa-e8b1a4df483c" /></p>

### Consultas con operadores

### Código

- Seleccionar pedidos que el tipo de cocina no es "Mexican"

```python
db.Pedidos.find({
  tipo_cocina: {$ne: "Mexican"}
})
```

- Seleccionar los pedidos con un valor entre "20000" y "50000"

```python
db.Pedidos.find({
  valor_pedido: {$gte: 20000, $lte: 50000}
})
```

### MongoDB

Se utilizó **ne** para seleccionar los valores diferentes al establecido, así como **gte** y **lte** para filtrar valores dentro de un rango determinado.

- Seleccionar pedidos que el tipo de cocina no es "Mexican"

Con el operador **ne** se obtienen todos los pedidos en donde el tipo de cocina es diferente de "Mexican".

<p align="center"><img width="818" height="420" alt="image" src="https://github.com/user-attachments/assets/a71d9dab-8234-42ad-b4fc-049045e6922d" /></p>

- Seleccionar los pedidos con un valor entre "20000" y "50000"

Con la combinación de los operadores **gte** y **$lte** se obtienen los pedidos cuyo valor del pedido se encuentran por encima de "20000" y por debajo de "50000".

<p align="center"><img width="818" height="420" alt="image" src="https://github.com/user-attachments/assets/eccd3932-32d7-4ed0-858e-24f946e38fd5" /></p>

## Consultas de agregación para calcular estadísticas

### Contar

### Código

- Contar total de pedidos

```python
db.Pedidos.aggregate([
  {$count: "total_pedidos"}
])
```

- Contar pedidos por ciudad

```python
db.Pedidos.aggregate([
  {$group: {_id: "$ciudad", Total: {$sum: 1}}},
  {$sort: {Total: -1}}
])
```

### MongoDB

Mediante el método "aggregate()" se realizaron consultas para contar y agrupar lo pedidos, permitiendo analizar información de los clientes según criterios como la cantidad y la ciudad de los pedidos.

- Contar total de pedidos

Se calcula el número total de pedido registrados en la colección para conocer el volumen de transacciones realizadas.

**Resultado:** El total de pedidos realizados es de 493. Por lo que se puede conocer la demanda general de comida rápida y planificar estrategias basadas en la cantidad de pedidos.

<p align="center"><img width="818" height="420"width="400" height="185" alt="image" src="https://github.com/user-attachments/assets/c240d2e5-999b-48a6-bb68-8726372033d4" /></p>

- Contar pedidos por ciudad

Se agrupan los pedidos según la ciudad y se calcula la cantidad de pedidos en cada una, permitiendo identificar las ciudades con mayor número de pedidos.

**Resultado:** La ciudad con más pedidos es "Hyderabad" con 76 pedidos, seguida de "Ahmedabad" con 71. Esto permite identificar las ciudades donde hay mayor actividad de pedidos y puede ser clave para tomar desiciones de distribución y promoción.

<p align="center"><img width="818" height="420" alt="image" src="https://github.com/user-attachments/assets/3da8da84-c82d-488c-94eb-5aba11af83ed" /></p>

### Sumar

### Código

- Sumar el valor total de todos los pedidos

```python
db.Pedidos.aggregate([
  {$group: {_id: null, total_valor: {$sum: "$valor_pedido"}}},
])
```

- Sumar la cantidad total de artículos por tipo de cocina

```python
db.Pedidos.aggregate([
  {$group: {_id: "$tipo_cocina", total_articulos: {$sum: "$cantidad_articulos"}}},
  {$sort: {total_articulos: -1}}
])
```

### MongoDB

Se reaizaron consultas para sumar criterios como la cantidad de artículos, tipo de cocina y valor de los pedidos, permitiendo obtener información sobre las preferencias de los clientes.

- Sumar el valor total de todos los pedidos

Se calcula la suma total de los valores de todos los pedidos realizados para conocer el total generado por los pedidos.

**Resultado:** El valor total de todos los pedidos realizados es de 399.955,75, permite evaluar el estado financiero y tomar decisiones estrategicas sobre los pedidos.

<p align="center"><img width="818" height="420" alt="image" src="https://github.com/user-attachments/assets/dcf747fa-f29e-4323-b6fe-e5dd690356c4" /></p>

- Sumar la cantidad total de artículos por tipo de cocina

Se agrupan los pedidos por tipo de cocina y se suma la cantidad de articulos de cada uno, identificando el tipo de cocina más solucitado.

**Resultado:** El tipo de con más artículos pedidos es "Fast Food" con 311 artículos, seguido de "South Indian" con 303 artículos, evidenciando la preferencia de los cliente y facilitando la planificación del inventario.

<p align="center"><img width="818" height="420" alt="image" src="https://github.com/user-attachments/assets/0b032b51-1539-4de6-aeb9-1790eb4e45db" /></p>
