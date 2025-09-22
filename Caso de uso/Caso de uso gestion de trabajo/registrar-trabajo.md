@startuml
title Registrar trabajo

Actor Usuario as U

usecase "Consultar trabajos" as UC1
usecase "Mostrar trabajos guardados" as UC2
usecase "Agregar trabajo" as UC3
usecase "Eliminar trabajo" as UC3_1
usecase "Modificar trabajo" as UC3_2
usecase "Completar campos de trabajo" as UC4
usecase "Guardar trabajo" as UC5
usecase "Verificar campos completos" as UC6

U --> UC1
UC1 --> UC2
UC2 --> UC3
UC3 --> UC3_1
UC3 --> UC3_2
UC3 --> UC4
UC4 --> UC5
UC5 --> UC6
UC6 --> UC4

note right of UC3_1
  3.1) En caso de eliminar el actor 
  selecciona el trabajo y hace click en 
  eliminar trabajo luego presiona 
  guardar cambios
end note

note right of UC3_2
  3.2) En caso de modificar trabajó el 
  actor se posiciona en el trabajo 
  modificando los campos y luego 
  presiona guardar cambios
end note

note right of UC6
  6.1) En caso de no estar completos 
  el sistema avisa que no se han 
  completados los campos y vuelve 
  al paso 4
end note

@enduml
