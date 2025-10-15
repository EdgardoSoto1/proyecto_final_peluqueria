# Caso de Uso: Registrar Trabajo

## Actores
- Usuario

## Precondiciones
- Usuario logueado

## Requerimientos

### Normal
1. El actor selecciona consultar trabajos
2. El sistema muestra los trabajos guardados
3. El actor selecciona agregar trabajo
4. El sistema muestra los campos a completar:
   - Nombre de trabajo
   - Duración 
   - Precio
5. El actor completa los campos y presiona guardar
6. El sistema verifica que todos los campos se hayan cargado y registra el trabajo.

### Alternativo
3.1. En caso de eliminar, el actor selecciona el trabajo y hace click en eliminar trabajo, luego presiona guardar cambios.
3.2. En caso de modificar, el actor se posiciona en el trabajo, modifica los campos y luego presiona guardar cambios.
6.1. En caso de no estar completos los campos, el sistema avisa que no se han completado y vuelve al paso 4.

## Postcondiciones
- Trabajo guardado

