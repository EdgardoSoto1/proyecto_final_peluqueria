# Caso de Uso: Gestión de Cliente

## Actores
- Usuario del Sistema (Administrador/Empleado)

## Precondiciones
- Usuario logueado en el sistema con permisos de gestión de clientes

## Requerimientos

### Normal - Alta de Cliente
1. El actor accede al módulo de gestión de clientes
2. El sistema muestra el menú de opciones de cliente
3. El actor selecciona "Registrar nuevo cliente"
4. El sistema muestra el formulario con los campos a completar:
   - Nombre
   - Apellido
   - Número de teléfono
   - Email
   - Observaciones (opcional)
5. El actor completa los campos y presiona guardar
6. El sistema verifica que todos los campos obligatorios estén completos y válidos
7. El sistema registra el nuevo cliente y genera un ID único
8. El sistema muestra mensaje de confirmación con el ID del cliente

### Normal - Modificar Cliente
1. El actor accede al módulo de gestión de clientes
2. El sistema muestra la lista de clientes o formulario de búsqueda
3. El actor selecciona o busca el cliente a modificar
4. El sistema muestra el formulario con los datos actuales del cliente
5. El actor modifica los campos deseados y presiona guardar
6. El sistema verifica que los datos sean válidos
7. El sistema actualiza la información del cliente y muestra confirmación

### Normal - Consultar Cliente
1. El actor accede al módulo de consulta de clientes
2. El sistema muestra las opciones de consulta:
   - Listar todos los clientes
   - Buscar cliente específico
   - Ver historial de cliente
3. El actor selecciona una opción
4. El sistema muestra la información solicitada:
   - Datos personales del cliente
   - Historial de turnos
   - Estado (Activo/Inactivo)

### Normal - Dar de Baja Cliente
1. El actor accede al módulo de gestión de clientes
2. El sistema muestra la lista de clientes activos
3. El actor selecciona el cliente a dar de baja
4. El sistema verifica si el cliente tiene turnos pendientes
5. El sistema solicita confirmación de la baja
6. El actor confirma la baja del cliente
7. El sistema desactiva el cliente y cancela turnos pendientes si los hay
8. El sistema muestra mensaje de confirmación

### Normal - Buscar Cliente
1. El actor accede a la función de búsqueda de clientes
2. El sistema muestra el formulario de búsqueda con criterios:
   - Buscar por nombre
   - Buscar por teléfono
   - Buscar por email
3. El actor ingresa criterios de búsqueda y ejecuta la búsqueda
4. El sistema busca clientes que coincidan con los criterios
5. El sistema muestra los resultados ordenados por relevancia

### Alternativo
6.1. En caso de email ya registrado, el sistema muestra mensaje "El email ya está registrado" y vuelve al paso 4
6.2. En caso de formato de email inválido, el sistema muestra mensaje "Formato de email inválido" y vuelve al paso 4
6.3. En caso de formato de teléfono incorrecto, el sistema muestra el formato esperado y vuelve al paso 4
3.1. En caso de cliente no encontrado, el sistema muestra mensaje "Cliente no encontrado" y regresa al paso 2
4.1. Si el cliente tiene turnos pendientes, el sistema muestra los turnos y pregunta si desea cancelarlos antes de dar de baja
5.1. En caso de no encontrar resultados, el sistema muestra "No se encontraron clientes con esos criterios"
6.1. Si el actor cancela la baja, el sistema regresa a la lista sin realizar cambios

## Postcondiciones
- Cliente creado, modificado, consultado o dado de baja según corresponda
- Historial del cliente mantenido para auditoría
- Turnos pendientes cancelados en caso de baja de cliente