# Booleanos (tipo `bool`)

En Python, los booleanos representan valores de verdad con dos únicas instancias: `True` (verdadero) y `False` (falso). Son subclase de `int` (`True` == 1, `False` == 0).

## 🛠️ Usos principales (todos)

### Generales
- Controlar flujo de ejecución (`if`, `elif`, `else`)
- Condiciones en bucles (`while condicion`, `for` con `break`)
- Almacenar estados activo/inactivo (encendido/apagado)
- Resultados de comparaciones (`5 > 3` → `True`)
- Flags y banderas en programas
- Validar entrada de usuario
- Controlar visibilidad de elementos en UI
- Habilitar/deshabilitar funcionalidades
- Representar respuestas sí/no
- Control de bucles infinitos con bandera
- Short-circuit evaluation (cortocircuito en `and`/`or`)
- Combinar múltiples condiciones
- Valores por defecto en funciones
- Representar éxito/fallo de operaciones

### Específicos para APIs
- Éxito/fracaso de una petición (`success = True`)
- Estado de autenticación (`is_authenticated`)
- Verificar permisos (`has_permission`)
- Indicar si un recurso existe (`exists`)
- Activar/desactivar endpoints (feature flags)
- Validar tokens (`is_valid`)
- Rate limiting (`is_rate_limited`)
- Cache hit/miss (`cache_hit = True/False`)
- Estado de salud de servicio (`is_healthy`)
- Confirmación de operaciones (`confirmed`)
- Modo debug activado (`debug_mode`)
- SSL/TLS habilitado (`use_ssl`)

### Específicos para juegos
- Jugador vivo o muerto (`is_alive`)
- Puertas abiertas/cerradas (`is_open`)
- Invulnerabilidad activa (`is_invincible`)
- Pausa del juego (`is_paused`)
- Fin del juego (`game_over`)
- Tecla presionada (`key_pressed`)
- Colisión detectada (`collision`)
- Objeto recogido (`collected`)
- Misión completada (`quest_done`)
- Enemigo visible en pantalla (`is_visible`)
- Sonido activado/desactivado (`sound_enabled`)
- Modo oscuro/claro (`dark_mode`)
- Jugador en suelo (`is_grounded`)
- Habilidad disponible (`skill_ready`)
- Diálogo activo (`dialogue_active`)

## ⚙️ Operaciones esenciales (todas)

| Operación | Descripción | Ejemplo |
|-----------|-------------|---------|
| `and` | AND lógico (True si ambos son True) | `True and False` → `False` |
| `or` | OR lógico (True si al menos uno es True) | `True or False` → `True` |
| `not` | NOT lógico (invierte el valor) | `not True` → `False` |
| `==` | Igualdad | `True == True` → `True` |
| `!=` | Desigualdad | `True != False` → `True` |
| `is` | Identidad (misma instancia) | `True is True` → `True` |
| `is not` | No identidad | `True is not False` → `True` |
| `bool(x)` | Conversión a booleano | `bool(5)` → `True` |
| `int(x)` | Conversión a entero | `int(True)` → `1`, `int(False)` → `0` |
| `str(x)` | Conversión a string | `str(True)` → `"True"` |
| `&` | AND bit a bit (funciona pero no recomendado) | `True & False` → `False` |
| `|` | OR bit a bit (funciona pero no recomendado) | `True | False` → `True` |
| `^` | XOR bit a bit | `True ^ True` → `False` |

### Short-circuit evaluation

| Operación | Comportamiento |
|-----------|----------------|
| `x and y` | Si `x` es `False`, devuelve `x`; si no, devuelve `y` |
| `x or y` | Si `x` es `True`, devuelve `x`; si no, devuelve `y` |

## 🧰 Métodos integrados (todos)

> **Nota**: `bool` tiene muy pocos métodos porque es un tipo inmutable y simple. Hereda la mayoría de `int`.

