@startuml
title Reservar turno

Actor Cliente as C

usecase "Ingresar datos personales" as UC1
usecase "Validar datos" as UC2
usecase "Consultar lista de trabajos" as UC3
usecase "Seleccionar trabajo" as UC4
usecase "Consultar turnos disponibles" as UC5
usecase "Seleccionar turno" as UC6
usecase "Guardar turno y enviar confirmación" as UC7

C --> UC1
UC1 --> UC2
UC2 --> UC3
UC3 --> UC4
UC4 --> UC5
UC5 --> UC6
UC6 --> UC7

note right of UC2
  2.1) En caso de no validar, 
  el sistema pide corregir los datos
end note

note right of UC6
  10.1) En caso de elegir un turno no disponible,
  el sistema abre pantalla de advertencia
  sugiriendo que seleccione otro turno
end note

@enduml
