# Cuestionario del libro

## Capitulo 4

### 1. What is output by the following code? (Choose all that apply.)
```
1: public class Fish {
2: public static void main(String[] args) {
3: int numFish = 4;
4: String fishType = "tuna";
5: String anotherFish = numFish + 1;
6: System.out.println(anotherFish + " " + fishType);
7: System.out.println(numFish + " " + 1);
8: } }
```
* F. The code does not compile.

La línea 5 da error de compilación, ya que se está realizando la suma de dos enteros y por lo tanto no se puede asignar el resultado en un String.

### 2. Which of these array declarations are not legal? (Choose all that apply.)
* C. String beans[] = new beans[6];
* E. int[][] types = new int[];
* F. int[][] java = new int[][];

No se puede declara un arreglo con el mismo nombre del tipo de dato o clase. Tampoco se pueden declarar arreglos sin especificar ningún tamaño.

### 3. Note that March 13, 2022 is the weekend when we spring forward, and November 6, 2022 is when we fall back for daylight saving time. Which of the following can fill in the blank without the code throwing an exception? (Choose all that apply.)
```
var zone = ZoneId.of("US/Eastern");
var date = ;
var time = LocalTime.of(2, 15);
var z = ZonedDateTime.of(date, time, zone);
```
* A. LocalDate.of(2022, 3, 13)
* C. LocalDate.of(2022, 11, 6)
* D. LocalDate.of(2022, 11, 7)

Ni la opción B ni E son fechas válidas, no existe el 40 de marzo y el 29 de febrero no aplica en 2023 por no corresponde a año bisiesto. MonthEnum no existe, debe ser Month.

### 4. Which of the following are output by this code? (Choose all that apply.)
```
3: var s = "Hello";
4: var t = new String(s);
5: if ("Hello".equals(s)) System.out.println("one");
6: if (t == s) System.out.println("two");
7: if (t.intern() == s) System.out.println("three");
8: if ("Hello" == s) System.out.println("four");
9: if ("Hello".intern() == t) System.out.println("five");
```
* A. one
* B. two
* C. three
* D. four
* E. five
* F. The code does not compile.
* G. None of the above

Aunque t utiliza el constructor de String mandando s, se realiza un objeto diferente. La primera condición es verdadera, se comparan contenidos. La segunda condición es falsa porque se t y s son objetos diferentes. La tercera condición llama t.intern(), el cual retorna el valor del pool de cadenas, el cual tiene la misma referencia en memoria que s. La siguiente condición es verdadera ya que tienen la misma referencia de memoria. La última condición es falsa, ya que "Hello" esta en el pool de cadenas y t es un objeto diferente que no se encuentra en el pool.

### 5. What is the result of the following code?
```
7: var sb = new StringBuilder();
8: sb.append("aaa").insert(1, "bb").insert(4, "ccc");
9: System.out.println(sb);
```
* B. abbaccca

Se inserta en la posción 1 del string el "bbb", es decir, después de la primera a, el siguiente insert pone "ccc" después del cuarto elemento, la segunda a teniendo encuenta la combinación que hizo el primer insert.

### 6. How many of these lines contain a compiler error? (Choose all that apply.)
```
23: double one = Math.pow(1, 2);
24: int two = Math.round(1.0);
25: float three = Math.random();
26: var doubles = new double[] {one, two, three};
```
* C. 2

Hay errores de compilación en las líneas 24 y 25. Math.round retorna un int si se manda un float, y un long si se manda un double. Math.random retorna double, el cual no se puede asignar a un tipo float.

### 7. Which of these statements is true of the two values? (Choose all that apply.)
```
2022–08–28T05:00 GMT-04:00
2022–08–28T09:00 GMT-06:00
```
* A. The first date/time is earlier.
* E. The date/times are six hours apart.

Al convertir ambas horas a GMT, la primera es 9:00 y la segunda 15:00, por lo tanto la primera es más temprana que la seguna y tienen una diferencia de 6 horas.

### 8. Which of the following return 5 when run independently? (Choose all that apply.)
```
var string = "12345";
var builder = new StringBuilder("12345");
```
* A. builder.charAt(4)
* B. builder.replace(2, 4, "6").charAt(3)
* F. string.replace("123", "1").charAt(2)

Tomar el último índice de un StringBuilder o String (el tamaño menos 1) retorna 5, por lo tanto la A es correcta. La opción B y F también son correctas porque toman el último índice después de hacer el replace.

### 9. Which of the following are true about arrays? (Choose all that apply.)
* A. The first element is index 0.
* C. Arrays are fixed size.
* F. Calling equals() on two different arrays containing the same primitive values always returns false.

