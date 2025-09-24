# Sistema peluqueria

## 1. Introducción
El propósito del siguiente trabajo es desarrollar un sistema para un negocio dedicado a la peluquería cuyos dueños manifestaron diferentes necesidades para poder optimizar el tiempo de trabajo y gestionar los turnos de los mismos.

Hasta el momento, la modalidad para reservar los turnos se basa en que los clientes reservan los turnos enviando un mensaje a los dueños, previamente preguntándoles la disponibilidad de los horarios y esperando la confirmación del turno dado.

Para confirmar, los dueños llevan un registro de los turnos de corte en un cuaderno que se otorgan de acuerdo a los días y horarios de trabajo del comercio.

En este software, los clientes podrán solicitar los turnos mediante una plataforma online donde se reflejan los tipos de trabajo y horarios disponibles para la reserva.

Los usuarios de la peluquería ingresarán al software y podrán ver los turnos dados de trabajos con los datos de los clientes: nombre y apellido, número de turno, fecha y hora del turno. También podrán reservar turnos, cancelar turnos, agregar tipo de trabajos y duración de los mismos.

---

# Hairdressing Jorge and Verónica

## 2. Abstract
The purpose of this work is to develop an interface for a hairdressing business whose owners have expressed different needs to optimize their working time and manage their appointments.

So far, the method for booking appointments is based on clients reserving appointments by sending a message to the owners, previously asking for the availability of time slots and waiting for confirmation of the given appointment.

To confirm, the owners keep a record of the haircut appointments in a notebook, which are assigned according to the days and hours of operation of the business.

In this software, clients will be able to request appointments through an online platform that reflects the types of services and available times for booking.

The users of the hairdressing salon will log into the software and will be able to see the scheduled appointments with the clients' details, including name, surname, appointment number, date, and time of the appointment. They will also be able to book appointments, cancel appointments, and add types of services and their durations.

---

## 3. Requerimientos

### Gestión de usuario
- Dar de alta usuario con nombre, usuario y contraseña
- Modificar usuario
- Consulta usuario
- Baja usuario 

### Gestión Clientes
- Alta de cliente: nombre, apellido, número de teléfono, email.
- Modificar cliente: nombre, apellido, número de teléfono, email
- Consulta de clientes 
- Baja cliente

### Gestión turno 
- Registrar turno con nombre, apellido, número de teléfono, email. 
- Solicitar el tipo de trabajo: corte, tintura, alisado. 
- Solicitar al cliente la elección de la fecha y hora del turno.
- Anular turno. 
- Mostrar lista de turnos agendados: nombre, cliente, fecha.

### Gestión de trabajos
- Registrar tipo de trabajo: nombre, duración, precio. 
- Modificar tipo de trabajo: nombre, duración, precio. 
- Baja de trabajo.


# 7. Entrevista

## Gestión de Turnos

### ¿Qué datos de los clientes son necesarios para reservar el turno?
Se necesita el nombre y apellido.

### ¿Les importaría pedirles algún dato más a los clientes a fin de poder gestionar mejor los turnos? Por ejemplo, el número de DNI y apellido?
No, solo el nombre, apellido, número de teléfono y email.

### ¿Qué necesitan programar/automatizar en la peluquería?
**Respuesta**: Orden de los turnos, que los clientes respeten el horario, que sepan los precios antes de ir, estandarizar los trabajos, coordinar los turnos de corte con los trabajos técnicos (tintura, permanente, etc.).

### ¿De todos esos, cuál es el más importante?
**Respuesta**: Que los clientes respeten los turnos.

### ¿Les anulan turnos ya programados?
Sí, muchos y con un anticipo sobre la hora.

### ¿Tienen alguna planilla Excel o herramienta que estén implementando?
Sí, tratamos de implementarlo con planilla de cálculo, pero nos es más práctico llevarlo de manera manual (agenda).

### ¿Es posible organizarlo, es decir, desarrollar un programa que los ayude?
Sí, porque la mayoría de los clientes tienen la tecnología como para adaptarse (celular, CPU, etc.) a lo que pidamos.

### ¿Tiene lapsos no productivos solo por los turnos anulados?
Sí, en el caso de que se cancele un turno cercano a la fecha otorgada.

### ¿Tienen servicio de internet?
Sí.

### ¿Con qué hardware cuentan?
Teléfonos móviles.

---

## Gestión de Trabajos

### ¿Cómo se contabilizan los tiempos de los turnos?
Los turnos de los cortes están divididos en un parámetro de horario que va desde las 09:00 hs hasta las 17:00 hs.  
Los cortes tienen una duración promedio de 15 min; el cliente prefiere medirlos en 30 min cada corte para tener un tiempo de gracia.  
Los turnos de los trabajos técnicos, como ser tintura, peinado, alisado, se establecen por segmento de tiempo de 30 minutos, es decir, desde 30 minutos hasta 120 minutos dependiendo del trabajo.  
**Ejemplo**: 
- Tipo de trabajo: corte - duración: 30 minutos
- Tipo de trabajo: tintura - duración: 60 minutos (dos segmentos de 30 minutos).

### ¿Se pueden identificar y fijar los tiempos de los trabajos técnicos?
Sí, sabemos lo que puede tardar un trabajo, pero es necesario especificar el tipo de trabajo, si es tintura, alisado o peinado.

