---
tags:
  - java
  - textos
  - strings
---
# anotaciones de [[JAVA primer curso]]

## strings
para la creacion de una string, a una variable se asigna un texto de cualquier largo declarandolo entre comillas dobles

```java
String nombre = "Alura";
```

## concatenacion
una de las diversas formas de concatenar strings es asignar o otra variable la "suma" de las variables que contienen strings

```java
String saludo = "Hola, ";
String nombre = "Alura";
String mensaje = saludo + nombre + "!";
```

## comparacion


```java
String saludo = "Hola, mi nombre es ";
String nombre = "Alicia ";
String continuacion = "y mi edad es ";
int edad = 17;

Sistem.out.println(String.format("%s %s, %s %d años"));
String mensaje = saludo + nombre + "," + continuacion + (String)(edad);
Sistem.out.println(mensaje)
```
```csharp
String nombre = "Maria";
int edad = 30;
double valor = 55.9999;
System.out.println(String.format("Mi nombre es %s, tengo %d años y hoy gasté %.2f dolares", nombre, edad, valor));
```