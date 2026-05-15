# Integers (tipo `int`)

En Python, los enteros son números sin parte fraccionaria, de precisión arbitraria (tamaño ilimitado). Se representan en decimal, binario (`0b`), octal (`0o`) o hexadecimal (`0x`).

## 🛠️ Usos principales (todos)

### Generales
- Contar elementos (`len()`, bucles `for`)
- Indexar secuencias (`lista[3]`, `texto[0]`)
- Controlar bucles (`range()`, `while`)
- Realizar operaciones matemáticas
- Almacenar edades, cantidades, IDs numéricos
- Recibir entrada numérica del usuario (`int(input())`)
- Usar como flags o códigos de estado
- Representar coordenadas (x, y, z)
- Controlar el flujo con condiciones (`if numero > 0`)
- Generar números aleatorios (`random.randint()`)
- Trabajar con módulo y división entera (`//`, `%`)
- Máscaras de bits y operaciones binarias (`&`, `|`, `^`, `<<`, `>>`)
- Definir tamaños de buffers o arrays
- Representar constantes (`MAX_INT`, `TIMEOUT`)
- Calcular hashes y checksums

### Específicos para APIs
- Códigos de estado HTTP (200, 404, 500)
- IDs de usuarios, productos, pedidos
- Límites de paginación (`?page=1&limit=10`)
- Timestamps UNIX (`time.time()` → entero)
- Puertos de red (80, 443, 8080)
- Timeouts en segundos
- Número de reintentos (retries)
- Versiones de API (v1, v2, v3)
- Códigos de error personalizados
- Límites de rate limiting (100 peticiones/hora)
- Tamaños de lotes (batch sizes)
- Prioridades de colas (1 alta, 5 baja)

### Específicos para juegos
- Puntuaciones y puntos de experiencia
- Niveles del jugador (1, 2, 3...)
- Cantidad de vidas, mana, energía
- Daño de armas y defensa
- Posiciones en grid/mapa (x, y)
- Velocidad de movimiento (píxeles/frame)
- Frame rate (FPS)
- Semillas para generación procedural (`random.seed(42)`)
- Número de enemigos en pantalla
- Tiempo de cooldown de habilidades
- Inventario (cantidad de objetos, pociones)
- Monedas, oro, puntos de tienda
- Duración de efectos (3 segundos congelado)
- Número de jugadores (1-4 en local)
- Distancias entre objetos
- Identificadores de sprites o animaciones

## ⚙️ Operaciones esenciales (todas)

| Operación | Descripción |
|-----------|-------------|
| `+` | Suma |
| `-` | Resta |
| `*` | Multiplicación |
| `/` | División flotante (devuelve `float`) |
| `//` | División entera (suelo) |
| `%` | Módulo (resto) |
| `**` | Potencia |
| `-x` | Negación |
| `+x` | Identidad |
| `abs(x)` | Valor absoluto |
| `pow(x, y, mod)` | Potencia con módulo opcional |
| `divmod(x, y)` | Tupla `(cociente, resto)` |
| `==` | Igualdad |
| `!=` | Desigualdad |
| `<`, `<=`, `>`, `>=` | Comparaciones |
| `&` | AND bit a bit |
| `|` | OR bit a bit |
| `^` | XOR bit a bit |
| `~` | NOT bit a bit (complemento) |
| `<<` | Desplazamiento izquierda |
| `>>` | Desplazamiento derecha |
| `int(x)` | Conversión a entero |
| `int(x, base)` | Desde string en base especificada |

## 🧰 Métodos integrados (TODOS)

> **Nota**: `int` tiene pocos métodos porque es un tipo inmutable y numérico. Los siguientes son TODOS los métodos disponibles.

### Métodos de instancia

| Método | Descripción |
|--------|-------------|
| `bit_length()` | Número de bits necesarios para representar el entero (sin signo) |
| `bit_count()` | Número de unos en representación binaria (Python 3.8+) |
| `to_bytes(length, byteorder, signed)` | Convierte entero a bytes |
| `from_bytes(bytes, byteorder, signed)` | **Método de clase**: convierte bytes a entero |
| `as_integer_ratio()` | Tupla `(numerador, denominador)` (denominador siempre 1) |
| `conjugate()` | Conjugado complejo (devuelve el mismo entero) |
| `real` | Propiedad: devuelve el mismo entero |
| `imag` | Propiedad: devuelve 0 (parte imaginaria) |
| `numerator` | Propiedad: devuelve el mismo entero |
| `denominator` | Propiedad: devuelve 1 |
| `__add__()`, `__sub__()`, etc. | Métodos mágicos (no se usan directamente) |

### Métodos de clase útiles (no son de instancia)

| Método | Descripción | Ejemplo |
|--------|-------------|---------|
| `int.from_bytes()` | Convierte bytes a entero | `int.from_bytes(b'\x01', 'big')` |
| `int.from_string()` | No existe; usar `int("10", base)` | `int("FF", 16)` |

### Métodos de instancia para números (heredados de `object`)

| Método | Descripción |
|--------|-------------|
| `__bool__()` | Devuelve `False` si es 0, `True` si no |
| `__str__()` | Representación en decimal (`"42"`) |
| `__repr__()` | Representación oficial (`"42"`) |
| `__format__(format_spec)` | Formateo con f-strings o `format()` |

## 🔢 Conversiones útiles (no son métodos pero esenciales)

| Función | Descripción |
|---------|-------------|
| `bin(x)` | String binario (`"0b1010"`) |
| `oct(x)` | String octal (`"0o12"`) |
| `hex(x)` | String hexadecimal (`"0xa"`) |
| `chr(x)` | Carácter Unicode correspondiente (65 → `"A"`) |

## ✅ Métodos totales

**`int` tiene 9 métodos de instancia documentados** (`bit_length`, `bit_count`, `to_bytes`, `from_bytes`, `as_integer_ratio`, `conjugate`, `real`, `imag`, `numerator`, `denominator` - algunos son propiedades). 

Los métodos mágicos (`__add__`, etc.) existen pero **no se usan directamente en código normal**.