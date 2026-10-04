# Cuestionario del libro

## Capitulo 2

### 1. Which of the following data types can be used in a switch expression? (Choose all that apply.)
* A. enum
* B. int
* C. Byte
* E. String
* F. char
* G. var

La expresión switch soporta tipos primitivos enteros menores a 32 bits, dejando fuera a long, double y float. Se permite también los String y var si es de algun tipo permitido.

### 2. What is the output of the following code snippet? (Choose all that apply.)
```
 3: int temperature = 4;
 4: long humidity = -temperature + temperature * 3;
 5: if (temperature>=4)
 6: if (humidity < 6) System.out.println("Too Low");
 7: else System.out.println("Just Right");
 8: else System.out.println("Too High");
```
*  B. Just Right

La operación que evalua humidity da 8. La primera condición (línea 5) se cumple y por lo tanto entra a la siguiente condición la cual da falso y por lo tanto entra al else mas próximo (línea 7).

### 3. Which of the following data types are permitted on the right side of a for-each expression? (Choose all that apply.)
* A. Double[][]
* D. List
* F. char[]
* H. Set

Los foreach admiten listas y arreglos, además el tipo de dato debe ser un iterable.

### 4. What is the output of calling printReptile(6)?
```
 void printReptile(int category) {
 var type = switch(category) {
 case 1,2 -> "Snake";
 case 3,4 -> "Lizard";
 case 5,6 -> "Turtle";
 case 7,8 -> "Alligator";
 };
 System.out.print(type);
 }
```
* F. None of the above

La expresión switch necesita la cláusula default, por lo tanto lanza error de compilación

### 5. What is the output of the following code snippet?
```
 List<Integer> myFavoriteNumbers = new ArrayList<>();
 myFavoriteNumbers.add(10);
 myFavoriteNumbers.add(14);
 for (var a : myFavoriteNumbers) {
 System.out.print(a + ", ");
 break;
 }
 for (int b : myFavoriteNumbers) {
 continue;
 System.out.print(b + ", ");
 }
 for (Object c : myFavoriteNumbers)
 System.out.print(c + ", ");
```
* A. It compiles and runs without issue but does not produce any output.
* B. 10, 14,
* C. 10, 10, 14,
* D. 10, 10, 14, 10, 14,
* E. Exactly one line of code does not compile.
* F. Exactly two lines of code do not compile.
* G. Three or more lines of code do not compile.
* H. The code contains an infinite loop and does not terminate.

El código da error de compilación en el print del segundo for, ya que el continue no está condicionada y siempre es parte del las iteraciones, por lo que siempre se va a saltar el print.

### 6. Which statements about decision structures are true? (Choose all that apply.)
* C. The conditional expression of a for loop is evaluated before the first execution of the
loop body.
* D. A switch expression that takes a String and assigns the result to a variable requires a
default branch.
* E. The body of a do/while loop is guaranteed to be executed at least once.

Los foreach no soportan todas las colecciones como map. Anter de la primera iteración de un for se evalua la condición de la misma. Cuando la expresión switch evalua un string requiere un default. Un do while siempre se ejecuta al menos una vez ya que primero ejecuta el do y despues evalua el while. El if solo puede tener un else.

### 7. Assuming weather is a well-formed nonempty array, which code snippet, when inserted independently into the blank in the following code, prints all of the elements of weather? (Choose all that apply.)
```
 private void print(int[] weather) {
 for( _______ ) {
 System.out.println(weather[i]);
 }
 }
```
* B. int i=0; i<=weather.length-1; ++i
* D. int i=weather.length-1; i>=0; i--

Si i se inicializa con el valor del tamaño de weahter dara problemas ya que el índice empieza en 0. La b es correcta porque se asegura que i tome de 0 hasta el indice igual al número de elementos menos 1. C es incorrecta porque el print llama al elemento por su indice en el arreglo, no la por variable. La D pasa ya que itera de adelante para atras.

### 8. What is the output of calling printType(11)?
```
 31: void printType(Object o) {
 32: if(o instanceof Integer bat) {
 33: System.out.print("int");
 34: } else if(o instanceof Integer bat && bat < 10) {
 35: System.out.print("small int");
 36: } else if(o instanceof Long bat || bat <= 20) {
 37: System.out.print("long");
 38: } default {
 39: System.out.print("unknown");
 40: }
 41: }
```
* G. The code contains two lines that do not compile.

