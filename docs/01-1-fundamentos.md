# 1. Fundamentos de programación en Java

## Índice

1. [Qué es programar](#11-qué-es-programar)
2. [Algoritmos](#12-algoritmos)
3. [Pseudocódigo](#13-pseudocódigo)
4. [Variables](#14-variables)
5. [Tipos de datos](#15-tipos-de-datos)
6. [Constantes](#16-constantes)
7. [Operadores aritméticos](#17-operadores-aritméticos)
8. [Operadores relacionales](#18-operadores-relacionales)
9. [Operadores lógicos](#19-operadores-lógicos)
10. [Operadores de asignación](#110-operadores-de-asignación)
11. [Operador ternario](#111-operador-ternario)
12. [Tabla comparativa](#112-tabla-comparativa-de-fundamentos)
13. [Conclusiones y buenas prácticas](#113-conclusiones-y-buenas-prácticas)

---

## 1.1 Qué es programar

### 1. Definición técnica

Programar es el proceso de diseñar, escribir, probar, depurar y mantener instrucciones ejecutables por una computadora mediante un lenguaje de programación. En Java, esas instrucciones se escriben en archivos `.java`, se compilan a bytecode y se ejecutan sobre la Java Virtual Machine, JVM.

### 2. Definición para una persona no técnica

Programar es darle instrucciones muy precisas a una computadora, como escribir una receta de cocina donde cada paso debe estar claro para que el resultado salga bien.

### 3. Caso de uso real

En una empresa de e-commerce, programar permite crear el flujo de compra: calcular precios, validar stock, aplicar descuentos, procesar pagos y emitir facturas.

### 4. Ventajas

- Automatiza tareas repetitivas.
- Reduce errores manuales.
- Permite construir productos digitales escalables.
- Facilita el análisis de datos y la toma de decisiones.

### 5. Desventajas o consideraciones

- Requiere precisión: una instrucción incorrecta puede causar errores.
- El código mal diseñado se vuelve costoso de mantener.
- No todo problema se resuelve solo escribiendo código; primero debe entenderse el negocio.

### 6. Buenas prácticas

- Entender el problema antes de codificar.
- Escribir código legible.
- Usar nombres descriptivos.
- Probar los casos normales y los casos límite.
- Mantener funciones pequeñas y enfocadas.

### 7. Errores comunes

- Empezar a codificar sin comprender el requerimiento.
- Copiar código sin entenderlo.
- Usar nombres como `x`, `a`, `dato` sin contexto.
- No probar el programa.

### 8. Ejemplo de código Java

```java
public class ProgramarEjemplo {
    public static void main(String[] args) {
        double precioProducto = 100.0;
        double descuento = 0.15;
        double precioFinal = precioProducto - (precioProducto * descuento);

        System.out.println("Precio final: " + precioFinal);
    }
}
```

### 9. Explicación línea por línea

- `public class ProgramarEjemplo`: declara una clase pública llamada `ProgramarEjemplo`.
- `public static void main(String[] args)`: define el punto de entrada del programa.
- `double precioProducto = 100.0;`: guarda el precio base del producto.
- `double descuento = 0.15;`: representa un descuento del 15%.
- `double precioFinal = ...`: calcula el precio después del descuento.
- `System.out.println(...)`: imprime el resultado en consola.

### 10. Pregunta típica de entrevista técnica

¿Qué significa programar y por qué no basta con escribir código que funcione?

### 11. Respuesta esperada de entrevista

Programar implica resolver problemas mediante instrucciones claras, mantenibles y verificables. No basta con que el código funcione una vez; debe ser entendible, probado, extensible y alineado con las reglas del negocio.

---

## 1.2 Algoritmos

### 1. Definición técnica

Un algoritmo es una secuencia finita, ordenada y no ambigua de pasos que transforma entradas en salidas para resolver un problema.

### 2. Definición para una persona no técnica

Es una receta con pasos exactos para lograr un objetivo, como calcular el total de una compra.

### 3. Caso de uso real

Un banco usa algoritmos para calcular intereses, cuotas de préstamos, riesgo crediticio y límites de crédito.

### 4. Ventajas

- Permiten razonar antes de programar.
- Facilitan detectar errores lógicos.
- Pueden implementarse en distintos lenguajes.
- Ayudan a medir eficiencia.

### 5. Desventajas o consideraciones

- Un algoritmo correcto puede ser ineficiente.
- Si las entradas no están bien definidas, el resultado puede ser incorrecto.
- Puede resolver técnicamente el problema equivocado si no se entiende el negocio.

### 6. Buenas prácticas

- Definir entradas y salidas.
- Considerar casos borde.
- Buscar simplicidad antes que sofisticación.
- Evaluar complejidad temporal y espacial cuando aplique.

### 7. Errores comunes

- Omitir validaciones.
- No contemplar listas vacías o valores nulos.
- Mezclar lógica de negocio con presentación.
- No documentar supuestos importantes.

### 8. Ejemplo de código Java

```java
public class AlgoritmoPromedio {
    public static void main(String[] args) {
        int[] calificaciones = {90, 80, 70};
        int suma = 0;

        for (int calificacion : calificaciones) {
            suma += calificacion;
        }

        double promedio = (double) suma / calificaciones.length;
        System.out.println("Promedio: " + promedio);
    }
}
```

### 9. Explicación línea por línea

- `int[] calificaciones = {90, 80, 70};`: define las entradas del algoritmo.
- `int suma = 0;`: inicializa el acumulador.
- `for (int calificacion : calificaciones)`: recorre cada nota.
- `suma += calificacion;`: acumula cada valor.
- `(double) suma / calificaciones.length`: convierte a decimal y calcula el promedio.
- `System.out.println(...)`: muestra la salida.

### 10. Pregunta típica de entrevista técnica

¿Cuáles son las características de un buen algoritmo?

### 11. Respuesta esperada de entrevista

Debe ser finito, claro, correcto, eficiente, mantenible y debe definir bien sus entradas, salidas y condiciones de error.

---

## 1.3 Pseudocódigo

### 1. Definición técnica

El pseudocódigo es una representación informal y estructurada de un algoritmo, escrita en lenguaje cercano al humano, sin depender estrictamente de la sintaxis de un lenguaje de programación.

### 2. Definición para una persona no técnica

Es un borrador de lo que hará el programa, explicado con pasos fáciles de leer antes de escribir el código real.

### 3. Caso de uso real

Un equipo define primero en pseudocódigo el flujo de aprobación de una solicitud de crédito antes de implementarlo en Java.

### 4. Ventajas

- Facilita la comunicación entre perfiles técnicos y no técnicos.
- Reduce errores antes de programar.
- Permite validar reglas de negocio.
- Sirve como documentación inicial.

### 5. Desventajas o consideraciones

- No se ejecuta.
- Puede ser ambiguo si no está bien escrito.
- No reemplaza pruebas ni código productivo.

### 6. Buenas prácticas

- Mantener pasos claros y numerados.
- Evitar detalles innecesarios de sintaxis.
- Incluir decisiones y repeticiones.
- Validarlo con el usuario de negocio.

### 7. Errores comunes

- Escribir pseudocódigo demasiado parecido a código real sin necesidad.
- Omitir condiciones de error.
- No actualizarlo si cambia la solución.

### 8. Ejemplo de código Java

Pseudocódigo previo:

```text
SI edad es mayor o igual a 18
    mostrar "Puede registrarse"
SI NO
    mostrar "No puede registrarse"
```

Implementación Java:

```java
public class PseudocodigoEjemplo {
    public static void main(String[] args) {
        int edad = 20;

        if (edad >= 18) {
            System.out.println("Puede registrarse");
        } else {
            System.out.println("No puede registrarse");
        }
    }
}
```

### 9. Explicación línea por línea

- `int edad = 20;`: define el dato a evaluar.
- `if (edad >= 18)`: valida la regla de mayoría de edad.
- Primer `println`: salida cuando la regla se cumple.
- `else`: alternativa cuando la condición no se cumple.
- Segundo `println`: salida para menores de edad.

### 10. Pregunta típica de entrevista técnica

¿Para qué sirve el pseudocódigo si no se puede ejecutar?

### 11. Respuesta esperada de entrevista

Sirve para razonar, comunicar y validar la solución antes de implementarla, reduciendo errores de diseño y malentendidos con negocio.

---

## 1.4 Variables

### 1. Definición técnica

Una variable es un identificador asociado a una ubicación de memoria que almacena un valor de un tipo determinado, cuyo contenido puede cambiar durante la ejecución del programa.

### 2. Definición para una persona no técnica

Es una caja con nombre donde guardas información, como el precio de un producto o el nombre de un cliente.

### 3. Caso de uso real

En facturación, variables guardan subtotal, impuestos, descuentos y total final de una factura.

### 4. Ventajas

- Permiten reutilizar datos.
- Mejoran la legibilidad.
- Facilitan cálculos intermedios.
- Hacen el programa dinámico.

### 5. Desventajas o consideraciones

- Variables mutables pueden generar errores si cambian inesperadamente.
- Nombres poco claros dificultan mantenimiento.
- Variables globales o de amplio alcance pueden causar acoplamiento.

### 6. Buenas prácticas

- Usar nombres descriptivos: `totalFactura`, no `tf`.
- Declarar variables cerca de donde se usan.
- Preferir inmutabilidad cuando sea posible.
- Inicializar antes de usar.

### 7. Errores comunes

- No inicializar variables locales.
- Usar tipos incorrectos para dinero, como `double`, en cálculos financieros reales.
- Reutilizar la misma variable para conceptos distintos.

### 8. Ejemplo de código Java

```java
import java.math.BigDecimal;

public class VariablesEjemplo {
    public static void main(String[] args) {
        String cliente = "Ana Pérez";
        BigDecimal subtotal = new BigDecimal("150.00");
        BigDecimal impuesto = new BigDecimal("28.50");
        BigDecimal total = subtotal.add(impuesto);

        System.out.println(cliente + " debe pagar: " + total);
    }
}
```

### 9. Explicación línea por línea

- `import java.math.BigDecimal;`: importa un tipo adecuado para valores monetarios.
- `String cliente`: almacena el nombre del cliente.
- `BigDecimal subtotal`: guarda el importe antes de impuestos.
- `BigDecimal impuesto`: guarda el valor del impuesto.
- `subtotal.add(impuesto)`: suma importes monetarios de forma precisa.
- `System.out.println(...)`: imprime el resumen.

### 10. Pregunta típica de entrevista técnica

¿Cuál es la diferencia entre declarar, inicializar y asignar una variable?

### 11. Respuesta esperada de entrevista

Declarar es definir tipo y nombre; inicializar es darle su primer valor; asignar es colocar o reemplazar un valor en una variable ya declarada.

---

## 1.5 Tipos de datos

### 1. Definición técnica

Un tipo de dato define el conjunto de valores posibles y operaciones válidas sobre una variable. Java tiene tipos primitivos (`int`, `double`, `boolean`, etc.) y tipos de referencia (`String`, clases, arrays, wrappers como `Integer`).

### 2. Definición para una persona no técnica

Es la etiqueta que dice qué puede guardarse en una caja: números, texto, verdadero/falso u objetos más complejos.

### 3. Caso de uso real

Un sistema de inventario usa `int` para cantidades, `String` para códigos de producto, `BigDecimal` para precios y `boolean` para indicar si un producto está activo.

### 4. Ventajas

- Evitan operaciones inválidas.
- Mejoran seguridad en compilación.
- Permiten optimización.
- Expresan intención del código.

### 5. Desventajas o consideraciones

- Elegir mal el tipo puede producir pérdida de precisión.
- Wrappers pueden ser `null` y provocar `NullPointerException`.
- Autoboxing puede impactar rendimiento en bucles intensivos.

### 6. Buenas prácticas

- Usar `BigDecimal` para dinero.
- Usar `long` para identificadores grandes.
- Usar `boolean` para estados binarios claros.
- Evitar conversiones implícitas confusas.

### 7. Errores comunes

- Comparar wrappers con `==`.
- Usar `float` o `double` para dinero.
- Ignorar overflow en `int`.
- Confundir primitivos con objetos.

### 8. Ejemplo de código Java

```java
import java.math.BigDecimal;

public class TiposDatosEjemplo {
    public static void main(String[] args) {
        int cantidad = 3;
        String producto = "Laptop";
        BigDecimal precioUnitario = new BigDecimal("999.99");
        boolean disponible = true;

        BigDecimal total = precioUnitario.multiply(BigDecimal.valueOf(cantidad));
        System.out.println(producto + " disponible: " + disponible);
        System.out.println("Total: " + total);
    }
}
```

### 9. Explicación línea por línea

- `int cantidad = 3;`: cantidad entera de productos.
- `String producto = "Laptop";`: texto con el nombre del producto.
- `BigDecimal precioUnitario`: valor monetario preciso.
- `boolean disponible = true;`: estado lógico.
- `multiply(...)`: multiplica precio por cantidad.
- `println`: muestra datos calculados.

### 10. Pregunta típica de entrevista técnica

¿Cuál es la diferencia entre un tipo primitivo y un wrapper en Java?

### 11. Respuesta esperada de entrevista

Un primitivo almacena directamente el valor y no puede ser `null`. Un wrapper es un objeto que envuelve un primitivo, puede ser `null`, tiene métodos y se usa en colecciones genéricas.

---

## 1.6 Constantes

### 1. Definición técnica

Una constante es un valor que no debe cambiar después de inicializarse. En Java se declara con `final`; las constantes globales suelen declararse como `public static final` y nombrarse en `SCREAMING_SNAKE_CASE`.

### 2. Definición para una persona no técnica

Es un dato fijo, como el porcentaje de IVA definido por ley o el número máximo de intentos permitidos.

### 3. Caso de uso real

Un sistema de autenticación usa una constante `MAX_INTENTOS_LOGIN` para bloquear una cuenta después de varios intentos fallidos.

### 4. Ventajas

- Evitan números mágicos.
- Mejoran legibilidad.
- Centralizan valores relevantes.
- Reducen modificaciones accidentales.

### 5. Desventajas o consideraciones

- No todo valor fijo debe ser constante en código; algunos deben ir en configuración.
- `final` en referencias impide reasignar, pero no siempre hace inmutable el objeto referenciado.

### 6. Buenas prácticas

- Nombrar constantes con `SCREAMING_SNAKE_CASE`.
- Usar constantes para reglas estables.
- Usar configuración para valores que cambian por ambiente.
- Evitar constantes públicas innecesarias.

### 7. Errores comunes

- Usar literales repetidos por todo el código.
- Creer que `final List` hace inmutable la lista.
- Exponer constantes internas de implementación.

### 8. Ejemplo de código Java

```java
public class ConstantesEjemplo {
    private static final int MAX_INTENTOS_LOGIN = 3;

    public static void main(String[] args) {
        int intentosFallidos = 2;
        boolean puedeIntentar = intentosFallidos < MAX_INTENTOS_LOGIN;

        System.out.println("Puede intentar nuevamente: " + puedeIntentar);
    }
}
```

### 9. Explicación línea por línea

- `private static final int MAX_INTENTOS_LOGIN = 3;`: define una constante de clase.
- `int intentosFallidos = 2;`: representa intentos actuales.
- `intentosFallidos < MAX_INTENTOS_LOGIN`: evalúa si aún puede intentar.
- `println`: imprime el resultado booleano.

### 10. Pregunta típica de entrevista técnica

¿Qué diferencia hay entre `final`, `static final` y una constante de configuración?

### 11. Respuesta esperada de entrevista

`final` impide reasignar una variable; `static final` crea una constante asociada a la clase; una constante de configuración puede provenir de archivos, variables de entorno o servicios externos y cambiar sin recompilar.

---

## 1.7 Operadores aritméticos

### 1. Definición técnica

Los operadores aritméticos realizan operaciones matemáticas sobre operandos numéricos: suma `+`, resta `-`, multiplicación `*`, división `/` y módulo `%`.

### 2. Definición para una persona no técnica

Son símbolos para hacer cuentas: sumar, restar, multiplicar, dividir y obtener el residuo de una división.

### 3. Caso de uso real

Calcular el total de productos, el impuesto aplicado, descuentos o el residuo para agrupar elementos en páginas.

### 4. Ventajas

- Sintaxis clara y directa.
- Permiten cálculos esenciales.
- Se combinan con variables y métodos.

### 5. Desventajas o consideraciones

- La división entre enteros descarta decimales.
- Dividir por cero causa error en enteros.
- Puede haber overflow en tipos numéricos.
- `+` también concatena Strings.

### 6. Buenas prácticas

- Usar paréntesis para expresar precedencia.
- Usar `BigDecimal` en dinero.
- Validar divisores.
- Evitar cálculos complejos en una sola línea.

### 7. Errores comunes

- Esperar decimales al dividir dos `int`.
- No validar divisor cero.
- Confundir módulo `%` con porcentaje.

### 8. Ejemplo de código Java

```java
public class OperadoresAritmeticosEjemplo {
    public static void main(String[] args) {
        int unidades = 10;
        int cajas = 3;

        int cajasCompletas = unidades / cajas;
        int unidadesSobrantes = unidades % cajas;

        System.out.println("Cajas completas: " + cajasCompletas);
        System.out.println("Unidades sobrantes: " + unidadesSobrantes);
    }
}
```

### 9. Explicación línea por línea

- `int unidades = 10;`: cantidad total.
- `int cajas = 3;`: cantidad por grupo o divisor.
- `unidades / cajas`: división entera.
- `unidades % cajas`: residuo de la división.
- `println`: muestra los resultados.

### 10. Pregunta típica de entrevista técnica

¿Qué resultado produce `5 / 2` en Java si ambos operandos son `int`?

### 11. Respuesta esperada de entrevista

Produce `2`, porque la división entre enteros descarta la parte decimal. Para obtener `2.5`, al menos un operando debe ser `double` o debe hacerse conversión explícita.

---

## 1.8 Operadores relacionales

### 1. Definición técnica

Los operadores relacionales comparan dos valores y producen un resultado booleano: `==`, `!=`, `>`, `<`, `>=`, `<=`.

### 2. Definición para una persona no técnica

Sirven para hacer preguntas como: ¿son iguales?, ¿uno es mayor?, ¿uno es menor?

### 3. Caso de uso real

Validar si un cliente tiene edad suficiente, si un saldo cubre una compra o si un pedido supera el monto mínimo para envío gratis.

### 4. Ventajas

- Permiten tomar decisiones.
- Son simples y expresivos.
- Se integran con estructuras `if`, `while` y validaciones.

### 5. Desventajas o consideraciones

- `==` compara referencias en objetos, no contenido, salvo primitivos.
- Comparar decimales de punto flotante puede ser impreciso.
- Comparaciones compuestas pueden perder legibilidad.

### 6. Buenas prácticas

- Usar `.equals()` para comparar contenido de objetos.
- Usar `compareTo` para `BigDecimal`.
- Extraer condiciones complejas a métodos con nombres claros.

### 7. Errores comunes

- Usar `==` para comparar Strings.
- Comparar `BigDecimal` con `equals` cuando importa solo el valor numérico.
- No contemplar valores nulos.

### 8. Ejemplo de código Java

```java
import java.math.BigDecimal;

public class OperadoresRelacionalesEjemplo {
    public static void main(String[] args) {
        BigDecimal saldo = new BigDecimal("500.00");
        BigDecimal compra = new BigDecimal("350.00");

        boolean saldoSuficiente = saldo.compareTo(compra) >= 0;
        System.out.println("Saldo suficiente: " + saldoSuficiente);
    }
}
```

### 9. Explicación línea por línea

- `BigDecimal saldo`: representa dinero disponible.
- `BigDecimal compra`: representa costo de la operación.
- `saldo.compareTo(compra) >= 0`: verifica si saldo es mayor o igual a compra.
- `println`: imprime si puede pagar.

### 10. Pregunta típica de entrevista técnica

¿Por qué no es recomendable comparar Strings con `==`?

### 11. Respuesta esperada de entrevista

Porque `==` compara si ambas referencias apuntan al mismo objeto, no si tienen el mismo contenido. Para contenido se usa `.equals()` o `.equalsIgnoreCase()` según el caso.

---

## 1.9 Operadores lógicos

### 1. Definición técnica

Los operadores lógicos combinan expresiones booleanas: AND `&&`, OR `||` y NOT `!`. `&&` y `||` usan evaluación de cortocircuito: si el resultado ya puede determinarse, no evalúan el resto.

### 2. Definición para una persona no técnica

Permiten combinar condiciones: “si es cliente activo y tiene saldo”, “si paga con tarjeta o transferencia”, “si no está bloqueado”.

### 3. Caso de uso real

Validar acceso a una plataforma: usuario activo, contraseña correcta y cuenta no bloqueada.

### 4. Ventajas

- Expresan reglas de negocio compuestas.
- Evitan validaciones anidadas innecesarias.
- El cortocircuito previene errores como acceder a métodos de objetos nulos.

### 5. Desventajas o consideraciones

- Condiciones largas reducen legibilidad.
- El abuso de negaciones dificulta entender reglas.
- El orden importa cuando hay posibles nulos.

### 6. Buenas prácticas

- Colocar validaciones de nulidad antes de usar el objeto.
- Extraer reglas complejas a métodos.
- Evitar expresiones con demasiados operadores mezclados.

### 7. Errores comunes

- Usar `&` en lugar de `&&` sin querer.
- No aprovechar cortocircuito para evitar `NullPointerException`.
- Crear condiciones imposibles o redundantes.

### 8. Ejemplo de código Java

```java
public class OperadoresLogicosEjemplo {
    public static void main(String[] args) {
        String usuario = "ana";
        boolean activo = true;
        boolean bloqueado = false;

        boolean puedeIngresar = usuario != null && activo && !bloqueado;
        System.out.println("Puede ingresar: " + puedeIngresar);
    }
}
```

### 9. Explicación línea por línea

- `String usuario = "ana";`: define el usuario.
- `boolean activo = true;`: indica que la cuenta está activa.
- `boolean bloqueado = false;`: indica que no está bloqueada.
- `usuario != null && activo && !bloqueado`: combina tres reglas.
- `!bloqueado`: niega el estado bloqueado.
- `println`: muestra la autorización.

### 10. Pregunta típica de entrevista técnica

¿Qué es la evaluación de cortocircuito?

### 11. Respuesta esperada de entrevista

Es el comportamiento de `&&` y `||` donde Java deja de evaluar condiciones cuando el resultado final ya está determinado. Por ejemplo, en `obj != null && obj.isActive()`, si `obj` es `null`, no se ejecuta `obj.isActive()`.

---

## 1.10 Operadores de asignación

### 1. Definición técnica

Los operadores de asignación almacenan valores en variables. Incluyen asignación simple `=` y asignaciones compuestas como `+=`, `-=`, `*=`, `/=`, `%=`.

### 2. Definición para una persona no técnica

Son formas de guardar o actualizar el valor de una caja. Por ejemplo: “al total actual súmale 100”.

### 3. Caso de uso real

Actualizar el stock de un producto después de una venta o acumular el total de una factura.

### 4. Ventajas

- Hacen el código más compacto.
- Expresan acumulaciones de manera clara.
- Reducen repetición.

### 5. Desventajas o consideraciones

- Pueden ocultar conversiones implícitas.
- Usados en exceso pueden dificultar lectura.
- En concurrencia, operaciones como `contador++` no son atómicas.

### 6. Buenas prácticas

- Usarlos en acumuladores simples.
- Evitar expresiones con efectos laterales complejos.
- En concurrencia, usar `AtomicInteger` o mecanismos seguros.

### 7. Errores comunes

- Confundir `=` con `==`.
- Creer que `+=` siempre es equivalente exacto a una suma simple con conversión explícita.
- Usar `++` en código concurrente sin sincronización.

### 8. Ejemplo de código Java

```java
public class OperadoresAsignacionEjemplo {
    public static void main(String[] args) {
        int stock = 20;
        int unidadesVendidas = 4;

        stock -= unidadesVendidas;
        stock += 10;

        System.out.println("Stock actualizado: " + stock);
    }
}
```

### 9. Explicación línea por línea

- `int stock = 20;`: stock inicial.
- `int unidadesVendidas = 4;`: unidades retiradas por venta.
- `stock -= unidadesVendidas;`: resta las unidades vendidas.
- `stock += 10;`: suma reposición de inventario.
- `println`: imprime el stock final.

### 10. Pregunta típica de entrevista técnica

¿Cuál es la diferencia entre `=` y `==`?

### 11. Respuesta esperada de entrevista

`=` asigna un valor a una variable. `==` compara dos valores o referencias y devuelve un booleano.

---

## 1.11 Operador ternario

### 1. Definición técnica

El operador ternario `condición ? valorSiVerdadero : valorSiFalso` es una expresión condicional que devuelve un valor según el resultado booleano de una condición.

### 2. Definición para una persona no técnica

Es una forma corta de decir: “si pasa esto, usa este valor; si no, usa este otro”.

### 3. Caso de uso real

Mostrar el estado de un pedido como “Envío gratis” o “Envío con costo” según el monto de compra.

### 4. Ventajas

- Reduce código simple.
- Es útil para asignaciones condicionales.
- Favorece expresiones compactas cuando la regla es clara.

### 5. Desventajas o consideraciones

- Ternarios anidados son difíciles de leer.
- No debe reemplazar lógica compleja.
- Puede disminuir claridad si la condición es larga.

### 6. Buenas prácticas

- Usarlo solo para decisiones simples.
- Evitar anidarlo.
- Mantener condiciones legibles.
- Preferir `if-else` para reglas con varias acciones.

### 7. Errores comunes

- Usarlo para ejecutar efectos secundarios.
- Anidar múltiples ternarios.
- Mezclar tipos incompatibles en las ramas.

### 8. Ejemplo de código Java

```java
public class OperadorTernarioEjemplo {
    public static void main(String[] args) {
        double totalCompra = 120.0;
        String tipoEnvio = totalCompra >= 100.0 ? "Envío gratis" : "Envío con costo";

        System.out.println(tipoEnvio);
    }
}
```

### 9. Explicación línea por línea

- `double totalCompra = 120.0;`: define el monto de la compra.
- `totalCompra >= 100.0`: evalúa si cumple el mínimo.
- `? "Envío gratis"`: valor si la condición es verdadera.
- `: "Envío con costo"`: valor si la condición es falsa.
- `println`: muestra el resultado.

### 10. Pregunta típica de entrevista técnica

¿Cuándo conviene usar el operador ternario y cuándo no?

### 11. Respuesta esperada de entrevista

Conviene usarlo para asignaciones simples basadas en una condición clara. No conviene usarlo para lógica compleja, múltiples condiciones anidadas o acciones con efectos secundarios.

---

## 1.12 Tabla comparativa de fundamentos

| Concepto | Propósito | Ejemplo Java | Riesgo común |
|---|---|---|---|
| Programar | Resolver problemas con instrucciones | `main` | Codificar sin analizar |
| Algoritmo | Definir pasos de solución | `for` para promediar | No contemplar casos borde |
| Pseudocódigo | Diseñar antes de codificar | `SI edad >= 18` | Ambigüedad |
| Variable | Guardar datos cambiantes | `int edad = 20` | Nombres pobres |
| Tipo de dato | Restringir valores y operaciones | `String`, `int` | Tipo incorrecto |
| Constante | Guardar valores fijos | `static final` | Números mágicos |
| Aritméticos | Calcular | `+`, `%` | División entera accidental |
| Relacionales | Comparar | `>=`, `!=` | `==` con objetos |
| Lógicos | Combinar condiciones | `&&`, `||`, `!` | Condiciones ilegibles |
| Asignación | Guardar/actualizar | `+=`, `-=` | Confundir `=` con `==` |
| Ternario | Condición expresiva compacta | `a ? b : c` | Anidarlo demasiado |

## 1.13 Conclusiones y buenas prácticas

Los fundamentos son la base de todo desarrollo Java profesional. Aunque parecen conceptos simples, gran parte de los errores en sistemas reales provienen de decisiones básicas mal tomadas: tipos inadecuados, condiciones confusas, nombres poco descriptivos o cálculos financieros imprecisos.

### Buenas prácticas generales

- Escribe código para humanos primero y para máquinas después.
- Usa nombres que representen conceptos del negocio.
- Evita valores mágicos; usa constantes o configuración.
- Usa `BigDecimal` para dinero.
- Prefiere condiciones claras y extraídas a métodos cuando crecen.
- Comprende la diferencia entre primitivos, objetos y referencias.
- Prueba entradas normales, límites y casos inválidos.

### Diagrama conceptual

```text
Problema real
     |
     v
Análisis del negocio
     |
     v
Algoritmo / pseudocódigo
     |
     v
Código Java
     |
     v
Pruebas y mantenimiento
```

[Siguiente entrega: estructuras de control, ciclos y métodos](./01-2-control-ciclos-metodos.md)
