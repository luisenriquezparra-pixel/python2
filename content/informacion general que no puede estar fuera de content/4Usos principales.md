# Strings (tipo `str`)

En Python, los strings son secuencias inmutables de caracteres Unicode delimitadas por comillas simples (`'`), dobles (`"`) o triples (`'''` o `"""`).

## 🛠️ Usos principales (todos)

### Generales
- Mostrar mensajes al usuario (`print()`)
- Almacenar datos textuales (nombres, direcciones, emails)
- Leer/escribir archivos de texto
- Formatear cadenas con variables (`f"texto {var}"`)
- Construir consultas SQL o comandos de sistema
- Procesar entrada del usuario (`input()`)
- Representar datos serializados (JSON, XML, CSV)
- Servir como claves en diccionarios
- Almacenar expresiones regulares
- Manejar rutas de archivos y directorios
- Generar claves hash para diccionarios (hashable)
- Almacenar tokens y claves secretas
- Manejar nombres de variables dinámicamente (`globals()[nombre_str]`)
- Evaluar expresiones con `eval()` (peligroso)
- Ejecutar código con `exec()`
- Crear docstrings
- Construir plantillas HTML/XML dinámicas
- Almacenar respuestas de APIs (texto plano)
- Servir como patrón para expresiones regulares (`re.compile()`)
- Representar fechas y horas en formato texto (`strftime`)
- Almacenar configuración en archivos (`.ini`, `.env`, `.yaml`)
- Construir mensajes de log
- Crear nombres de columnas en DataFrames (pandas)
- Guardar consultas a bases de datos (SQL)
- Manejar comandos en sistemas embebidos
- Representar rutas en URLs
- Almacenar datos de formularios web
- Generar reportes en texto plano
- Crear nombres de archivos dinámicamente
- Validar entradas de usuario (con regex)
- Servir como separadores o delimitadores (`"---"`, `"===="`)
- Construir barras de progreso en consola
- Guardar respuestas de modelos de IA

### Específicos para APIs
- Construir URLs endpoints (`f"/api/v1/users/{user_id}"`)
- Formatear JSON manualmente o con `json.dumps()`
- Construir cuerpos de peticiones HTTP
- Parsear respuestas de APIs (`.text`, `.json()`)
- Manejar tokens de autenticación (JWT, Bearer)
- Construir query strings (`"?name={nombre}&age={edad}"`)
- Validar datos de entrada con regex
- Generar logs de peticiones/respuestas
- Crear mensajes de error para respuestas API
- Construir headers HTTP (`{"Authorization": f"Bearer {token}"}`)
- Serializar parámetros de rutas dinámicas
- Manejar webhooks (validar firmas, parsear payloads)
- Formatear fechas ISO 8601
- Construir cuerpos de GraphQL queries
- Generar claves de caché (`f"user:{user_id}:profile"`)

### Específicos para juegos
- Mostrar diálogos de personajes
- Construir menús de opciones
- Formatear puntuaciones y marcadores
- Mostrar mensajes de estado ("Game Over", "Level 3")
- Construir sistemas de diálogos ramificados
- Guardar/leer archivos de guardado (JSON, CSV, texto)
- Manejar comandos de consola (juegos tipo MUD)
- Formatear tablas de clasificación (leaderboards)
- Mostrar estadísticas del jugador (vida, mana, experiencia)
- Construir sistemas de inventario (descripciones de items)
- Manejar chat entre jugadores (multijugador)
- Generar nombres aleatorios de personajes
- Formatear tiempo de juego (`f"{horas:02d}:{minutos:02d}"`)
- Mostrar tooltips y descripciones de objetos
- Construir sistemas de misiones
- Manejar entrada de texto del jugador (comandos, nombres)
- Crear efectos de texto (animaciones con caracteres)
- Formatear diálogos con colores ANSI (juegos de terminal)
- Guardar configuraciones del jugador
- Mostrar mensajes de combate (daño, críticos, curas)

## ⚙️ Operaciones esenciales (todas)