La línea tiene erroes de compilación en la línea 36 y 38, bat aun no ha sido creado formalmente por lo que fallta la segunda expresión del OR, además de que default no existe en la estructura de un if.

### 9. Which statements, when inserted independently into the following blank, will cause the code to print 2 at runtime? (Choose all that apply.)
```
 int count = 0;
 BUNNY: for(int row = 1; row <=3; row++)
 RABBIT: for(int col = 0; col <3 ; col++) {
 if((col + row) % 2 == 0)
 ______;
 count++;
 }
 System.out.println(count);
```
A. break BUNNY
B. break RABBIT
C. continue BUNNY
D. continue RABBIT
E. break
F. continue
G. None of the above, as the code contains a compiler error.

Con la opción A, se rompe el primer for dejaron a count en 1. La opción B es correcta porque porque al estar count en 2, rompe RABBIT pero BUNNY y terminó de iterar. C tambien es correcta, en la tercera iteración de BUNNY count ya está en 1, al iterar una vez  RABBIT, count llega a 2 y en su segunda hace un continue, pasando al print porque BUNNY ya terminó. E es correcto porque está rompiendo a RABBIT.

### 10. Given the following method, how many lines contain compilation errors? (Choose all that apply.)
```
 10: private DayOfWeek getWeekDay(int day, final int thursday) {
 11: int otherDay = day;
 12: int Sunday = 0;
 13: switch(otherDay) {
 14: default:
 15: case 1: continue;
 16: case thursday: return DayOfWeek.THURSDAY;
 17: case 2,10: break;
 18: case Sunday: return DayOfWeek.SUNDAY;
 19: case DayOfWeek.MONDAY: return DayOfWeek.MONDAY;
 20: }
 21: return DayOfWeek.FRIDAY;
 22: }
```
* E. 4

En un switch no se puede usar continue. Para validar con varibles, se deben marcar con final (constantes). Siempre se deben evaluar con valores del mismo tipo.

### 11. What is the output of calling printLocation(Animal.MAMMAL)?
```
 10: class Zoo {
 11: enum Animal {BIRD, FISH, MAMMAL}
 12: void printLocation(Animal a) {
 13: long type = switch(a) {
 14: case BIRD -> 1;
 15: case FISH -> 2;
 16: case MAMMAL -> 3;
 17: default -> 4;
 18: };
 19: System.out.print(type);
 20: } }
```
* A. 3

Se imprime 3, ya que segun el switch, si es MAMMAL se retorna 3.

### 12. What is the result of the following code snippet?
```
 3: int sing = 8, squawk = 2, notes = 0;
 4: while(sing > squawk) {
 5: sing--;
 6: squawk += 2;
 7: notes += sing + squawk;
 8: }
 9: System.out.println(notes);
```
* C. 23

En el primer ciclo notes vale 11 (7 + 4), después se le suma 12 (6 + 6) y no se cumple la siguiente condición. Por lo tanto notes queda en 23.

### 13. What is the output of the following code snippet?
```
 2: boolean keepGoing = true;
 3: int result = 15, meters = 10;
 4: do {
 5: meters--;
 6: if(meters==8) keepGoing = false;
 7: result -= 2;
 8: } while keepGoing;
 9: System.out.println(result);
```
* G. The code does not compile for a different reason.

La condición que evalua el while (línea 8) debe estar dentro de parentesís.

### 14. Which statements about the following code snippet are correct? (Choose all that apply.)
```
 for(var penguin : new int[2])
 System.out.println(penguin);
 var ostrich = new Character[3];
 for(var emu : ostrich)
 System.out.println(emu);
 List<Integer> parrots = new ArrayList<Integer>();
 for(var macaw : parrots)
 System.out.println(macaw);
```
* B. The data type of penguin is int.
* D. The data type of emu is Character.
* F. The data type of macaw is Integer.

En un foreach se iteran listas, arreglas, toda colección iterable, al declarar una variable con var dentro del foreach para cada elemento, el elemento agarra el tipo de dato de esa colección, no la colección.

