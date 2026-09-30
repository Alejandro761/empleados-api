# Cuestionario del libro

## Capitulo 2

### 1. Which of the following Java operators can be used with boolean variables? (Choose all that apply.)
* A. ==
* D. !
* G. Cast with (boolean)

Tanto == como ! son operadores de comparación para datos primitivos como boolean.

### 2. What data type (or types) will allow the following code snippet to compile? (Choose all that apply.)
```
byte apples = 5;
short oranges = 10;
_____ bananas = apples + oranges;
```
* A. int
* B. long
* D. double

El tipo boolean solo puede ser true o false, no un número. Al asignar a una variable la suma de un byte y short , automaticamente es un int , por lo tanto puede ser int o long.

### 3. What change, when applied independently, would allow the following code snippet to  compile? (Choose all that apply.)
```
3: long ear = 10;
4: int hearing = 2 * ear;
```
* B. Cast ear on line 4 to int.
* C. Change the data type of ear on line 3 to short.
* D. Cast 2 * ear on line 4 to int.
* F. Change the data type of hearing on line 4 to long

Casteando la variable ear en la línea 3 o 4 a int, definiendo la linea 4 como long o la linea 3 como short.

### 4. What is the output of the following code snippet?
```
3: boolean canine = true, wolf = true;
4: int teeth = 20;
5: canine = (teeth != 10) ^ (wolf=false);
6: System.out.println(canine+", "+teeth+", "+wolf);
```
* B. true, 20, false

En la línea 5, la primera expresión es verdadera, meintras que la segunda no es una comparación sino una asignación de false a wolf. El operador ^ representa XOR, por lo que la operación lanzará verdadero. asignando true a canine.

### 5. Which of the following operators are ranked in increasing or the same order of precedence? Assume the + operator is binary addition, not the unary form. (Choose all that apply.)
* A. +, *, %, -- 
* C. =, ==, !

Los postifijo ++ -- tienen la prescedencia más alta, por lo que no pueden ir al inicio. Después van los prefijos, auditivos binarios, comparadores de igualdad y asignación.

### 6. What is the output of the following program?
```
1: public class CandyCounter {
2:    static long addCandy(double fruit, float vegetables) {
3:       return (int)fruit+vegetables;
4:    }
5:    
6:    public static void main(String[] args) {
7:       System.out.print(addCandy(1.4, 2.4f) + ", ");
8:       System.out.print(addCandy(1.9, (float)4) + ", ");
9:       System.out.print(addCandy((long)(int)(short)2, (float)4)); } }
```
* F. None of the above.

Se genera error de compilación en línea 3 porque se realiza un casteo de fruit a int, pero la suma genera un tipo float porque vegetables es de ese tipo.

### 7. What is the output of the following code snippet?
```
int ph = 7, vis = 2;
boolean clear = vis > 1 & (vis < 9 || ph < 2);
boolean safe = (vis > 2) && (ph++ > 1);
boolean tasty = 7 <= --ph;
System.out.println(clear + "- " + safe + "- " + tasty);
```
* D. true- false- false

clear es verdadera, ya que en la expresión (vis < 9 || ph < 2) se regresa verdadero por cumplirse una operación, y la expresión completa da verdadera al tratarse de un AND.  Con safe la operación termina en la primera expresión, al dar falso la segunda expresión ya no se evalua. La tercera da false debido a que el valor de ph no cambio, pues no se evaluo el postfijo de la linea 3, y en la línea 4 tiene un prefijo que le resta y lo deja con 6.

### 8. What is the output of the following code snippet?
```
4: int pig = (short)4;
5: pig = pig++;
6: long goat = (int)2;
7: goat -= 1.0;
8: System.out.print(pig + " -  " + goat);
```
* A. 4 -  1

Aunque en la línea 5 se está incrementando a pig, primero se realiza la asignación, por lo que la operación ++ solo se ejecuta sin asignar el resultado en la variable.

### 9. What are the unique outputs of the following code snippet? (Choose all that apply.)
```
int a = 2, b = 4, c = 2;
System.out.println(a > 2 ? - - c : b++);
System.out.println(b = (a!=c ? a : b++));
System.out.println(a > b ? b < c ? b : 2 : 1);
```
* A. 1
* D. 4
* E. 5

La segunda línea imprime 4, ya que la condición no se cumple y el operador ternario ejecuta lo que está despues de : (else) e incrementa uno a b. La condición de la tercera línea nuevamente entra a :, lo que hace que b se asigne a sí mísmo, ignorando la operación ++ al tratarse de un postfijo. La ultima línea imprime uno, pues la primera condición no se cumple, lanzandolo al ultimo else.

### 10. What are the unique outputs of the following code snippet? (Choose all that apply.)
```
    short height = 1, weight = 3;
    short zebra = (byte) weight * (byte) height;
    double ox = 1 + height * 2 + weight;
    long giraffe = 1 + 9 % height + 1;
    System.out.println(zebra);
    System.out.println(ox);
    System.out.println(giraffe);
```
* G. The code does not compile.

La línea 2 no compila por que la multiplicación de dos byte es promovido a entero.

### 11. What is the output of the following code?
```
    11: int sample1 = (2 * 4) % 3;
    12: int sample2 = 3 * 2 % 3;
    13: int sample3 = 5 * (1 % 2);
    14: System.out.println(sample1 + ", " + sample2 + ", " + sample3);
```
* D. 2, 0, 5

