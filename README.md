                                                   /***** First *****/

        VS Code provides the workspace and terminal, while JShell is useful for trying short Java expressions; a full Java program goes in a .java file and can be compiled with javac and run with java.


## Data Types in Java

Java is **statically typed** — every variable must be declared with a type before use. Types split into two families: **primitive** (8 built-in types) and **non-primitive / reference** (classes, interfaces, arrays, enums).

### Primitive Data Types (8 total)

| Type | Size | Default | Range / Notes |
|------|------|---------|---------------|
| `byte` | 1 byte (8-bit) | 0 | −128 to 127 |
| `short` | 2 bytes (16-bit) | 0 | −32,768 to 32,767 |
| `int` | 4 bytes (32-bit) | 0 | −2³¹ to 2³¹−1 |
| `long` | 8 bytes (64-bit) | 0L | −2⁶³ to 2⁶³−1 (suffix `L`) |
| `float` | 4 bytes (32-bit) | 0.0f | ~7 significant digits (suffix `f`) |
| `double` | 8 bytes (64-bit) | 0.0d | ~15 significant digits; default for decimals |
| `char` | 2 bytes (16-bit) | '\u0000' | Single Unicode character, 0–65,535 |
| `boolean` | JVM-dependent | false | Only `true` or `false` |

Primitives are grouped as **integral** (`byte, short, int, long, char`) and **floating-point** (`float, double`). `char` is the only unsigned type.

**Example:**
```java
int age = 25;
long population = 8_000_000_000L;
float price = 19.99f;
double pi = 3.14159;
char grade = 'A';
boolean isActive = true;
```

### Non-Primitive / Reference Types

These store a **reference** (memory address), not the value itself. Examples: `String`, arrays, classes, interfaces. Their default value is `null`.

```java
String name = "Alice";
int[] scores = {90, 85, 77};
```

### Key Concepts Worth Highlighting

**1. Type Conversion.** *Widening* (automatic, safe): `byte → short → int → long → float → double`. *Narrowing* requires an explicit cast and may lose data:
```java
int i = 100;
byte b = (byte) i;   // explicit cast
double d = 9.78;
int x = (int) d;     // x = 9, fractional part lost
```

**2. Integer overflow.** Arithmetic that exceeds a type's range wraps around silently:
```java
int max = Integer.MAX_VALUE;   // 2147483647
System.out.println(max + 1);   // -2147483648 (overflow)
```

**3. Floating-point precision.** Use `BigDecimal` for money:
```java
System.out.println(0.1 + 0.2);   // 0.30000000000000004
```

**4. Literals.** Hex `0x1F`, binary `0b1010`, octal `017`, underscores for readability `1_000_000`.

**5. Wrapper classes.** Each primitive has a wrapper (`Integer`, `Double`, `Character`…) enabling use in collections; autoboxing converts automatically:
```java
Integer boxed = 42;   // autoboxing
int unboxed = boxed;  // unboxing
```

**6. `char` and Unicode.** `char` holds a UTF-16 code unit; `'A'` is `65`. Strings are immutable reference types.

If your video used different emphasis (e.g., memory layout, `var` inference, or a specific slide deck), share the transcript or re-upload the file and I'll align the summary exactly to it.