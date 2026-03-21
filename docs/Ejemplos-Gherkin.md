## Tabla de contenidos
- [Ejemplo future](#ejemplo-future)
- [Ejemplo scenario](#ejemplo-scenario)

## Ejemplo future

-Incorrecto:
  
  Feature: Inicio de registro de usuario mediante curp
  Como banco
  Quiero iniciar el registro de un usuario mediante el curp
  Para hacerlo cliente

-Recomendaciones:
  
  CURP debe ir en mayúsculas
  “Para hacerlo cliente” es ambiguo (¿cliente del banco? ¿cliente activo?)

-Correcto:
  
  Feature: Inicio de registro de usuario mediante CURP
  Como Banco
  Quiero iniciar el registro de un usuario usando su CURP
  Para convertirlo en cliente del banco

-Incorrecto:
  
  Feature: Registro de medios electronicos 
  Como banco
  Quiero Registrar los mendios electronicos 
  Para notificar al usuario

-Recomendaciones:
  
  ¿Que vas a notificar?

-Correcto:
  
  Feature: Registro de medios electrónicos
  Como Banco
  Quiero registrar los medios electrónicos del usuario
  Para poder notificarle información relevante

-Incorrecto:
  
  Feature: Verificación de OTP
  Como Banco
  Quiero confirmar la otp 
  Para poder confirmar el número de celular

-Recomendaciones:
  
  Omitir repetición de “confirmar”

-Correcto:

  Feature: Verificación de OTP
  Como Banco
  Quiero validar el código OTP enviado al usuario
  Para confirmar su número de celular

-Incorrecto:

  Feature: Registro de Datos
  Como Banco
  Quiero Registrar el domicilio del usuario
  Para Conocer su dirección

-Recomendaciones:
  
  “Registro de Datos” es demasiado genérico

-Correcto: 

  Feature: Registro de domicilio del usuario
  Como Banco
  Quiero registrar el domicilio del usuario
  Para conocer su dirección fiscal y de contacto

-Recomendaciones:
  
  “Registro de Datos” es demasiado genérico

-Correcto: 

  Feature: Registro de domicilio del usuario
  Como Banco
  Quiero registrar el domicilio del usuario
  Para conocer su dirección fiscal y de contacto

  Correcto:

  Feature: Evaluación economica del cliente
  Como Banco
  Quiero evaluar al usuario economicamente
  Para saber si es apto para una tarjeta de debído

## Ejemplo scenario

  Ejemplos: 
  
  Feature: Inicio de registro de usuario mediante CURP
  
  Scenario: Inicio de registro de usuario con CURP extranjera válida

  Feature: Registro de número celular
  
  Scenario: Registro de número celular con lada internacional rechazado
 
  Feature: Verificación de OTP
  
  Scenario:  Verificación de OTP fallida por omisión de ingreso

  Feature: Registro de domicilio del usuario
  
  Scenario: Registro de domicilio rechazado por código postal con formato inválido

  Feature: Evaluación economica de clientes

  Scenario: Rechazo de evaluación económica para cliente con perfil estudiante
  