| Operación | Descripción |
|-----------|-------------|
| `+` | Concatenación |
| `*` | Repetición |
| `[]` | Indexación |
| `[:]` | Slicing |
| `in` | Pertenencia |
| `not in` | No pertenencia |
| `==` | Igualdad |
| `!=` | Desigualdad |
| `<`, `<=`, `>`, `>=` | Comparación lexicográfica |
| `len()` | Longitud |
| `for c in s` | Iteración carácter por carácter |
| `%` | Formateo estilo printf (antiguo) |
| `.format()` | Formateo con placeholders |

## 🧰 Métodos integrados (TODOS - 47 métodos en Python 3.12)

### Mayúsculas/minúsculas
| Método | Descripción |
|--------|-------------|
| `capitalize()` | Primera letra mayúscula, resto minúscula |
| `casefold()` | Minúsculas agresivo (para comparaciones) |
| `lower()` | Todo minúsculas |
| `upper()` | Todo mayúsculas |
| `swapcase()` | Invierte mayúsculas/minúsculas |
| `title()` | Cada palabra empieza con mayúscula |

### Búsqueda
| Método | Descripción |
|--------|-------------|
| `find(sub)` | Índice más bajo donde aparece sub, o -1 |
| `rfind(sub)` | Índice más alto donde aparece sub, o -1 |
| `index(sub)` | Igual que find, pero lanza error |
| `rindex(sub)` | Igual que rfind, pero lanza error |
| `count(sub)` | Número de ocurrencias (no superpuestas) |

### Validación (booleanos)
| Método | Descripción |
|--------|-------------|
| `isalnum()` | ¿solo letras y números? |
| `isalpha()` | ¿solo letras? |
| `isascii()` | ¿todos caracteres ASCII? |
| `isdecimal()` | ¿solo dígitos decimales? |
| `isdigit()` | ¿solo dígitos? |
| `isidentifier()` | ¿identificador válido de Python? |
| `islower()` | ¿todo minúsculas? |
| `isnumeric()` | ¿solo caracteres numéricos? |
| `isprintable()` | ¿todos imprimibles? |
| `isspace()` | ¿solo espacios, tabs, saltos de línea? |
| `istitle()` | ¿formato título? |
| `isupper()` | ¿todo mayúsculas? |

### Modificación
| Método | Descripción |
|--------|-------------|
| `replace(old, new)` | Reemplaza todas las ocurrencias |
| `strip()` | Elimina espacios al inicio y final |
| `lstrip()` | Elimina espacios solo al inicio |
| `rstrip()` | Elimina espacios solo al final |
| `removeprefix(prefix)` | Elimina prefijo si existe (Python 3.9+) |
| `removesuffix(suffix)` | Elimina sufijo si existe (Python 3.9+) |

### División y unión
| Método | Descripción |
|--------|-------------|
| `split(sep)` | Divide en lista por separador |
| `rsplit(sep)` | Divide desde la derecha |
| `splitlines()` | Divide por saltos de línea |
| `partition(sep)` | (antes, sep, después) → tupla de 3 |
| `rpartition(sep)` | Igual desde la derecha |
| `join(iterable)` | Une elementos con el string como separador |

### Relleno y alineación
| Método | Descripción |
|--------|-------------|
| `center(width)` | Centra en un ancho dado |
| `ljust(width)` | Alinea a la izquierda |
| `rjust(width)` | Alinea a la derecha |
| `zfill(width)` | Rellena con ceros a la izquierda |
| `expandtabs(tabsize)` | Reemplaza tabs por espacios |

### Codificación
| Método | Descripción |
|--------|-------------|
| `encode(encoding)` | Convierte a bytes |
| `maketrans(x, y, z)` | Crea tabla de traducción |
| `translate(table)` | Traduce usando tabla de maketrans |

### Misceláneos
| Método | Descripción |
|--------|-------------|
| `startswith(prefix)` | ¿empieza con? |
| `endswith(suffix)` | ¿termina con? |
| `format(*args, **kwargs)` | Formateo avanzado |
| `format_map(mapping)` | Format con diccionario |