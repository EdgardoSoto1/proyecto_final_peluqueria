# Gestiones del Sistema de Peluquería

## 1. Gestión de Usuarios

### 1.1 Dar de Alta Usuario
- **Datos requeridos**:
  - Nombre de usuario (único en el sistema)
  - Contraseña (mínimo 8 caracteres)
  - Rol del usuario (Administrador/Empleado)
- **Validaciones**:
  - Verificar unicidad del nombre de usuario
  - Validar fortaleza de contraseña
  - Confirmar contraseña

### 1.2 Modificar Usuario
- **Campos modificables**:
  - Nombre de usuario
  - Contraseña
  - Rol del usuario
  - Estado (Activo/Inactivo)
- **Restricciones**:
  - Un usuario no puede modificar su propio rol
  - Debe mantener al menos un administrador activo

### 1.3 Consultar Usuario
- **Tipos de consulta**:
  - Lista completa de usuarios
  - Búsqueda por nombre de usuario
  - Filtrado por rol y estado
- **Información mostrada**:
  - Nombre de usuario, rol, estado, fecha de creación, último acceso

### 1.4 Dar de Baja Usuario
- **Proceso**:
  - Baja lógica (no se elimina físicamente)
  - Conserva historial para auditoría
  - Previene auto-eliminación del administrador

### 1.5 Autenticación de Usuario
- **Proceso de login**:
  - Validación de credenciales
  - Control de usuarios activos
  - Registro de accesos
  - Manejo de sesiones

---

## 2. Gestión de Clientes

### 2.1 Alta de Cliente
- **Datos requeridos**:
  - Nombre (obligatorio)
  - Apellido (obligatorio)
  - Número de teléfono (obligatorio)
  - Email (obligatorio, único)
- **Datos opcionales**:
  - Observaciones especiales
- **Validaciones**:
  - Formato de email válido
  - Unicidad de email
  - Formato de teléfono correcto

### 2.2 Modificar Cliente
- **Campos modificables**:
  - Nombre y apellido
  - Número de teléfono
  - Email
  - Observaciones
  - Estado (Activo/Inactivo)
- **Validaciones**:
  - Mantener unicidad de email
  - Preservar historial de turnos

### 2.3 Consultar Clientes
- **Tipos de consulta**:
  - Lista completa paginada
  - Búsqueda por nombre, teléfono o email
  - Historial de turnos por cliente
- **Información mostrada**:
  - Datos personales, estado, fecha de registro, cantidad de turnos

### 2.4 Dar de Baja Cliente
- **Proceso**:
  - Verificar turnos pendientes
  - Baja lógica manteniendo historial
  - Cancelación automática de turnos futuros
  - Confirmación del usuario

### 2.5 Búsqueda Avanzada de Clientes
- **Criterios de búsqueda**:
  - Por nombre (parcial o completo)
  - Por teléfono
  - Por email
  - Por estado (Activo/Inactivo)
- **Resultados ordenados por relevancia**

### 2.6 Autoregistro de Cliente
- **Proceso web/móvil**:
  - Formulario público de registro
  - Verificación por email
  - Validación de datos
  - Creación de perfil básico

---

## 3. Gestión de Turnos

### 3.1 Registrar Turno
- **Datos del cliente**:
  - Selección de cliente existente o registro nuevo
  - Nombre y apellido
  - Número de teléfono
  - Email
- **Datos del turno**:
  - Tipo de trabajo (corte, tintura, alisado)
  - Fecha y hora disponible
  - Duración estimada
  - Observaciones especiales
- **Validaciones**:
  - Verificar disponibilidad de horario
  - Validar duración según tipo de trabajo
  - Confirmar datos del cliente

### 3.2 Modificar Turno
- **Campos modificables**:
  - Fecha y hora (si hay disponibilidad)
  - Tipo de trabajo
  - Cliente asignado
  - Observaciones
- **Restricciones**:
  - No solapar con otros turnos
  - Respetar horarios de atención

### 3.3 Anular Turno
- **Proceso**:
  - Selección del turno a cancelar
  - Confirmación de la cancelación
  - Notificación al cliente (opcional)
  - Liberación del horario

### 3.4 Consultar Turnos
- **Tipos de vista**:
  - Lista de turnos por fecha
  - Agenda semanal/mensual
  - Turnos por cliente
  - Turnos por estado (confirmado, cancelado, realizado)

---

## 4. Gestión de Trabajos

### 4.1 Registrar Tipo de Trabajo
- **Datos requeridos**:
  - Nombre del trabajo (único)
  - Duración en minutos
  - Precio del servicio
- **Ejemplos**:
  - Corte: 30 minutos, $500
  - Tintura: 60 minutos, $1200
  - Alisado: 120 minutos, $2000

### 4.2 Modificar Tipo de Trabajo
- **Campos modificables**:
  - Nombre del trabajo
  - Duración en minutos
  - Precio del servicio
  - Estado (Activo/Inactivo)
- **Impacto**:
  - Los cambios afectan solo turnos futuros
  - Los turnos existentes mantienen datos originales

### 4.3 Dar de Baja Trabajo
- **Proceso**:
  - Verificar si hay turnos pendientes con este trabajo
  - Baja lógica del tipo de trabajo
  - Mantener historial para reportes

### 4.4 Consultar Trabajos
- **Información mostrada**:
  - Lista de todos los tipos de trabajo
  - Estado (Activo/Inactivo)
  - Precio y duración actual
  - Cantidad de turnos realizados

---

## Contabilización de Tiempos de los Turnos

Los turnos de los cortes están divididos en un parámetro de horario que va desde las **09:00 hs** hasta las **17:00 hs**.  
Los cortes tienen una duración promedio de **15 minutos**; sin embargo, el cliente prefiere medirlos en **30 minutos** cada corte para tener un tiempo de gracia.

Los turnos de los trabajos técnicos, como tintura, peinado y alisado, se establecen por segmentos de tiempo de **30 minutos**, es decir, desde **30 minutos** hasta **120 minutos** dependiendo del trabajo.  

### Ejemplo:
- Tipo de trabajo: **corte** - duración: **30 minutos**
- Tipo de trabajo: **tintura** - duración: **60 minutos** (dos segmentos de 30 minutos).

---

## Identificación y Fijación de Tiempos de Trabajos Técnicos

Sí, sabemos lo que puede tardar un trabajo, pero es necesario especificar el tipo de trabajo, ya sea tintura, alisado o peinado.