### 15. What is the result of the following code snippet?
```
 final char a = 'A', e = 'E';
 char grade = 'B';
 switch (grade) {
 default:
 case a:
 case 'B': 'C': System.out.print("great ");
 case 'D': System.out.print("good "); break;
 case e:
 case 'F': System.out.print("not good ");
 }
```

* F. None of the above

Existe error de compilación en el segundo caso, ya que se deben evaluar los casos de manera separada con case.

### 16. Given the following array, which code snippets print the elements in reverse order from how they are declared? (Choose all that apply.)
```
 char[] wolf = {'W', 'e', 'b', 'b', 'y'};
```

* A.

```
 int q = wolf.length;
 for( ; ; ) {
 System.out.print(wolf[--q]);
 if(q==0) break;
 }
```

* B.

```
 for(int m=wolf.length-1; m>=0; --m)
 System.out.print(wolf[m]);
```

* D.

```
 int x = wolf.length-1;
 for(int j=0; x>=0 && j==0; x--)
 System.out.print(wolf[x]);
```

Aunque en la opción A el for es infinito, q va predecrementando al llamar cada elemento de wolf y con una condición rompe el bucle. La opción B inicializa m en el último índice de wolf y lo recorre de manera correcta. La opción C falla desde el primer ciclo, imprimiendo un índice que no existe. La opción D inicia con el último índice y lo recorre de forma correcta. La opción E es un bucle infinito, la variable w jamas cambia y se evalua una variable constante. La opción F también inicia en un índice inexistente.

### 17. What distinct numbers are printed when the following method is executed? (Choose all that apply.)
```
 private void countAttendees() {
 int participants = 4, animals = 2, performers = -1;
 while((participants = participants+1) < 10) {}
 do {} while (animals++ <= 1);
 for( ; performers<2; performers+=2) {}
 System.out.println(participants);
 System.out.println(animals);
 System.out.println(performers);
 }
```
* B. 3
* E. 10

Las variables se incrementan en ciclos while, do whiel y for respectivamente, dando como resultado el valor de 10 en una y 3 en dos de ellas.

### 18. Which statements about pattern matching and flow scoping are correct? (Choose all
that apply.)
* C. Pattern matching with an if statement is implemented using the instanceof operator.
* E. Flow scoping means a pattern variable is only accessible if the compiler can discern its type.

Pattern matching en un if es implementado usando instaceof. No aplica en else ya que este no cuenta con una expresión booleana.

### 19. What is the output of the following code snippet?
```
 2: double iguana = 0;
 3: do {
 4: int snake = 1;
 5: System.out.print(snake++ + " ");
 6: iguana--;
 7: } while (snake <= 5);
 8: System.out.println(iguana);
```
* E. The code does not compile.

La variable snake fue declarado dentro del scope de do while, por lo tanto, da error de compilación en la línea 7 al estar en la condición del while.

### 20. Which statements, when inserted into the following blanks, allow the code to compile and run without entering an infinite loop? (Choose all that apply.)
```
 4: int height = 1;
 5: L1: while(height++ <10) {
 6: long humidity = 12;
 7: L2: do {
 8: if(humidity-- % 12 == 0) ;
 9: int temperature = 30;
 10: L3: for( ; ; ) {
 11: temperature++;
 12: if(temperature>50) ;
 13: }
 14: } while (humidity > 4);
 15: }
```

* A. break L2 on line 8; continue L2 on line 12
* E. continue L2 on line 8; continue L2 on line 12

Hay que omitir usar continue en L3 ya que es un for infinito. Utilizando break en L2 se omite el segundo bucle. Al utilizar continue en L2 tanto en línea 8 como 12, nos ayuda a avanzar en el segundo bucle hasta que termine, evitando así un ciclo infinito en L3.

### 21. A minimum of how many lines need to be corrected before the following method will compile?
```
 21: void findZookeeper(Long id) {
 22: System.out.print(switch(id) {
 23: case 10 -> {"Jane"}
 24: case 20 -> {yield "Lisa";};
 25: case 30 -> "Kelly";
 26: case 30 -> "Sarah";
 27: default -> "Unassigned";
 28: });
 29: }
```
* E. Four