El primer elemento de un array siempre es 0, además tienen un tamaño fijo. Utilizar equals para comparar dos arreglos diferentes con los mismos valores devuelve false, ya que equals sirve para comparar igualdad de objetos, no de contenido, y ambos arreglos son objetos diferentes.

### 10. How many of these lines contain a compiler error? (Choose all that apply.)
```
23: int one = Math.min(5, 3);
24: long two = Math.round(5.5);
25: double three = Math.floor(6.6);
26: var doubles = new double[] {one, two, three};
```
* A. 0

No hay errores de compilación. Math.min retorna el mismo tipo de dato que se le manda al igual que floor, round un long si se le manda un double.

### 11. What is the output of the following code?
```
var date = LocalDate.of(2022, 4, 3);
date.plusDays(2);
date.plusHours(3);
System.out.println(date.getYear() + " " + date.getMonth()
 + " " + date.getDayOfMonth());
```
* E. The code does not compile.

Hay error de compilación en la línea 3 porque no existe la función plusHours, de hecho LocalDate no soporta hora, solo fecha.

### 12. What is output by the following code? (Choose all that apply.)
```
var numbers = "012345678".indent(1);
numbers = numbers.stripLeading();
System.out.println(numbers.substring(1, 3));
System.out.println(numbers.substring(7, 7));
System.out.print(numbers.substring(7));
```
* A. 12
* D. 78
* E. A blank line

El primer print toma dos caracteres, 1 y 2 (se encuentran entre los índices 1 y 3). el segundo print no toma ningún carácter por lo que solo da un salto de línea. El tercer print toma los caracteres del índice 7 hasta el último, 7 y 8.

### 13. What is the result of the following code?
```
public class Lion {
 public void roar(String roar1, StringBuilder roar2) {
 roar1.concat("!!!");
 roar2.append("!!!");
 }
 public static void main(String[] args) {
 var roar1 = "roar";
 var roar2 = new StringBuilder("roar");
 new Lion().roar(roar1, roar2);
 System.out.println(roar1 + " " + roar2);
} }
```
* B. roar roar!!!

Un tipo String es inmutable, por lo que ejecutar concat retorna un nuevo String sin cambiar el original. Sin embargo, un StringBuilder es inmutable, por lo la función append añade una cadena a la original. Por lo tanto, la opción B es correcta. 

### 14. Given the following, which can correctly fill in the blank? (Choose all that apply.)
```
var date = LocalDate.now();
var time = LocalTime.now();
var dateTime = LocalDateTime.now();
var zoneId = ZoneId.systemDefault();
var zonedDateTime = ZonedDateTime.of(dateTime, zoneId);
Instant instant = __________;
```
* A. Instant.now()
* F. zonedDateTime.toInstant()

Instant no tiene un constructor público, pero sí existe la función now, que retorna una marca de tiempo del instante en el que se ejecuta. Instant necesita que la marca de tiempo cuente con una fecha, hora y un huso horario.

### 15. What is the output of the following? (Choose all that apply.)
```
var arr = new String[] { "PIG", "pig", "123"};
Arrays.sort(arr);
System.out.println(Arrays.toString(arr));
System.out.println(Arrays.binarySearch(arr, "Pippa"));
```
* C. [123, PIG, pig]
* E. -3

En un ordenamiento, los número van antes que las letras y las mayúsculas antes que las minúsculas. La busqueda binaria determina donde se insertaría un valor, al determinar su lugar, niega el valor y le resta uno.

### 16. What is included in the output of the following code? (Choose all that apply.)
```
var base = "ewe\nsheep\\t";
int length = base.length();
int indent = base.indent(2).length();
int translate = base.translateEscapes().length();
var formatted = "%s %s %s".formatted(length, indent, translate);
System.out.format(formatted);
```
* A. 10
* B. 11
* G. 16

La variable base tiene 11 caracteres, ese valor viene de lenght. La función indent añade dos espacios al inicio de cada línea, por lo que se añaden 4 mas, sin embargo, el método también normaliza añadiendo una nueva línea al final si esta falta. El carácter adicional implica sumar cinco caracteres a los 11 existentes. La función translateEscapes convierte las secuencias de escape de texto en sus caracteres reales correspondientes, en este caso convierte \\\t en \t , por lo que translate se queda con el valor de 10.

### 17. Which of these statements are true? (Choose all that apply.)
```
var letters = new StringBuilder("abcdefg");
```
* A. letters.substring(1, 2) returns a single-character String.
* G. letters.substring(6, 5) throws an exception.