Primero se evaluan los parentesís, después multiplicaciones, divisiones y residuos de izquierda a derecha, y finalmente las sumas y restas. 

### 12. The _________ operator increases a value and returns the original value, while the _______ operator decreases a value and returns the new value.
* D. post-increment, pre-decrement

El operador post incremento realiza la operación pero retorna el valor origial de la variable, mientras que el pre drecremento realiza la operación y retorna ese nuevo valor.

### 13. What is the output of the following code snippet?
```
    boolean sunny = true, raining = false, sunday = true;
    boolean goingToTheStore = sunny & raining ^ sunday;
    boolean goingToTheZoo = sunday && !raining;
    boolean stayingHome = !(goingToTheStore && goingToTheZoo);
    System.out.println(goingToTheStore + "- " + goingToTheZoo 
       + "- " +stayingHome);
```
* F. true- true- false

La operación sunny & raining ^ sunday se resuelve de izquierda a derecha, realizando primero sunny & raining y el resultado de ese con ^ sunday, dando un true. El operador ! en un booleano invierte su valor, ya que compara si el booleano es false.  

### 14. Which of the following statements are correct? (Choose all that apply.)
* B. The inequality operator (!=) can be used to compare objects.
* E. The return value of an assignment operation expression is the value of the newly assigned variable.
* G. The logical complement operator (!) cannot be used to flip numeric values.

Los operadores != y == pueden usarse para comparar objetos. No se pueden usar para comparar un booleano con un entero. El operador ! no invierte números. El tipo de valor de retorno debe ser el mismo que el tipo de la variable a la que se está asignando el valor.

### 15. Which operators take three operands or values? (Choose all that apply.)
* D. ? :

El operador ternario toma 3 valores: condición ? verdadero : falso

### 16. How many lines of the following code contain compiler errors?
```
    int note = 1 * 2 + (long)3;
    short melody = (byte)(double)(note *= 2);
    double song = melody;
    float symphony = (float)((song == 1_000f) ? song * 2L : song);
```
* B. 1

La primera línea da error de compilación, al sumar el entero generado por la operación 1 * 2 con el 3 long, se promueve el resultado a long, el cual no puede asignarse a una variable tipo int.

### 17. Given the following code snippet, what are the values of the variables after it is executed? (Choose all that apply.)
```
    int ticketsTaken = 1;
    int ticketsSold = 3;
    ticketsSold += 1 + ticketsTaken++;
    ticketsTaken *= 2;
    ticketsSold += (long)1;
```
* C. ticketsSold is 6.
* F. ticketsTaken is 4.

En la línea 3, primero se realiza la operación con el valor original de ticketsTaken y se asigna a ticketsSold, después se realiza el postfijo ++. La ultima línea no da errro de compilación, ya que el operador += genera un casteo implícito automático al tipo de la variable receptora, es decir que internamente realiza ticketsSold = (int) (ticketsSold + (long)1);;

### 18. Which of the following can be used to change the order of operation in an expression? (Choose all that apply.)
* C. ( )

Los parentesís pueden agrupar operaciones para establecer el orden de la expresión.

### 19. What is the result of executing the following code snippet? (Choose all that apply.)
```
    3: int start = 7;
    4: int end = 4;
    5: end += ++start;
    6: start = (byte)(Byte.MAX_VALUE + 1);
```
* B. start is - 128.
* F. end is 12.

No existe error de compilación porque se permite asignar un tipo numerico mas pequeño a un tipo mas grande. La línea 3 realiza primero la operación ++ y después la operación +=. En la línea 6, se incrementa uno al número máximo en un byte, conviritendo la operación en un byte (para evitar la conversión automatica a int), como se pasó el límite de byte (127), el valor se desborda hacia el límite negativo, el cuál es -128. 

### 20. Which of the following statements about unary operators are true? (Choose all that apply.)
* A. Unary operators are always executed before any surrounding numeric binary or ternary operators.
* D. The post-decrement operator (--) returns the value of the variable before the decrement is applied.
* E. The ! operator cannot be used on numeric values.

Los operadores postfijos siempre van a retornar primero el valor de la variable antes de aplicar la operación, mientras que los prefijos realizan primero la operación y retornan su resultado. El operador - sirve para restar valores númericos. El operador invierte valores booleanos, no númericos.

### 21. What is the result of executing the following code snippet?
```
    int myFavoriteNumber = 8;
    int bird = ~myFavoriteNumber;
    int plane = - myFavoriteNumber;
    var superman = bird == plane ? 5 : 10;
    System.out.println(bird + "," + plane + "," + --superman);
```
* E. - 9,- 8,9

El operador ~ suma 1 al valor y lo convierte en negativo, haciendo que bird tome -9 en la segunda línea. En la siguiente línea, se multiplica myFavoriteNumber con el signo - el cual implicitamente representa -1, por lo que plane toma el valor de -8. En la línea 4 hay una condicón ternaria que pregunta si bird y plane son iguales, lo cual es falso, por lo tanto superman toma el valor de 10. En la última línea se mandan a imprimir las variables, siendo superman llamado con el subfijo --, esta operación primero hace un decremento en 1 para reasignarlo a superman y después retorna el valor del mismo, retornando 9.