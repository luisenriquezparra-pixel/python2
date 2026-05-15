# Floats (tipo `float`)

En Python, los floats son números de punto flotante de doble precisión (64 bits, estándar IEEE 754). Representan números decimales con parte fraccionaria.

## 🛠️ Usos principales (todos)

### Generales
- Representar medidas (peso, altura, distancia)
- Calcular porcentajes y promedios
- Operaciones científicas y matemáticas
- Almacenar coordenadas en 2D/3D
- Velocidad, aceleración, tiempo
- Temperaturas y magnitudes físicas
- Divisiones que no son exactas (`10 / 3 = 3.333`)
- Raíces cuadradas y potencias no enteras
- Trigonometría (seno, coseno, tangente)
- Probabilidades y ratios (0.0 a 1.0)
- Interpolación lineal (LERP)
- Umbrales y tolerancias en comparaciones
- Representar monedas (no recomendado por precisión)
- Marcas de tiempo fraccionarias (`time.time()`)
- Escalas y factores de zoom

### Específicos para APIs
- Ratios de caché (0.95 = 95% de aciertos)
- Métricas de rendimiento (95.5 ms de latencia)
- Porcentajes de éxito/error de endpoints
- Umbrales para alerts (CPU > 0.85)
- Probabilidades en A/B testing
- Pesos en modelos de ML (0.1234, -0.5678)
- Puntuaciones de confianza (0.0 a 1.0)
- Tasas de conversión (2.5% → 0.025)
- Versiones semánticas parciales (1.0, 2.5, 3.14)
- Valores de sensores IoT (23.5°C, 101.3 kPa)

### Específicos para juegos
- Posiciones en mundo continuo (x = 123.45, y = 678.90)
- Velocidad del jugador (5.2 unidades/segundo)
- Ángulos de rotación (90.0°, 180.5°)
- Tiempo delta entre frames (0.016 segundos a 60 FPS)
- Interpolación de movimientos (LERP)
- Gravedad (9.81 m/s²)
- Fricción y amortiguamiento (0.98 cada frame)
- Salud del jugador (75.5 de 100 HP)
- Daño con decimales (12.3 de daño por segundo)
- Tamaños de proyectiles (0.5, 1.0, 2.5)
- Opacidad/alpha para transparencias (0.0 a 1.0)
- Volumen de sonido (0.0 = silencio, 1.0 = máximo)
- Tiempo de invencibilidad (1.5 segundos)
- Duración de animaciones (0.25s, 0.5s)
- Zoom de cámara (1.0 normal, 2.0 acercado)

## ⚙️ Operaciones esenciales (todas)

| Operación | Descripción |
|-----------|-------------|
| `+` | Suma |
| `-` | Resta |
| `*` | Multiplicación |
| `/` | División (siempre devuelve `float`) |
| `//` | División entera (devuelve `float` si hay decimales, sino `int`) |
| `%` | Módulo (funciona con floats) |
| `**` | Potencia (devuelve `float` si exponente no entero) |
| `-x` | Negación |
| `+x` | Identidad |
| `abs(x)` | Valor absoluto |
| `round(x, ndigits)` | Redondeo a ndigits decimales |
| `math.floor(x)` | Suelo (entero más grande ≤ x) |
| `math.ceil(x)` | Techo (entero más pequeño ≥ x) |
| `math.trunc(x)` | Truncamiento (elimina decimales) |
| `==`, `!=`, `<`, `<=`, `>`, `>=` | Comparaciones (con precaución por precisión) |
| `math.isclose(a, b, rel_tol, abs_tol)` | Comparación con tolerancia |
| `float(x)` | Conversión a float |

## 🧰 Métodos integrados (todos)

| Método | Descripción | Ejemplo |
|--------|-------------|---------|
| `as_integer_ratio()` | Tupla `(numerador, denominador)` representación exacta | `(3.25).as_integer_ratio()` → `(13, 4)` |
| `is_integer()` | ¿Es un entero? (ej: 3.0 → True, 3.5 → False) | `(5.0).is_integer()` → `True` |
| `hex()` | Representación hexadecimal (para depuración) | `(16.5).hex()` → `"0x1.0800000000000p+4"` |
| `fromhex(s)` | **Método de clase**: crea float desde hexadecimal | `float.fromhex("0x1.08p+4")` → `16.5` |
| `conjugate()` | Conjugado complejo (devuelve el mismo float) | `(3.5).conjugate()` → `3.5` |
| `real` | Propiedad: devuelve el mismo float | `(2.5).real` → `2.5` |
| `imag` | Propiedad: devuelve 0.0 (parte imaginaria) | `(2.5).imag` → `0.0` |
| `numerator` | Propiedad: numerador (no exacto por binario) | `(0.75).numerator` → `3` |
| `denominator` | Propiedad: denominador (no exacto por binario) | `(0.75).denominator` → `4` |

## 📦 Constantes especiales

| Constante        | Descripción                                  |
| ---------------- | -------------------------------------------- |
| `float('inf')`   | Infinito positivo                            |
| `float('-inf')`  | Infinito negativo                            |
| `float('nan')`   | Not a Number (resultado inválido)            |
| `math.inf`       | Infinito (alternativa)                       |
| `math.nan`       | NaN (alternativa)                            |
| `math.pi`        | π = 3.141592653589793                        |
| `math.e`         | e = 2.718281828459045                        |
| `math.tau`       | τ = 6.283185307179586                        |
| `sys.float_info` | Información de precisión (máx, mín, epsilon) |
