# Caso de Uso: Reservar turno

## Actores
- Cliente

## Precondiciones
-

## Requerimientos

### Normal
1. El actor ingresa su nombre, apellido, número telefónico y email
2. El sistema verifica que los datos ingresados sean correctos
3. El actor consulta lista de trabajos
4. El sistema muestra lista de trabajos
5. El actor selecciona el tipo de trabajo
6. El sistema verifica el trabajo seleccionado
7. El actor consulta turnos disponibles
8. El sistema muestra lista de turnos disponibles
9. El actor selecciona turno
10. El sistema guarda el turno realizado y envía email de confirmación al cliente

### Alternativo
2.1. En caso de no validar, el sistema pide corregir los datos
10.1. En caso de elegir un turno no disponible, el sistema abre pantalla de advertencia sugiriendo que seleccione otro turno

## Postcondiciones
- Turno reservado

