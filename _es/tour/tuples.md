---
layout: tour
title: Tuples
partof: scala-tour
num: 
language: es

next-page: mixin-class-composition
previous-page: inner-classes

---

En Scala, una tupla es un valor que contiene una cantidad fija de elementos, cada cual de un tipo diferente.
Tuplas son inmutables.

Las tuplas son prácticas para el retorno de  múltiples valores desde un método.

Una tupla que contiene dos elementos puede ser creada:

```tut
val ingrediente = ("Azucar" , 25)
```
Esto crea una tupla conteniendo un elemento `String` y un element `Int`.

El tipo inferido de `ingredientes` es `(String, Int)`, siendo una versión corta de `Tuple2[String, Int]`.

Para representar una tupla Scala usa una serie de clases: `Tuple2`, `Tuple3`, etc.. hasta `Tuple22`.
Cada clase contiene tantos tipos de parámetros como sus elementos.

## Accediendo a sus elementos

Una manera de acceder a los elementos de una tupla es por posición. 
Los elementos individualmente son nombrados `_1`, `_2` y asi sucesivamente.


```tut
println(ingredientes._1) // Azucar
println(ingredientes._2) // 25
```

## Reconociemto de patrones en tuplas

Una tupla puede ser descompuesta usando `reconocimiento de patrones` 

```tut
val (nombre, cantidad) = ingredientes
println(nombre) // Azucar
println(cantidad) // 25
```

El tipo inferido de `nombre` es `String` y  `cantidad`  es `Int`.

Otro ejemplo de `reconociemnto de patrones` en una tupla:

```tut
val planetas =
  List(("Mercurio", 57.9), ("Venus", 108.2), ("Tierra", 149.6),
       ("Marte", 227.9), ("Jupiter", 778.3))
planets.foreach{
  case ("Tierra", distancia) =>
    println(s"Nuestro planeta esta a $distance millones de kilometros desde el sol")
  case _ =>
}
```

Un ejemplo para compresiones `for`:

```tut
val numPares = List((2, 5), (3, -7), (20, 56))
for ((a, b) <- numPares) {
  println(a * b)
}
```

## Tuplas y Casos de clase

Quizás encuentre alguna vez dificultad para escoger entre Tuplas y `Casos de clase`. `Casos de clase` tiene elementos que pueden ser  nombrados.
Los nombres pueden facilitar la comprensión de algunos tipos de códigos. En el ejemplo anterior de los planetas, quizás podiamos definir `case class Planeta(nombre: STring, distancia: Double)` en vez de tuplas.
