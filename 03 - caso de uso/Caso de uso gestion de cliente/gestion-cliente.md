# Caso de Uso: Gestión de Cliente

## 1. Alta de Cliente

### Descripción
Permite al usuario del sistema registrar un nuevo cliente en la base de datos de la peluquería.

### Actor Principal
- Usuario del Sistema (Administrador/Empleado)

### Actor Secundario
- Cliente (cuando se autoregistra)

### Precondiciones
- El usuario debe estar autenticado en el sistema
- El usuario debe tener permisos para gestionar clientes

### Flujo Principal
1. El usuario accede a la opción "Gestionar Clientes"
2. El sistema muestra el menú de gestión de clientes
3. El usuario selecciona "Registrar nuevo cliente"
4. El sistema muestra el formulario de registro de cliente
5. El usuario ingresa los siguientes datos:
   - Nombre (obligatorio)
   - Apellido (obligatorio)
   - Número de teléfono (obligatorio)
   - Email (obligatorio)
   - Observaciones (opcional)
6. El sistema valida que:
   - Los campos obligatorios no estén vacíos
   - El formato del email sea válido
   - El número de teléfono tenga formato correcto
   - El email no esté registrado para otro cliente
7. El sistema registra el nuevo cliente
8. El sistema genera un ID único para el cliente
9. El sistema muestra mensaje de confirmación con el ID del cliente

### Flujos Alternativos
**6a. Email ya registrado:**
- El sistema muestra mensaje "El email ya está registrado para otro cliente"
- Muestra opción para ver el cliente existente
- Regresa al paso 5

**6b. Formato de email inválido:**
- El sistema muestra mensaje "Formato de email inválido"
- Regresa al paso 5

**6c. Teléfono con formato incorrecto:**
- El sistema muestra mensaje con el formato esperado
- Regresa al paso 5

### Postcondiciones
- Se crea un nuevo cliente en el sistema
- El cliente puede ser seleccionado para reservar turnos
- Se genera un historial vacío para el cliente

---

## 2. Modificar Cliente

### Descripción
Permite al usuario del sistema actualizar la información de un cliente existente.

### Actor Principal
- Usuario del Sistema (Administrador/Empleado)

### Precondiciones
- El usuario debe estar autenticado
- Debe existir al menos un cliente en el sistema

### Flujo Principal
1. El usuario accede a la opción "Gestionar Clientes"
2. El sistema muestra las opciones de gestión
3. El usuario selecciona "Modificar cliente"
4. El sistema muestra la lista de clientes o formulario de búsqueda
5. El usuario selecciona o busca el cliente a modificar
6. El sistema muestra el formulario con los datos actuales del cliente
7. El usuario modifica los campos deseados:
   - Nombre
   - Apellido
   - Número de teléfono
   - Email
   - Observaciones
   - Estado (Activo/Inactivo)
8. El sistema valida los datos modificados
9. El sistema actualiza la información del cliente
10. El sistema muestra mensaje de confirmación

### Flujos Alternativos
**5a. Cliente no encontrado:**
- El sistema muestra mensaje "Cliente no encontrado"
- Regresa al paso 4

**8a. Email ya existe para otro cliente:**
- El sistema muestra mensaje de error
- Regresa al paso 7

### Postcondiciones
- Los datos del cliente son actualizados en el sistema
- Se mantiene el historial de turnos del cliente

---

## 3. Consultar Cliente

### Descripción
Permite al usuario consultar la información de los clientes registrados en el sistema.

### Actor Principal
- Usuario del Sistema (Administrador/Empleado)

### Precondiciones
- El usuario debe estar autenticado

### Flujo Principal
1. El usuario accede a la opción "Consultar Clientes"
2. El sistema muestra las opciones de consulta:
   - Listar todos los clientes
   - Buscar cliente específico
   - Ver historial de cliente
3. El usuario selecciona una opción
4. **Si selecciona "Listar todos":**
   - El sistema muestra una lista paginada con todos los clientes activos
5. **Si selecciona "Buscar específico":**
   - El usuario ingresa criterios de búsqueda (nombre, teléfono o email)
   - El sistema muestra los clientes que coinciden
6. **Si selecciona "Ver historial":**
   - El usuario selecciona un cliente
   - El sistema muestra el historial completo de turnos del cliente

### Información Mostrada
- ID del cliente
- Nombre completo
- Teléfono
- Email
- Estado (Activo/Inactivo)
- Fecha de registro
- Cantidad de turnos realizados
- Último turno

### Postcondiciones
- Se muestra la información solicitada del cliente o clientes

