# Requerimientos

## 1. Gestión de Usuarios
- **Dar de alta usuario**: 
  - Nombre de usuario
  - Contraseña
- **Modificar usuario**
- **Consultar usuario**
- **Dar de baja usuario**

---

## 2. Gestión de Clientes
- **Alta de cliente**: 
  - Nombre
  - Apellido
  - Número de teléfono
  - Email
- **Modificar cliente**: 
  - Nombre
  - Apellido
  - Número de teléfono
  - Email
- **Consultar clientes**
- **Dar de baja cliente**

---

## 3. Gestión de Turnos
- **Registrar turno**: 
  - Nombre
  - Apellido
  - Número de teléfono
  - Email
- **Solicitar tipo de trabajo**: 
  - (corte, tintura, alisado)
- **Solicitar elección de fecha y hora del turno**
- **Anular turno**
- **Mostrar lista de turnos agendados**: 
  - Nombre
  - Cliente
  - Fecha

---

# Gestión de Trabajos

## 1. Registro de Trabajos
- **Registrar tipo de trabajo**: 
  - Nombre
  - Duración
  - Precio

## 2. Modificación de Trabajos
- **Modificar tipo de trabajo**: 
  - Nombre
  - Duración
  - Precio

## 3. Baja de Trabajos
- **Dar de baja trabajo**

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