Para hacer un substring se tiene que mandar primero el índice por donde se debe comenzar el recorte y después mandar hasta dónde. Tomar un índice y su consecuente da un String un solo carácter. Si se manda al revés, primero el número mayor, entonces lanzará una excepción. Sí se mandan dos valores iguales se retorna un String vacío.

### 18. What is the result of the following code? (Choose all that apply.)
```
13: String s1 = """
14: purr""";
15: String s2 = "";
16:
17: s1.toUpperCase();
18: s1.trim();
19: s1.substring(1, 3);
20: s1 += "two";
21:
22: s2 += 2;
23: s2 += 'c';
24: s2 += false;
25:
26: if ( s2 == "2cfalse") System.out.println("==");
27: if ( s2.equals("2cfalse")) System.out.println("equals");
28: System.out.println(s1.length());
```
* C. 7
* F. equals

La variable s1 no es afectada por las líneas 17 al 19 porque es un String es inmutable. En la línea 20 se le añaden tres nuevos caracteres, por lo que su tamaño ahora es de 7. El String s2 es iniciado vacío, después en la línea se añade un 2, una c y un false, permitiendo estas operaciones ya que un valor de otro tipo se puede asignar a un string si se concatena con un string. Aunque el string con el que se evalua la igualdad en la línea 26 es la misma que contiene s2, el if da falso porque == compara objetos, y son diferentes objetos. Sin embargo, el siguiente if sí es verdadero porque equals compara los contenidos de los String.

### 19. Which of the following fill in the blank to print a positive integer? (Choose all that apply.)
```
String[] s1 = { "Camel", "Peacock", "Llama"};
String[] s2 = { "Camel", "Llama", "Peacock"};
String[] s3 = { "Camel"};
String[] s4 = { "Camel", null};
System.out.println(Arrays.______ );
```
* A. compare(s1, s2)
* B. mismatch(s1, s2)
* D. mismatch (s3, s4)

La opción A es correcta porque el índice 1 de s1 es mayor alfabeticamente que el índice 1 de s2. Las opciones B y D son correctas porque ambas devuelven un número entero positivo ya que las matrices son diferentes en el índice 1.

### 20. Note that March 13, 2022 is the weekend that clocks spring ahead for daylight saving time.
```
What is the output of the following? (Choose all that apply.)
var date = LocalDate.of(2022, Month.MARCH, 13);
var time = LocalTime.of(1, 30);
var zone = ZoneId.of("US/Eastern");
var dateTime1 = ZonedDateTime.of(date, time, zone);
var dateTime2 = dateTime1.plus(1, ChronoUnit.HOURS);
long diff = ChronoUnit.HOURS.between(dateTime1, dateTime2);
int hour = dateTime2.getHour();
boolean offset = dateTime1.getOffset()
 == dateTime2.getOffset();
System.out.println("diff = " + diff);
System.out.println("hour = " + hour);
System.out.println("offset = " + offset);
```
* A. diff = 1
* D. hour = 3

La primera hora tiene 1:30, mientras que la segunda hora, asignada a hour, tiene 3:30, ya que, al sumar la primera mas una hora se debe tomar en cuenta el adelanto de una hora por el horario de verano, osea se le suma una hora extra de manera explícita. Aun así, la diferencia de hora estrictamente es de 1 hora, ya que ChronoUnit.HOURS.between no cuenta la hora adelantada por el horario de verano.

### 21. Which of the following can fill in the blank to print avaJ? (Choose all that apply.)
```
3: var puzzle = new StringBuilder("Java");
4: puzzle._________ ;
5: System.out.println(puzzle);
```
* A. reverse()
* C. append("vaJ$").delete(0, 3).deleteCharAt(puzzle.length() - 1)

La función reverse invierte los caracteres del StringBuilder, por lo que la opción A es correcta. La C también está bien, ya que primero inserta la cadena "vaJ$", elimina los primeros tres caracteres (Jav) y después elimina el último, dejando "avaJ".  

### 22. What is the output of the following code?
```
var date = LocalDate.of(2022, Month.APRIL, 30);
date.plusDays(2);
date.plusYears(3);
System.out.println(date.getYear() + " " + date.getMonth()
 + " " + date.getDayOfMonth());
```
* A. 2022 APRIL 30

La clase LocalDate es inmutable, por lo tanto, las funciones plusDays y plusYears solo retornan, no modifican a la instancia date. La opción correcta es A porque al no modificarse date, simplemente se imprime la fecha con la que se inicializó.