---

## 4. Dar de Baja Cliente

### Descripción
Permite al usuario dar de baja (desactivar) un cliente del sistema.

### Actor Principal
- Usuario del Sistema (Administrador/Empleado)

### Precondiciones
- El usuario debe estar autenticado
- Debe existir al menos un cliente en el sistema

### Flujo Principal
1. El usuario accede a la opción "Gestionar Clientes"
2. El usuario selecciona "Dar de baja cliente"
3. El sistema muestra la lista de clientes activos o formulario de búsqueda
4. El usuario selecciona el cliente a dar de baja
5. El sistema verifica si el cliente tiene turnos pendientes
6. **Si NO tiene turnos pendientes:**
   - El sistema solicita confirmación de la baja
7. **Si tiene turnos pendientes:**
   - El sistema muestra los turnos pendientes
   - Solicita confirmación mencionando que se cancelarán los turnos
8. El usuario confirma la baja del cliente
9. El sistema desactiva el cliente (baja lógica)
10. Si tenía turnos pendientes, los marca como cancelados
11. El sistema muestra mensaje de confirmación

### Flujos Alternativos
**8a. El usuario cancela:**
- El sistema regresa a la lista de clientes sin realizar cambios

**5a. Cliente con muchos turnos pendientes:**
- El sistema sugiere reagendar antes de dar de baja
- Permite cancelar la operación

### Postcondiciones
- El cliente queda inactivo en el sistema
- Se mantiene el historial del cliente para consultas
- Los turnos pendientes quedan cancelados
- El cliente no aparece en las listas de selección para nuevos turnos

---

## 5. Buscar Cliente

### Descripción
Permite realizar búsquedas específicas de clientes utilizando diferentes criterios.

### Actor Principal
- Usuario del Sistema (Administrador/Empleado)

### Precondiciones
- El usuario debe estar autenticado
- Debe haber clientes registrados en el sistema

### Flujo Principal
1. El usuario accede a la opción "Buscar Cliente"
2. El sistema muestra el formulario de búsqueda con los siguientes campos:
   - Buscar por nombre (parcial o completo)
   - Buscar por teléfono
   - Buscar por email
   - Estado (Activo/Inactivo/Todos)
3. El usuario ingresa uno o más criterios de búsqueda
4. El usuario ejecuta la búsqueda
5. El sistema busca clientes que coincidan con los criterios
6. El sistema muestra los resultados ordenados por relevancia
7. El usuario puede seleccionar un cliente para ver detalles completos

### Flujos Alternativos
**5a. No se encuentran resultados:**
- El sistema muestra mensaje "No se encontraron clientes con esos criterios"
- Sugiere ampliar la búsqueda

**3a. Búsqueda vacía:**
- El sistema muestra mensaje "Ingrese al menos un criterio de búsqueda"
- Regresa al paso 3

### Postcondiciones
- Se muestran los clientes que coinciden con la búsqueda
- El usuario puede acceder a las acciones de cada cliente encontrado

---

## 6. Autoregistro de Cliente

### Descripción
Permite a un cliente registrarse por sí mismo en el sistema para poder solicitar turnos online.

### Actor Principal
- Cliente

### Precondiciones
- El sistema debe tener habilitado el autoregistro
- El cliente debe tener acceso a la interfaz web/móvil

### Flujo Principal
1. El cliente accede a la página de autoregistro
2. El sistema muestra el formulario de registro público
3. El cliente ingresa sus datos:
   - Nombre
   - Apellido
   - Número de teléfono
   - Email
   - Acepta términos y condiciones
4. El sistema valida los datos ingresados
5. El sistema envía un código de verificación al email proporcionado
6. El cliente ingresa el código de verificación
7. El sistema valida el código
8. El sistema registra al cliente con estado "Verificado"
9. El sistema envía email de bienvenida con instrucciones

### Flujos Alternativos
**4a. Email ya registrado:**
- El sistema muestra "Ya existe una cuenta con este email"
- Ofrece opción de recuperar acceso
- Permite usar email diferente

**6a. Código incorrecto:**
- El sistema muestra "Código de verificación incorrecto"
- Permite reintentar (máximo 3 intentos)
- Ofrece opción de reenviar código

**6b. Código expirado:**
- El sistema permite generar nuevo código
- Regresa al paso 5

### Postcondiciones
- El cliente queda registrado y verificado en el sistema
- El cliente puede solicitar turnos online
- Se crea un perfil básico para el cliente
- El cliente recibe credenciales de acceso temporal