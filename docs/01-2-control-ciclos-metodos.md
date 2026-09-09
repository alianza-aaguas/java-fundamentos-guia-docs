# 2. Estructuras de control, ciclos y métodos en Java

## Índice

1. [Estructuras de control](#21-estructuras-de-control)
2. [if](#22-if)
3. [if-else](#23-if-else)
4. [if-else if](#24-if-else-if)
5. [switch](#25-switch)
6. [switch expression](#26-switch-expression-java-moderno)
7. [Operador ternario](#27-operador-ternario)
8. [Ciclos](#28-ciclos)
9. [for](#29-for)
10. [foreach](#210-foreach)
11. [while](#211-while)
12. [do-while](#212-do-while)
13. [break](#213-break)
14. [continue](#214-continue)
15. [Métodos](#215-métodos)
16. [Conclusiones y buenas prácticas](#216-conclusiones-y-buenas-prácticas)

---

## 2.1 Estructuras de control

Las estructuras de control permiten que un programa tome decisiones o repita instrucciones según condiciones. Son esenciales para modelar reglas de negocio reales.

### Diagrama conceptual

```text
Entrada -> Evaluación de condición -> Decisión -> Acción
                    |
                    v
                Repetición
```

---

## 2.2 if

### Definición técnica

`if` ejecuta un bloque de código solo cuando una condición booleana es verdadera.

### Definición para una persona no técnica

Es una forma de decir: “si pasa esto, haz esto otro”.

### Caso de uso real

Validar si un cliente puede comprar porque su saldo es suficiente.

### Ventajas

- Muy simple de entender.
- Ideal para una sola condición.
- Es la base de decisiones más complejas.

### Desventajas o consideraciones

- Si crece demasiado, el código se vuelve difícil de leer.
- Puede generar lógica duplicada si no se diseña bien.

### Buenas prácticas

- Mantener la condición simple.
- Extraer reglas complejas a métodos.
- Usar nombres claros en booleanos.

### Errores comunes

- Poner acciones muy grandes dentro del bloque.
- Anidar `if` innecesariamente.

### Ejemplo de código Java

```java
public class IfEjemplo {
    public static void main(String[] args) {
        int edad = 20;

        if (edad >= 18) {
            System.out.println("Puede ingresar");
        }
    }
}
```

### Explicación línea por línea

- `int edad = 20;`: valor que será evaluado.
- `if (edad >= 18)`: verifica si es mayor de edad.
- `println`: se ejecuta solo si la condición es verdadera.

### Pregunta típica de entrevista técnica

¿Cuándo usarías `if` en lugar de `switch`?

### Respuesta esperada de entrevista

`if` se usa cuando las condiciones son booleanas, más flexibles o expresan rangos y comparaciones complejas. `switch` es más adecuado para comparar contra valores discretos.

---

## 2.3 if-else

### Definición técnica

`if-else` permite ejecutar un bloque cuando la condición es verdadera y otro bloque alternativo cuando es falsa.

### Definición para una persona no técnica

Es como decir: “si ocurre esto, haz A; si no, haz B”.

### Caso de uso real

Determinar si una compra tiene envío gratis o no.

### Ventajas

- Da dos caminos claros de ejecución.
- Muy útil para decisiones binarias.

### Desventajas o consideraciones

- Puede crecer en complejidad si se encadena sin criterio.

### Buenas prácticas

- Usarlo cuando realmente existan dos escenarios.
- Mantener ambos bloques equilibrados.

### Errores comunes

- Escribir condiciones que no son mutuamente excluyentes.
- Meter lógica no relacionada dentro del `else`.

### Ejemplo de código Java

```java
public class IfElseEjemplo {
    public static void main(String[] args) {
        double totalCompra = 120.0;

        if (totalCompra >= 100.0) {
            System.out.println("Envío gratis");
        } else {
            System.out.println("Envío con costo");
        }
    }
}
```

### Explicación línea por línea

- `double totalCompra = 120.0;`: define el monto.
- `if (...)`: evalúa el umbral.
- Bloque verdadero: imprime envío gratis.
- `else`: bloque alternativo.
- Bloque falso: imprime envío con costo.

### Pregunta típica de entrevista técnica

¿Qué pasa si la condición del `if` es falsa y no hay `else`?

### Respuesta esperada de entrevista

No se ejecuta ningún bloque y el programa continúa con la siguiente instrucción.

---

## 2.4 if-else if

### Definición técnica

Permite evaluar múltiples condiciones en secuencia hasta que una sea verdadera.

### Definición para una persona no técnica

Es como revisar varias opciones una por una hasta encontrar la correcta.

### Caso de uso real

Clasificar el nivel de descuento según el valor de compra.

### Ventajas

- Representa escalas o rangos con claridad.
- Evita duplicar lógica.

### Desventajas o consideraciones

- Muchas ramas pueden volverlo difícil de mantener.

### Buenas prácticas

- Ordenar de la condición más específica a la más general cuando aplique.
- Evitar cadenas excesivas; considerar estrategia o tabla de reglas.

### Errores comunes

- Dejar una condición imposible al final.
- Repetir comparaciones innecesarias.

### Ejemplo de código Java

```java
public class IfElseIfEjemplo {
    public static void main(String[] args) {
        int puntaje = 82;
        String nivel;

        if (puntaje >= 90) {
            nivel = "Alto";
        } else if (puntaje >= 70) {
            nivel = "Medio";
        } else {
            nivel = "Bajo";
        }

        System.out.println(nivel);
    }
}
```

### Explicación línea por línea

- `int puntaje = 82;`: dato de entrada.
- `String nivel;`: variable de salida.
- Primer `if`: verifica nivel alto.
- `else if`: verifica nivel medio.
- `else`: nivel bajo por defecto.

### Pregunta típica de entrevista técnica

¿Qué problema resuelve `else if`?

### Respuesta esperada de entrevista

Permite evaluar múltiples condiciones mutuamente excluyentes en orden, evitando anidar muchos `if`.

---

## 2.5 switch

### Definición técnica

`switch` selecciona un bloque de ejecución según el valor de una expresión, comparándolo con casos constantes.

### Definición para una persona no técnica

Sirve para elegir una opción entre varias, como un menú.

### Caso de uso real

Mostrar mensajes según el estado de un pedido: `PENDIENTE`, `ENVIADO`, `ENTREGADO`.

### Ventajas

- Más legible que múltiples `if-else` cuando se compara un mismo valor.
- Útil para menús, estados y códigos.

### Desventajas o consideraciones

- Menos flexible que `if` para condiciones complejas.
- En su forma clásica puede requerir `break` para evitar fall-through.

### Buenas prácticas

- Usar `switch` cuando una sola variable decide el flujo.
- Evitar lógica compleja dentro de cada caso.

### Errores comunes

- Olvidar `break` en `switch` clásico.
- Usarlo para rangos o condiciones no discretas.

### Ejemplo de código Java

```java
public class SwitchEjemplo {
    public static void main(String[] args) {
        String estado = "ENVIADO";

        switch (estado) {
            case "PENDIENTE":
                System.out.println("Aún no se procesa");
                break;
            case "ENVIADO":
                System.out.println("El pedido va en camino");
                break;
            case "ENTREGADO":
                System.out.println("Pedido completado");
                break;
            default:
                System.out.println("Estado desconocido");
        }
    }
}
```

### Explicación línea por línea

- `String estado`: valor evaluado.
- `switch (estado)`: inicia el selector.
- Cada `case`: compara un posible valor.
- `break`: evita que continúe con los siguientes casos.
- `default`: maneja valores no esperados.

### Pregunta típica de entrevista técnica

¿Qué ocurre si olvidas `break` en un `switch` clásico?

### Respuesta esperada de entrevista

Se produce fall-through: la ejecución continúa en los casos siguientes hasta encontrar un `break` o terminar el `switch`.

---

## 2.6 switch expression Java moderno

### Definición técnica

`switch expression` permite que `switch` devuelva un valor, usando flechas `->` o bloques con `yield`.

### Definición para una persona no técnica

Es una versión moderna del `switch` que además de elegir una opción, te entrega un resultado.

### Caso de uso real

Calcular el costo de envío según el tipo de cliente.

### Ventajas

- Más conciso.
- Evita fall-through accidental.
- Permite asignar valores de forma limpia.

### Desventajas o consideraciones

- Requiere Java moderno.
- Puede ser menos familiar para desarrolladores nuevos.

### Buenas prácticas

- Usarlo cuando el `switch` produce un valor.
- Mantener casos breves y claros.

### Errores comunes

- Mezclarlo con sintaxis antigua sin criterio.
- No entender cuándo usar `yield`.

### Ejemplo de código Java

```java
public class SwitchExpressionEjemplo {
    public static void main(String[] args) {
        String tipoCliente = "PREMIUM";

        String beneficio = switch (tipoCliente) {
            case "BASICO" -> "Descuento 5%";
            case "PREMIUM" -> "Descuento 15%";
            default -> "Sin descuento";
        };

        System.out.println(beneficio);
    }
}
```

### Explicación línea por línea

- `String tipoCliente`: valor de entrada.
- `String beneficio = switch (...)`: el `switch` retorna un valor.
- `->`: asocia caso con resultado.
- `default`: valor por defecto.
- `println`: imprime el beneficio.

### Pregunta típica de entrevista técnica

¿Cuál es la diferencia principal entre `switch` clásico y `switch expression`?

### Respuesta esperada de entrevista

El clásico ejecuta bloques de instrucciones, mientras que el `switch expression` produce un valor y usa una sintaxis más segura y concisa.

---

## 2.7 Operador ternario

### Definición técnica

Ya se explicó en fundamentos: es una expresión condicional compacta que devuelve un valor según una condición booleana.

### Definición sencilla

Es un `if-else` resumido en una línea.

### Caso de uso real

Elegir un mensaje corto según si un pago fue aprobado o rechazado.

### Buenas prácticas

- Solo para decisiones simples.
- No anidarlo demasiado.

### Ejemplo de código Java

```java
public class TernarioControlEjemplo {
    public static void main(String[] args) {
        int edad = 17;
        String mensaje = edad >= 18 ? "Mayor de edad" : "Menor de edad";
        System.out.println(mensaje);
    }
}
```

### Explicación línea por línea

- `edad >= 18`: condición.
- `? "Mayor de edad"`: valor verdadero.
- `: "Menor de edad"`: valor falso.

### Pregunta típica de entrevista técnica

¿Por qué el operador ternario es una expresión y no una sentencia?

### Respuesta esperada de entrevista

Porque devuelve un valor que puede ser usado en una asignación, retorno o composición de expresiones.

---

## 2.8 Ciclos

Los ciclos repiten instrucciones mientras se cumpla una condición o para cada elemento de una colección.

### Diagrama conceptual

```text
Inicio -> Evaluar -> ¿Sigue? -> Sí -> Repetir
                     |
                     No
                     v
                   Fin
```

---

## 2.9 for

### Definición técnica

`for` ejecuta un bloque un número conocido o controlado de veces mediante inicialización, condición e incremento.

### Caso de uso real

Recorrer las primeras 12 cuotas de un préstamo.

### Ejemplo de código Java

```java
public class ForEjemplo {
    public static void main(String[] args) {
        for (int i = 1; i <= 5; i++) {
            System.out.println("Iteración: " + i);
        }
    }
}
```

### Explicación línea por línea

- `int i = 1`: inicialización.
- `i <= 5`: condición de continuidad.
- `i++`: incremento.

### Pregunta típica de entrevista técnica

¿Cuándo prefieres `for` sobre `while`?

### Respuesta esperada de entrevista

Cuando sabes o controlas claramente cuántas iteraciones vas a realizar.

---

## 2.10 foreach

### Definición técnica

`for-each` recorre cada elemento de un array o colección sin manejar índices explícitos.

### Caso de uso real

Procesar una lista de facturas o nombres de clientes.

### Ejemplo de código Java

```java
public class ForeachEjemplo {
    public static void main(String[] args) {
        String[] productos = {"Mouse", "Teclado", "Monitor"};

        for (String producto : productos) {
            System.out.println(producto);
        }
    }
}
```

### Explicación línea por línea

- `String[] productos`: colección de elementos.
- `for (String producto : productos)`: cada vuelta toma un elemento.

### Pregunta típica de entrevista técnica

¿Cuál es una limitación de `foreach`?

### Respuesta esperada de entrevista

No permite acceder fácilmente al índice ni modificar la colección estructuralmente durante el recorrido.

---

## 2.11 while

### Definición técnica

`while` repite un bloque mientras la condición sea verdadera, evaluando la condición antes de entrar.

### Caso de uso real

Intentar autenticación hasta que el usuario acierte o se agoten los intentos.

### Ejemplo de código Java

```java
public class WhileEjemplo {
    public static void main(String[] args) {
        int contador = 0;

        while (contador < 3) {
            System.out.println("Intento " + contador);
            contador++;
        }
    }
}
```

### Pregunta típica de entrevista técnica

¿Qué ocurre si la condición inicial es falsa?

### Respuesta esperada de entrevista

El bloque no se ejecuta ni una sola vez.

---

## 2.12 do-while

### Definición técnica

`do-while` ejecuta el bloque al menos una vez y luego evalúa la condición.

### Caso de uso real

Mostrar un menú al menos una vez en consola.

### Ejemplo de código Java

```java
public class DoWhileEjemplo {
    public static void main(String[] args) {
        int opcion;
        int contador = 0;

        do {
            System.out.println("Menú mostrado una vez");
            contador++;
        } while (contador < 1);
    }
}
```

### Pregunta típica de entrevista técnica

¿Qué diferencia clave tiene respecto a `while`?

### Respuesta esperada de entrevista

`do-while` ejecuta primero y pregunta después; `while` pregunta primero y, si no se cumple, no entra.

---

## 2.13 break

### Definición técnica

`break` termina inmediatamente un ciclo o `switch`.

### Caso de uso real

Detener una búsqueda cuando se encuentra un producto.

### Ejemplo de código Java

```java
public class BreakEjemplo {
    public static void main(String[] args) {
        for (int i = 1; i <= 10; i++) {
            if (i == 4) {
                break;
            }
            System.out.println(i);
        }
    }
}
```

### Pregunta típica de entrevista técnica

¿Qué diferencia hay entre `break` y `return`?

### Respuesta esperada de entrevista

`break` sale del ciclo o `switch`; `return` sale del método completo.

---

## 2.14 continue

### Definición técnica

`continue` salta la iteración actual y continúa con la siguiente.

### Caso de uso real

Ignorar registros inválidos en un lote de procesamiento.

### Ejemplo de código Java

```java
public class ContinueEjemplo {
    public static void main(String[] args) {
        for (int i = 1; i <= 5; i++) {
            if (i == 3) {
                continue;
            }
            System.out.println(i);
        }
    }
}
```

### Pregunta típica de entrevista técnica

¿Para qué sirve `continue`?

### Respuesta esperada de entrevista

Para saltar la iteración actual y pasar a la siguiente sin terminar el ciclo completo.

---

## 2.15 Métodos

### Definición técnica

Un método es un bloque reutilizable de código que encapsula una operación, puede recibir parámetros y puede devolver un valor.

### Caso de uso real

Calcular impuestos, validar descuentos o formatear reportes.

### Ejemplo de código Java

```java
public class MetodosEjemplo {
    public static void main(String[] args) {
        double total = calcularTotal(100.0, 0.19);
        System.out.println(total);
    }

    static double calcularTotal(double base, double impuesto) {
        return base + (base * impuesto);
    }
}
```

### Explicación línea por línea

- `calcularTotal`: método reutilizable.
- `double base, double impuesto`: parámetros.
- `return ...`: devuelve el resultado.

### Pregunta típica de entrevista técnica

¿Qué ventaja principal tienen los métodos?

### Respuesta esperada de entrevista

Permiten reutilización, encapsulan lógica, mejoran legibilidad y facilitan pruebas y mantenimiento.

---

## 2.16 Conclusiones y buenas prácticas

Las estructuras de control y los métodos transforman datos en decisiones y acciones. Son la base del flujo de cualquier aplicación Java.

### Buenas prácticas generales

- Usa `if` para reglas booleanas y `switch` para valores discretos.
- Prefiere `switch expression` cuando necesitas un valor de salida.
- Usa ciclos claros y evita lógica pesada dentro de cada iteración.
- Extrae comportamiento repetido a métodos.
- Mantén condiciones legibles y cortas.

[Siguiente entrega: POO](./01-3-poo.md)
