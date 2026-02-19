# 🦆 DuckScript v0.1 (Beta) — Windows Edition

```
 ____             _     ____            _       _
|  _ \ _   _  ___| | __/ ___|  ___ _ __(_)_ __ | |_
| | | | | | |/ __| |/ /\___ \ / __| '__| | '_ \| __|
| |_| | |_| | (__|   <  ___) | (__| |  | | |_) | |_
|____/ \__,_|\___|_|\_\|____/ \___|_|  |_| .__/ \__|
                                          |_|
```

> **"If it looks like Python and quacks like Python... it's DuckScript!"**

DuckScript es un lenguaje de programación compilado en C, diseñado para Windows, con una sintaxis similar a Python pero usando **abreviaciones** para escribir código más rápido y compacto. Extensión de archivo: `.duck`.

---

## 📋 Contenido del paquete

```
duckscript_v0.1/
├── src/
│   ├── duck.h           ← Cabecera principal (tipos, AST, API)
│   ├── duck_lexer.c     ← Analizador léxico (tokenizer)
│   ├── duck_parser.c    ← Parser (genera el AST)
│   ├── duck_value.c     ← Sistema de valores en tiempo de ejecución
│   ├── duck_env.c       ← Entornos y ámbitos de variables
│   ├── duck_interp.c    ← Intérprete tree-walk (motor principal)
│   ├── duck_main.c      ← Punto de entrada, REPL, banner
│   └── build.bat        ← Script de compilación (MinGW)
├── examples/
│   ├── 01_hello.duck       ← Hola Mundo
│   ├── 02_variables.duck   ← Variables y operadores
│   ├── 03_control.duck     ← if/while/for
│   ├── 04_funciones.duck   ← Funciones y recursión
│   ├── 05_listas_dicts.duck← Listas y diccionarios
│   └── 06_avanzado.duck    ← Excepciones, strings, math
├── docs/
│   └── KEYWORD_TABLE.md    ← Tabla completa de palabras clave
└── README.md               ← Este archivo
```

---

## 🔧 Compilación e Instalación (Windows)

### Requisitos
- **MinGW-w64** con `gcc` instalado y en el PATH
  - Descarga: https://winlibs.com/ (recomendado)
  - O desde: https://www.mingw-w64.org/

### Compilar

```batch
cd src
build.bat
```

El ejecutable se genera en: `bin\duck.exe`

Opcionalmente, añade `bin\` a tu PATH de Windows para usar `duck` globalmente.

---

## 🚀 Uso

```batch
:: Modo REPL interactivo
duck.exe

:: Ejecutar un archivo .duck
duck.exe mi_programa.duck

:: Ver ayuda y palabras clave
duck.exe --help

:: Ver versión
duck.exe --version
```

---

## 📝 Sintaxis de DuckScript

### Palabras clave completas

| DuckScript  | Python       | Descripción              |
|-------------|--------------|--------------------------|
| `prn()`      | `print()`    | Imprimir en consola      |
| `inp()`     | `input()`    | Leer entrada del usuario |
| `qk()`      | *(especial)* | Print con emoji 🦆       |
| `iff`       | `if`         | Condicional              |
| `elif`      | `elif`       | Sino si                  |
| `els`       | `else`       | Sino                     |
| `whl`       | `while`      | Bucle while              |
| `fr`        | `for`        | Bucle for                |
| `brk`       | `break`      | Romper bucle             |
| `cnt`       | `continue`   | Continuar bucle          |
| `pass`      | `pass`       | Sin operación            |
| `fn`        | `def`        | Definir función          |
| `ret`       | `return`     | Retornar valor           |
| `lmb`       | `lambda`     | Función lambda           |
| `yld`       | `yield`      | Generador                |
| `try`       | `try`        | Bloque try               |
| `ctch`      | `except`     | Capturar excepción       |
| `fnl`       | `finally`    | Bloque finally           |
| `rse`       | `raise`      | Lanzar excepción         |
| `imp`       | `import`     | Importar                 |
| `frm`       | `from`       | Importar desde           |
| `nd`        | `and`        | Y lógico                 |
| `or`        | `or`         | O lógico                 |
| `nt`        | `not`        | No lógico                |
| `in`        | `in`         | Pertenencia              |
| `tru`       | `True`       | Verdadero                |
| `fls`       | `False`      | Falso                    |
| `nul`       | `None`       | Nulo                     |

### Funciones Built-in

| DuckScript       | Python          | Descripción            |
|-----------------|-----------------|------------------------|
| `len(x)`        | `len(x)`        | Longitud               |
| `rng(a,b,s)`    | `range(a,b,s)`  | Rango numérico         |
| `str(x)`        | `str(x)`        | Convertir a string     |
| `int(x)`        | `int(x)`        | Convertir a entero     |
| `flt(x)`        | `float(x)`      | Convertir a decimal    |
| `typ(x)`        | `type(x)`       | Tipo del valor         |
| `abs(x)`        | `abs(x)`        | Valor absoluto         |
| `mx(x)`         | `max(x)`        | Máximo                 |
| `mn(x)`         | `min(x)`        | Mínimo                 |
| `sm(x)`         | `sum(x)`        | Suma de lista          |
| `sqr(x)`        | `math.sqrt(x)`  | Raíz cuadrada          |
| `flr(x)`        | `math.floor(x)` | Redondeo hacia abajo   |
| `cil(x)`        | `math.ceil(x)`  | Redondeo hacia arriba  |
| `rnd(x,n)`      | `round(x,n)`    | Redondear              |
| `rndi(a,b)`     | `random.randint`| Entero aleatorio a..b  |

### Métodos de String

| DuckScript       | Python           |
|-----------------|------------------|
| `.uppr()`       | `.upper()`       |
| `.lwr()`        | `.lower()`       |
| `.strp()`       | `.strip()`       |
| `.splt(sep)`    | `.split(sep)`    |
| `.rpl(a,b)`     | `.replace(a,b)`  |
| `.fnd(sub)`     | `.find(sub)`     |

### Métodos de Lista

| DuckScript       | Python           |
|-----------------|------------------|
| `.app(item)`    | `.append(item)`  |
| `.pop()`        | `.pop()`         |
| `.srt()`        | `.sort()`        |
| `.rvs()`        | `.reverse()`     |
| `.jn(sep)`      | `sep.join(list)` |

### Métodos de Diccionario

| DuckScript       | Python           |
|-----------------|------------------|
| `.ks()`         | `.keys()`        |
| `.vls()`        | `.values()`      |
| `.gt(key)`      | `.get(key)`      |

---

## 💡 Ejemplos de código

### Hola Mundo
```duck
prn("Hola desde DuckScript!")
qk("Con emoji de pato!")
```

### Variables
```duck
nombre = "DuckScript"
version = 0.1
activo = tru
nada = nul
```

### Condicional
```duck
edad = 20
iff edad >= 18:
    pr("Mayor de edad")
