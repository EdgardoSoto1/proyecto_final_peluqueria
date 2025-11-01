# Caso de Uso: Gestión de Usuario

## Actores
- Administrador

## Precondiciones
- Administrador logueado en el sistema

## Requerimientos

### Normal - Dar de Alta Usuario
1. El actor accede al módulo de gestión de usuarios
2. El sistema muestra el menú de opciones de usuario
3. El actor selecciona "Dar de alta usuario"
4. El sistema muestra el formulario con los campos a completar:
   - Nombre de usuario
   - Contraseña
   - Confirmar contraseña
   - Rol (Administrador/Empleado)
5. El actor completa los campos y presiona guardar
6. El sistema verifica que todos los campos estén completos y válidos
7. El sistema registra el nuevo usuario y muestra mensaje de confirmación

### Normal - Modificar Usuario
1. El actor accede al módulo de gestión de usuarios
2. El sistema muestra la lista de usuarios existentes
3. El actor selecciona el usuario a modificar
4. El sistema muestra el formulario con los datos actuales del usuario
5. El actor modifica los campos deseados y presiona guardar
6. El sistema verifica que los datos sean válidos
7. El sistema actualiza la información del usuario

### Normal - Consultar Usuario
1. El actor accede al módulo de gestión de usuarios
2. El sistema muestra la lista completa de usuarios con:
   - Nombre de usuario
   - Rol asignado
   - Estado (Activo/Inactivo)
   - Fecha de creación
3. El actor puede filtrar o buscar usuarios específicos
4. El sistema muestra los resultados de la búsqueda

### Normal - Dar de Baja Usuario
1. El actor accede al módulo de gestión de usuarios
2. El sistema muestra la lista de usuarios activos
3. El actor selecciona el usuario a dar de baja
4. El sistema solicita confirmación de la acción
5. El actor confirma la baja del usuario
6. El sistema desactiva el usuario y muestra mensaje de confirmación

### Alternativo
6.1. En caso de nombre de usuario ya existente, el sistema muestra mensaje "El nombre de usuario ya existe" y vuelve al paso 4
6.2. En caso de contraseñas que no coinciden, el sistema muestra mensaje "Las contraseñas no coinciden" y vuelve al paso 4  
6.3. En caso de contraseña insegura, el sistema muestra los requisitos de seguridad y vuelve al paso 4
3.1. En caso de intento de darse de baja a sí mismo, el sistema muestra mensaje "No puede darse de baja a sí mismo" y regresa al paso 2
5.1. Si el actor cancela la baja, el sistema regresa a la lista sin realizar cambios

## Postcondiciones
- Usuario creado, modificado, consultado o dado de baja según corresponda
- Cambios reflejados en el sistema de autenticación