# Caso de Uso: Gestión de Usuario

## 1. Dar de Alta Usuario

### Descripción
Permite al administrador registrar un nuevo usuario en el sistema de la peluquería.

### Actor Principal
- Administrador

### Precondiciones
- El administrador debe estar autenticado en el sistema
- El administrador debe tener permisos para gestionar usuarios

### Flujo Principal
1. El administrador accede a la opción "Gestionar Usuarios"
2. El sistema muestra el formulario de registro de usuario
3. El administrador ingresa los siguientes datos:
   - Nombre de usuario (único en el sistema)
   - Contraseña (mínimo 8 caracteres)
   - Confirmar contraseña
   - Rol del usuario (Administrador/Empleado)
4. El sistema valida que:
   - El nombre de usuario no existe
   - Las contraseñas coinciden
   - La contraseña cumple con los requisitos de seguridad
5. El sistema registra el nuevo usuario
6. El sistema muestra un mensaje de confirmación

### Flujos Alternativos
**4a. Usuario ya existe:**
- El sistema muestra mensaje de error "El nombre de usuario ya existe"
- Regresa al paso 3

**4b. Contraseñas no coinciden:**
- El sistema muestra mensaje "Las contraseñas no coinciden"
- Regresa al paso 3

**4c. Contraseña no cumple requisitos:**
- El sistema muestra mensaje con los requisitos de seguridad
- Regresa al paso 3

### Postcondiciones
- Se crea un nuevo usuario en el sistema
- El usuario puede autenticarse con las credenciales proporcionadas

---

## 2. Modificar Usuario

### Descripción
Permite al administrador modificar los datos de un usuario existente.

### Actor Principal
- Administrador

### Precondiciones
- El administrador debe estar autenticado
- Debe existir al menos un usuario en el sistema

### Flujo Principal
1. El administrador accede a la opción "Gestionar Usuarios"
2. El sistema muestra la lista de usuarios existentes
3. El administrador selecciona el usuario a modificar
4. El sistema muestra el formulario con los datos actuales del usuario
5. El administrador modifica los campos deseados:
   - Nombre de usuario
   - Contraseña (opcional)
   - Rol del usuario
   - Estado (Activo/Inactivo)
6. El sistema valida los datos modificados
7. El sistema actualiza la información del usuario
8. El sistema muestra mensaje de confirmación

### Flujos Alternativos
**6a. Nombre de usuario ya existe:**
- El sistema muestra mensaje de error
- Regresa al paso 5

### Postcondiciones
- Los datos del usuario son actualizados en el sistema

---

## 3. Consultar Usuario

### Descripción
Permite al administrador consultar la información de los usuarios del sistema.

### Actor Principal
- Administrador

### Precondiciones
- El administrador debe estar autenticado

### Flujo Principal
1. El administrador accede a la opción "Consultar Usuarios"
2. El sistema muestra las opciones de consulta:
   - Listar todos los usuarios
   - Buscar usuario específico
3. El administrador selecciona una opción
4. **Si selecciona "Listar todos":**
   - El sistema muestra una lista con todos los usuarios y su información básica
5. **Si selecciona "Buscar específico":**
   - El administrador ingresa el nombre de usuario a buscar
   - El sistema muestra los detalles completos del usuario

### Información Mostrada
- Nombre de usuario
- Rol asignado
- Estado (Activo/Inactivo)
- Fecha de creación
- Último acceso

### Postcondiciones
- Se muestra la información solicitada del usuario o usuarios

---

## 4. Dar de Baja Usuario

### Descripción
Permite al administrador dar de baja (desactivar) un usuario del sistema.

### Actor Principal
- Administrador

### Precondiciones
- El administrador debe estar autenticado
- Debe existir al menos un usuario diferente al administrador

### Flujo Principal
1. El administrador accede a la opción "Gestionar Usuarios"
2. El sistema muestra la lista de usuarios activos
3. El administrador selecciona el usuario a dar de baja
4. El sistema solicita confirmación de la acción
5. El administrador confirma la baja del usuario
6. El sistema desactiva el usuario (baja lógica)
7. El sistema muestra mensaje de confirmación

### Flujos Alternativos
**3a. Intenta dar de baja a sí mismo:**
- El sistema muestra mensaje "No puede darse de baja a sí mismo"
- Regresa al paso 2

**5a. El administrador cancela:**
- El sistema regresa a la lista de usuarios sin realizar cambios

### Postcondiciones
- El usuario queda inactivo en el sistema
- Se mantiene el historial del usuario para auditoría
- El usuario no puede autenticarse en el sistema

---

## 5. Autenticar Usuario

### Descripción
Permite a un usuario acceder al sistema mediante sus credenciales.

### Actor Principal
- Usuario (Administrador/Empleado)

### Precondiciones
- El usuario debe estar registrado y activo en el sistema

### Flujo Principal
1. El usuario accede a la pantalla de login
2. El sistema muestra el formulario de autenticación
3. El usuario ingresa:
   - Nombre de usuario
   - Contraseña
4. El sistema valida las credenciales
5. **Si las credenciales son válidas:**
   - El sistema permite el acceso
   - Redirige al usuario al menú principal según su rol
6. **Si las credenciales son inválidas:**
   - El sistema muestra mensaje de error
   - Regresa al paso 3

### Flujos Alternativos
**4a. Usuario no existe:**
- El sistema muestra "Credenciales inválidas"
- Regresa al paso 3

**4b. Usuario inactivo:**
- El sistema muestra "Usuario deshabilitado"
- Regresa al paso 3

**4c. Contraseña incorrecta:**
- El sistema muestra "Credenciales inválidas"
- Regresa al paso 3

### Postcondiciones
- El usuario queda autenticado en el sistema
- Se registra el acceso en el log del sistema
- El usuario puede acceder a las funcionalidades según su rol