| Método | Descripción | Ejemplo |
|--------|-------------|---------|
| `__bool__()` | Método mágico (no se usa directamente) | `bool(x)` lo llama internamente |
| `__str__()` | Representación string | `str(True)` → `"True"` |
| `__repr__()` | Representación oficial | `repr(True)` → `"True"` |
| `__int__()` | Conversión a entero | `int(True)` → `1` |
| `__and__(other)` | AND (`&`) | `True & False` → `False` |
| `__or__(other)` | OR (`|`) | `True | False` → `True` |
| `__xor__(other)` | XOR (`^`) | `True ^ False` → `True` |
| `__rand__(other)` | AND reflejado | `False & True` llama a `__rand__` |
| `__ror__(other)` | OR reflejado | `False | True` llama a `__ror__` |
| `__rxor__(other)` | XOR reflejado | `False ^ True` llama a `__rxor__` |
| `__invert__()` | NOT bit a bit (`~`) | `~True` → `-2` (cuidado) |

### Métodos heredados de `int` (no suelen usarse con bool)

| Método | Nota |
|--------|------|
| `bit_length()` | Funciona pero no tiene sentido en bool |
| `bit_count()` | Funciona pero no tiene sentido en bool |
| `to_bytes()` | Funciona pero no es práctico |
| `as_integer_ratio()` | Devuelve `(1, 1)` para True, `(0, 1)` para False |
| `conjugate()` | Devuelve el mismo valor |
| `real` | Devuelve el mismo valor |
| `imag` | Devuelve `0` |

## 🔄 Conversiones a bool (valores truthy/falsy)

### Valores que son `False` (falsy)

| Tipo | Valores falsy |
|------|---------------|
| `bool` | `False` |
| `int`, `float` | `0`, `0.0`, `-0` |
| `str` | `""` (string vacío) |
| `list` | `[]` |
| `tuple` | `()` |
| `dict` | `{}` |
| `set` | `set()` |
| `None` | `None` |
| `range` | `range(0)` |
| `decimal.Decimal` | `Decimal(0)` |
| `fractions.Fraction` | `Fraction(0, 1)` |

### Todo lo demás es `True` (truthy)

| Tipo | Ejemplos truthy |
|------|-----------------|
| `int`, `float` | `1`, `-1`, `0.1`, `3.14` |
| `str` | `"0"`, `"False"`, `"hola"` |
| `list` | `[False]`, `[0]`, `[""]` |
| `tuple` | `(None,)` |
| `dict` | `{"key": "value"}` |
| `set` | `{0}` |

## ⚙️ Funciones útiles con booleanos

| Función | Descripción | Ejemplo |
|---------|-------------|---------|
| `all(iterable)` | `True` si TODOS los elementos son truthy | `all([True, True, False])` → `False` |
| `any(iterable)` | `True` si AL MENOS UNO es truthy | `any([False, False, True])` → `True` |
| `bool(x)` | Convierte x a booleano (truthy/falsy) | `bool(0)` → `False` |
| `int(x)` | Convierte bool a int | `int(True)` → `1` |

## 🎯 Comparaciones comunes que devuelven bool

| Operación | Resultado | Ejemplo |
|-----------|-----------|---------|
| `==` | Igualdad | `5 == 5` → `True` |
| `!=` | Desigualdad | `5 != 3` → `True` |
| `<`, `<=`, `>`, `>=` | Comparaciones numéricas | `5 > 3` → `True` |
| `is` | Identidad de objeto | `True is True` → `True` |
| `in` | Pertenencia | `"a" in "hola"` → `True` |
| `isinstance(x, type)` | Verifica tipo | `isinstance(True, bool)` → `True` |

## 💡 Ejemplos de uso en APIs y juegos

### APIs
```python
is_authenticated = token is not None
has_permission = user.role == "admin"
cache_hit = key in cache
success = response.status_code == 200
debug_mode = os.getenv("DEBUG", "false").lower() == "true"