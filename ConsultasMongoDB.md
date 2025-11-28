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
  id_pedido: "p10004",
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

Mediante "insertOne()" para agregar un pedido y "inserMany" para agregar múltiples pedidos a la vez, se facilita la gestión eficiente de los pedidos, permitiendo detallar de forma organizada cada pedido.

- InsertOne()

Cuando se realiza un solo pedido, se utilliza "insertOne()" para insertar ese documento en la colección "Pedidos".

<p align="center"><img width="818" height="420" alt="image" src="https://github.com/user-attachments/assets/0f36d9c0-0cea-4877-8f52-a23b8f2b5384" /></p>

- InsertMany()

Cuando se realiza varios pedidos a la vez, se utiliza "insertMany()" para insetar múltiples documentos en la colección de forma simultánea.

<p align="center"><img width="818" height="420" alt="image" src="https://github.com/user-attachments/assets/88549e93-55d2-406c-80da-e534751b02ec" /></p>

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

Se actualizó la información de los pedidos por medio de "updateOne()", modificando la ciudad y cantidad de articulos de acuerdo con el id seleccionado.

- Actualiza ciudad de un pedido

Se cambio la ciudad del pedido "p1001" a "Medellín"

<p align="center"><img width="818" height="420" alt="image" src="https://github.com/user-attachments/assets/47783750-577e-4ae3-a233-50bf0c94de74" /></p>

- Actualizar la cantidad de artículos por id

En el pedido con id "p10002"se modificó la cantidad a "2"

<p align="center"><img width="818" height="420" alt="image" src="https://github.com/user-attachments/assets/fd57fe5d-694a-4873-aec5-7534696a0aae" /></p>
