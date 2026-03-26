# Conceptos Básicos de BDD y Gherkin

## Tabla de contenidos
- [¿Qué es BDD?](#qué-es-bdd)
- [Qué es Gherkin](#qué-es-gherkin)
- [Elementos Principales](#elementos-principales)
    -[Feature](#feature)
    -[Scenario](#scenario)
    -[Background](#background)
    -[Scenario Outline](#scenario-outline)
- [Buenas practicas elementos principales](#buenas-practicas-elementos-principales)
    -[Feature Buenas Practicas](#feature-buenas-practicas)
    -[Scenario Buenas Practicas](#scenario-buenas-practicas)
    -[Background Buenas Practicas](#background-buenas-practicas)
    -[Scenario Outline Buenas Practicas](#scenario-outline-buenas-practicas)
- [Estructura gherkin](#estructura-gherkin)
    -[Given](#given)
    -[When](#when)
    -[Then](#then)
    -[And](#and)
    -[But](#but)

## ¿Qué es BDD?
Bdd significa Desarrollo impulsado por el comportamiento y se centra en describir el comportamiento del sistema

Bdd realiza las preguntas ¿Qué hace el sistema? y ¿Por qué lo hace el sistema?, como lo indica su metodología se centra en el comportamiento y esas son las preguntas principales de la metodología

## ¿Qué es Gherkin?
Es el nombre del lenguaje que se utiliza para describir el comportamiento y tiene sus propias reglas

## Elementos Principales

### Feature
Representa la funcionalidad del sistema, puede ser escrito desde la perspectiva del usuario o del negocio, define ¿Qué hace el sistema?, no como se implementa

### Scenario
Describe una caso concreto de comportamiento. Un ejemplo especifico de como debe de funcionar la feature, cada escenario debe de ser independiente

### Background
Se utiliza para definir el contexto inicial, evitando repetir pasos en cada escenario, reutilizando de forma clara y sencilla el Given y el And, si mayor o igual de 3 escenarios ocupan los mismo pasos implementarlo , evitarlo si es en menos de 3 escenarios

### Scenario Outline
Se utiliza cuando el comportamiento de la funcionalidad no cambia, y un mismo escenario puede ser probado de multiples maneras y podemos hacer uso de una tabla llamada examples. En dicha tabla colocaremos las variables y si dichas variables son validas o invalidas segun las pruebas

## Buenas Practicas Elementos principales

### Feature Buenas Practicas
El nombre del feature responde ¿Qué funcionalidad es la que voy probar? De tal manera que sea entendible para cualquier involucrado, es importante no usar un lenguaje tecnico sino ser lo más especifico y sencillo posible. 

Nota: Siempre especificar cual es el porque de tu funcionalidad , ya que permite profundizar en lo que se va a probar

Ejemplo correcto: Transferencias Bancarias

Ejemplo incorrecto: API de Transferencias

### Scenario Buenas Practicas
Describe que comportamiento de mi funcionalidad voy a probar (Un escenario de prueba), debe leerse como una historia corta

Un Scenario responde principalmente a: 

¿Qué comportamiento ocurre en una situación concreta? Muchas veces ese comportamiento:

1. Lo realiza un usuario u otro tipo de usuario

  -Scenario: Usuario visualiza un mensaje de confirmación al agregar un producto
  
  -Scenario: Administrador aprueba la solicitud de vacaciones
  
Mismo escenario pero sin quien realiza la acción 

  -Scenario: Usuario visualiza el saldo de su cuenta

  -Scenario: Se muestra el saldo con formato monetario correcto

2. Lo ejecuta el sistema

  -Scenario: El sistema rechaza la operación cuando la cuenta está bloqueada

  -Scenario: Se muestra un error cuando el saldo es insuficiente

  -Scenario: Se calcula correctamente el total del carrito

Mismo escenario pero sin quien realiza la acción

  -Scenario: Usuario visualiza el saldo con formato correcto

  -Scenario: Se muestra el saldo con formato correcto al consultar la cuenta

### Background Buenas Practicas
[Usarlo solo si se repite 3 o más de 3 escenarios ocupan los mismo pasos, en ese caso implementarlo , evitarlo si es en menos de 3 escenarios, y estos deben de ser cortos y sencillos, debe de describir un estado no acciones del usuario
Ejemplo correcto:

Background:
  Given el cliente está autenticado
  And se encuentra en la pantalla de transferencias

Ejemplo incorrecto:
Background:
  Given el cliente quiere hacer una transferencia]


### Scenario Outline Buenas Practicas
Se utiliza solo si la logica es identica, y el escenario aplica para varios ejemplos, máximo 5 ejemplos para escenarios de este tipo, más de 5 nos dice que quizás debemos de dividir los escenarios

## Estructura Gherkin
### Given 
El Given describe la acción previo al escenario. Es el inicio para detonar nuestro flujo 
### When
Lo que detona el escenario . Es decir, que acción me permite validar mi escenario. Es el corazón del escenario y y capta el momento en que el usuario interactura con el sistema. Siempre de manera detallada, no quedarnos con lo que nos dice el escenario, si hablamos de una busqueda, lo correcto sería ingresar un articulo. No solo que el usuario realizará una busqueda. Sino que es lo que va a buscar
### Then
Describe el resultado esperado a partir de la acción anterior. En este caso del Then
### And

### But
