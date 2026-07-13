# Agenda de Contactos

Aplicación de consola en Python para gestionar contactos: añadir, buscar y listar. Implementa las operaciones básicas de un CRUD sobre una estructura de datos en memoria.

## Funcionalidades

- **Añadir contacto** — guarda un nombre y su número de teléfono.
- **Buscar contacto** — devuelve el teléfono asociado a un nombre.
- **Listar contactos** — muestra todos los contactos guardados.
- **Salir** — cierra el programa de forma controlada.

## Decisiones de diseño

**Diccionario como almacenamiento.** El nombre es la clave y el teléfono el valor, lo que da una búsqueda directa en O(1) en lugar de recorrer una lista completa.

**Validación de entradas.** Ni el nombre ni el teléfono pueden quedar vacíos. El programa avisa al usuario y vuelve al menú en lugar de guardar un registro corrupto.

**Búsqueda insensible a mayúsculas.** Si la búsqueda directa falla, se compara en minúsculas antes de dar el contacto por inexistente. Así "ana", "Ana" y "ANA" encuentran el mismo contacto — que era el fallo más común al probar el programa.

**Bucle principal con menú.** El programa no termina tras una operación: vuelve al menú hasta que el usuario elige salir explícitamente.

## Cómo ejecutarlo

```bash
python agenda_contactos.py
```

Requiere Python 3. Sin dependencias externas.

## Ejemplo

```
===== MENU PRINCIPAL =====
1. Añadir un contacto
2. Buscar un contacto
3. Listar todos los contactos
4. Salir
Elige una opcion: 1

--- Añadir contacto ---
Nombre: Ana Torres
Numero de telefono: 0414-1234567
Contacto guardado: Ana Torres -> 0414-1234567
```

## Limitaciones conocidas

Los datos se pierden al cerrar el programa (almacenamiento solo en memoria).

## Próximos pasos

- [ ] Persistencia en archivo JSON o base de datos SQLite
- [ ] Editar y eliminar contactos (completar el CRUD)
- [ ] Validación de formato del número de teléfono

## Qué aprendí

Que el código que funciona no es lo mismo que el código que resiste a un usuario real. La mitad de las líneas de este programa existen para manejar lo que pasa cuando alguien escribe algo que no debía.

## Tecnologías

`Python 3` · `Diccionarios` · `CRUD` · `Validación de entradas`

---
Andrés Barros · Estudiante de Ingeniería de Sistemas