Switch no permite el uso de tipo Long, tampoco se admiten llaves en los cases. No pueden hacer dos casos validando el mismo valor.

### 22. What is the output of the following code snippet? (Choose all that apply.)
```
 2: var tailFeathers = 3;
 3: final var one = 1;
 4: switch (tailFeathers) {
 5: case one: System.out.print(3 + " ");
 6: default: case 3: System.out.print(5 + " ");
 7: }
 8: while (tailFeathers > 1) {
 9: System.out.print(--tailFeathers + " "); }
```
* E. 5 2 1

El 5 viene del print en el case 3 de la sentencia switchm. Después en el while hay un bucle de dos ciclos, donde se imprime 2 y despues 1.

### 23. What is the output of the following code snippet?
```
 15: int penguin = 50, turtle = 75;
 16: boolean older = penguin >= turtle;
 17: if (older = true) System.out.println("Success");
 18: else System.out.println("Failure");
 19: else if(penguin != 50) System.out.println("Other");
```
* F. None of the above

La línea 19 tiene error de compilación ya que es un else if pero antes de él no tiene un if que le corresponda.

### 24. Which of the following are possible data types for friends that would allow the code to compile? (Choose all that apply.)
```
 for(var friend in friends) {
 System.out.println(friend);
 }
```
* G. None of the above

La sintaxis es incorrecta, en vez de in se deben usar los dos puntos (:).

### 25. What is the output of the following code snippet?
```
 6: String instrument = "violin";
 7: final String CELLO = "cello";
 8: String viola = "viola";
 9: int p = -1;
 10: switch(instrument) {
 11: case "bass" : break;
 12: case CELLO : p++;
 13: default: p++;
 14: case "VIOLIN": p++;
 15: case "viola" : ++p; break;
 16: }
 17: System.out.print(p); 
```
* D. 2

Como ningun case se cumple, cae en default incrementando el valor de p, pero como no cuenta con un break, ejecuta los siguientes case sin validar el valor, por lo tanto ejecuta dos incrementos más para p, que corresponden a dos case que se encuentran debajo del default.

### 26. What is the output of the following code snippet? (Choose all that apply.)
```
 9: int w = 0, r = 1;
 10: String name = "";
 11: while(w < 2) {
 12: name += "A";
 13: do {
 14: name += "B";
 15: if(name.length()>0) name += "C";
 16: else break;
 17: } while (r <=1);
 18: r++; w++; }
 19: System.out.println(name);
```
* F. The code compiles but never terminates at runtime.

El código se encontrará con un bucle infinito en el do while ya que este tiene como condición una variable que nunca cambia dentro de su scope y regresa verdadero.

### 27. What is printed by the following code snippet?
```
 23: byte amphibian = 1;
 24: String name = "Frog";
 25: String color = switch(amphibian) {
 26: case 1 -> { yield "Red"; }
 27: case 2 -> { if(name.equals("Frog")) yield "Green"; }
 28: case 3 -> { yield "Purple"; }
 29: default -> throw new RuntimeException();
 30: };
 31: System.out.print(color);
```

* F. The code does not compile.

La línea 27 tiene error de compilación porque solo se retorna un valor si se cumple la condición dentro del bloque del case.

### 28. What is the output of calling getFish("goldie")?
```
 40: void getFish(Object fish) {
 41: if (!(fish instanceof String guppy))
 42: System.out.print("Eat!");
 43: else if (!(fish instanceof String guppy)) {
 44: throw new RuntimeException();
 45: }
 46: System.out.print("Swim!");
 47: }
```
* F. None of the above

Hay error de compilación en la línea 43 (guppy) porque se declara una variable la cual ya habia sido declarada en la línea 41.

### 29. What is the result of the following code?
```
 1: public class PrintIntegers {
 2: public static void main(String[] args) {
 3: int y = -2;
 4: do System.out.print(++y + " ");
 5: while(y <= 5);
 6: } }
```
* C. -1 0 1 2 3 4 5 6

Se declara la varibale y con valor -2, este pasa por un bucle do while, la cual el preincrementada y despues impresa, hasta que no se cumpla que sea menor o igual a 5, imprimiendo del -1 al 6 de forma consecuente.