elif edad >= 16:
    pr("Casi!")
els:
    pr("Menor de edad")
```

### Bucle for
```duck
fr i in rng(1, 6):
    pr("Numero:", i)
```

### Bucle while
```duck
x = 0
whl x < 5:
    x += 1
    pr("x =", x)
```

### Funciones
```duck
fn potencia(base, exp):
    ret base ** exp

prn(potencia(2, 10))
```

### Recursión
```duck
fn fibonacci(n):
    iff n <= 1:
        ret n
    ret fibonacci(n - 1) + fibonacci(n - 2)

fr i in rng(10):
    pr(fibonacci(i))
```

### Listas
```duck
nums = [1, 2, 3, 4, 5]
nums.app(6)
nums.srt()
prn("Max:", mx(nums))
prn("Sum:", sm(nums))
```

### Diccionarios
```duck
pato = {"nombre": "Donald", "edad": 34}
prn(pato["nombre"])
prn(pato.gt("edad"))
fr k in pato.ks():
    pr(k, ":", pato.gt(k))
```

### Manejo de errores
```duck
try:
    x = 10 / 0
ctch:
    pr("Error capturado!")
fnl:
    pr("Siempre se ejecuta.")
```

### Strings
```duck
s = "  Hola DuckScript!  "
prn(s.strp().uppr())
prn(s.strp().splt(" "))
prn(s.strp().rpl("DuckScript", "Mundo"))
```

---

## 🏗️ Arquitectura

DuckScript es un **intérprete tree-walk** implementado completamente en C:

```
Código .duck
     │
     ▼
┌─────────────┐
│  Lexer      │  duck_lexer.c  → Convierte texto en tokens
└─────────────┘
     │
     ▼
┌─────────────┐
│  Parser     │  duck_parser.c → Construye el AST
└─────────────┘
     │  (Abstract Syntax Tree)
     ▼
┌─────────────┐
│ Interpreter │  duck_interp.c → Evalúa el AST nodo a nodo
└─────────────┘
     │
     ▼
  Resultado en consola
```

**Componentes:**
- `duck_lexer.c` — Análisis léxico, manejo de indentación (INDENT/DEDENT)
- `duck_parser.c` — Parser recursivo descendente, genera AST completo
- `duck_value.c` — Sistema de tipos dinámicos (int, float, str, bool, null, list, dict, fn)
- `duck_env.c` — Entornos anidados con soporte para closures
- `duck_interp.c` — Intérprete con más de 40 nodos de AST soportados
- `duck_main.c` — REPL con colores ANSI, historial, banner ASCII

---

## 🛣️ Roadmap

| Versión | Características planificadas |
|---------|------------------------------|
| **v0.1** | ✅ Core del lenguaje, REPL, funciones, listas, dicts |
| **v0.2** | Clases (cls), herencia, métodos en objetos |
| **v0.3** | Módulo estándar `ducklib` (io, math, web) |
| **v0.4** | Closures completos, lambdas, generadores |
| **v0.5** | Sistema de módulos `.duck` importables |
| **v1.0** | Compilador a bytecode + VM propia |

---



*"Code like a duck: calm on the surface, paddling like crazy underneath."*

