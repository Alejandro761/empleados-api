# Cuestionario del libro

## Capitulo 1

### 1. Which of the following are legal entry point methods that can be run from the command line? (Choose all that apply.)
* D. public static final void main(String[] args)
* E. public static void main(String[] args)

El metodo main debe ser público para que la máquina virtual de java pueda llamarlo, también debe ser estático ya que no se hace una instancia de la clase y como no regresa nada debe ser de tipo void.

### 2. Which answer options represent the order in which the following statements can be assembled into a program that will compile successfully? (Choose all that apply.)
```
X: class Rabbit {}
Y: import java.util.*;
Z: package animals;
```
* C. Z, Y, X
* D. Y, X
* E. Z, X

El orden correcto es package, import, class, aunque tanto package como import son opcionales.

### 3. Which of the following are true? (Choose all that apply.)
```
public class Bunny {
    public static void main(String[] x) {
        Bunny bun = new Bunny();
} }
```
* A. Bunny is a class.
* E. bun is a reference to an object.

Bunny es una clase, las clases se definen con la palabra reservada class, por lo tanto, bun no es una clase sino una instancia de la clase Bunny. Tampoco main es una clase ni un objeto, es un metodo de tipo void.

### 4. Which of the following are valid Java identifiers? (Choose all that apply.)
B. _helloWorld$
E. Public
G. _Q2_

Las variable pueden empezar con $ o _, pero no con números. Pueden tener letras mayúsculas y minúsculas y java distingue entre ellas. Un solo guión bajo ( _ ) es una palabra reservada. 

### 5. Which statements about the following program are correct? (Choose all that apply.)
```
2:  public class Bear {
3:     private Bear pandaBear;
4:     private void roar(Bear b) {
5:        System.out.println("Roar!");
6:        pandaBear = b;
7:     }
8:     public static void main(String[] args) {
9:        Bear brownBear = new Bear();
10:       Bear polarBear = new Bear();
11:       brownBear.roar(polarBear);
12:       polarBear = null;
13:       brownBear = null;
14:       System.gc(); } }
```
* A. The object created on line 9 is eligible for garbage collection after line 13.
* D. The object created on line 10 is eligible for garbage collection after line 13.
* F. Garbage collection might or might not run.

La recolección de basura no está garantizada. Aunque en la línea 12 polarBear pierda el objeto que se creó en la línea 10, este aun no es elegible para el garbage collection ya que aun se tiene la referencia de ese objeto en brownBear.pandaBear. Es en la línea 13 cuando se pierden ambos objetos ya que brownBear borra la referencia del objeto que se creó en la línea 9 y por lo tanto del objeto al que apunto en la linea 11.

### 6. Assuming the following class compiles, how many variables defined in the class or method are in scope on the line marked on line 14?
```
1:  public class Camel {
2:     { int hairs = 3_000_0; }
3:     long water, air=2;
4:     boolean twoHumps = true;
5:     public void spit(float distance) {
6:        var path = "";
7:        { double teeth = 32 + distance++; }
8:        while(water > 0) {
9:           int age = twoHumps ? 1 : 2;
10:          short i=- 1;
11:          for(i=0; i<10; i++) {
12:             var Private = 2;
13:          }
14:          // SCOPE
15:       }
16:    }
17: }
```
* F. 7

En las líneas 2 y 7 hay variables dentro de bloques que incian y terminan en una sola línea, esas variables solo existen en ese bloque. La variable de la línea 12 está en un bloque que terminé en la línea 13, antes del SCOPE. Las variables que estan al alcance son las variables de la clase definidas en las lineas 3 y 4, el parametro de la función split y la variable definida dentro de está y las variables definidas dentro del while.

### 7. Which are true about this code? (Choose all that apply.)
```
public class KitchenSink {
    private int numForks;
    public static void main(String[] args) {
        int numKnives;
        System.out.print("""
            "# forks = " + numForks +
            " # knives = " + numKnives +
            # cups = 0""");
    }
}
```
* C. The output includes: # cups = 0.
* E. The output includes one or more lines that begin with whitespace.

Todo lo que está dentro de las comillas triples es texto, por lo que las variables numForks y numKnives en realidad no se están llamando.

### 8. Which of the following code snippets about var compile without issue when used in a method? (Choose all that apply.)
* B. var fall = "leaves";
* D. var night = Integer.valueOf(3);
* E. var day = 1/0;
* H. var morning = ""; morning = null;

Un tipo var no puede ser incializado como nulo, pero si se le puede asignar si el tipo subyacente no es primitivo. var no se pudde usar en una asignación múltiple.

### 9. Which of the following are correct? (Choose all that apply.)
* E. A class variable of type String defaults to null.

Los tipos float incluyen punto decimal y tanto ese como otros tipos primitivos no se inicializan por default con null. El tipo String al tratarse de una clase por defecto es null.

### 10. Which of the following expressions, when inserted independently into the blank line, allow the code to compile? (Choose all that apply.)
```
public void printMagicData() {
    var magic = __________;
    System.out.println(magic);
}
```
* A. 3_1
* E. 2_234.0_0
* F. 9___6

No se puede colocar un guión bajo al inicio o al final y tampoco junto a un punto.

### 11. Given the following two class files, what is the maximum number of imports that can be removed and have the code still compile?
```
// Water.java
package aquarium;
public class Water { }
// Tank.java
package aquarium;
import java.lang.*;
import java.lang.System;
import aquarium.Water;
import aquarium.*;
public class Tank {
    public void print(Water water) {
    System.out.println(water); } }
```
* E. 4

La importación de java.lang se puede omitir ya que está importado por defecto. Como Water y Tank se encuentran dentro del paquete aquarium, se pueden omitir los imports de aquarium.

### 12. Which statements about the following class are correct? (Choose all that apply.)
```
1: public class ClownFish {
2:    int gills = 0, double weight=2;
3:    { int fins = gills; }
4:    void print(int length = 3) {
5:       System.out.println(gills);
6:       System.out.println(weight);
7:       System.out.println(fins);
8:       System.out.println(length);
9: } }
```
* A. Line 2 generates a compiler error.
* C. Line 4 generates a compiler error.
* D. Line 7 generates a compiler error.

La línea 2 genera error de compilación porque no se puede hacer multiples declaraciones de diferentes tipos separados por coma. La línea 4 genera error de compilación porque no se puden establecer valores por defecto en parametros de funciones. La línea 7 genera error de compilación porque esa variable no está declarada, solo existió en un scope que vive y muere en la línea 3.

### 13. Given the following classes, which of the following snippets can independently be inserted in place of INSERT IMPORTS HERE and have the code compile? (Choose all that apply.)
```
package aquarium;
public class Water {
    boolean salty = false;
}
package aquarium.jellies;
public class Water {
    boolean salty = true;
}
package employee;
INSERT IMPORTS HERE
public class WaterFiller {
    Water water;
}
```
* A. import aquarium.*;
* B. import aquarium.Water;
import aquarium.jellies.*;
* C. import aquarium.*;
import aquarium.jellies.Water;

La opción A importa la clase Water que se encuentra en el paquete aquarium. Las opciones B y C importar la clase Water especificandolo en el import tomando prioridad sobre los comodines. Las opciones D y E generan error porque java no sabe cual Water elegir.

### 14. Which of the following statements about the code snippet are true? (Choose all that apply.)
```
3: short numPets = 5L;
4: int numGrains = 2.0;
5: String name = "Scruffy";
6: int d = numPets.length();
7: int e = numGrains.length;
8: int f = name.length();
```
* A. Line 3 generates a compiler error.
* B. Line 4 generates a compiler error.
* D. Line 6 generates a compiler error.
* E. Line 7 generates a compiler error.

Un valor asignado a un shor no lleva L. Los enteros no llevan punto decimal. La función length devuelve el tamaño de una cadena de texto por lo que no existe en tipos de datos primitivos.

### 15. Which of the following statements about garbage collection are correct? (Choose all that apply.)
* C. Garbage collection allows the JVM to reclaim memory for other objects.
* E. An object may be eligible for garbage collection but never removed from the heap.
* F. An object is eligible for garbage collection once no references to it are accessible in the program.

No existe garantía de cuando se ejecutará la recolección de basura aunque se llame la función System.gc(). Cuando no existen referencias a un objeto, este ya es elegible para el garbage collection.

### 16. Which are true about this code? (Choose all that apply.)
```
var blocky = """
    squirrel \s
    pigeon   \
    termite""";
System.out.print(blocky);
```
* A. It outputs two lines.
* D. There is one line with trailing whitespace.

Se imprimen dos líneas ya que un \ ignora el salto de línea. Existe espacio en blanco al final de la primera línea porque \s permite conservar los espacios en blanco.

### 17. What lines are printed by the following program? (Choose all that apply.)
```
1:  public class WaterBottle {
2:     private String brand;
3:     private boolean empty;
4:     public static float code;
5:     public static void main(String[] args) {
6:        WaterBottle wb = new WaterBottle();
7:        System.out.println("Empty = " + wb.empty);
8:        System.out.println("Brand = " + wb.brand);
9:        System.out.println("Code = " + code);
10:    } }
```
* D. Empty = false
* F. Brand = null
* G. Code = 0.0

El valor por defecto de un booleano es false, ya que se trata de un dato primitivo. Igualmente un float es primitivo, por lo que su valor por defecto es 0.0. Un String al tratarse de una clase, si no es inicializada su valor es null.


### 18. Which of the following statements about var are true? (Choose all that apply.)
* B. The type of a var is known at compile time.
* C. A var cannot be used as an instance variable.
* F. The type of a var cannot change at runtime.

El tipo var no puede usarse en un contructor. Una variable declarada con var no puede recibir un valor de otro tipo de dato posteriormente.

### 19. Which are true about the following code? (Choose all that apply.)
```
var num1 = Long.parseLong("100");
var num2 = Long.valueOf("100");
System.out.println(Long.max(num1, num2));
```
* A. The output is 100.
* D. num1 is a primitive.

La función parseLong regresa un tipo long primitivo, mientras que valueOf regresa un objeto Long. La salida compara el máximo de ambas variables, el cual es 100 porque los dos son iguales.

### 20. Which statements about the following class are correct? (Choose all that apply.)
```
1:  public class PoliceBox {
2:     String color;
3:     long age;
4:     public void PoliceBox() {
5:        color = "blue";
6:        age = 1200;
7:     }
8:     public static void main(String []time) {
9:        var p = new PoliceBox();
10:       var q = new PoliceBox();
11:       p.color = "green";
12:       p.age = 1400;
13:       p = q;
14:       System.out.println("Q1="+q.color);
15:       System.out.println("Q2="+q.age);
16:       System.out.println("P1="+p.color);
17:       System.out.println("P2="+p.age);
18: } }
```
* C. It prints P1=null.

Tanto p como q se crean con sus valores nulos porque no existe un contructor definido en la clase, ya que PoliceBox() es un tipo void y nunca es invocado. A los atributos de p se asignan valores pero después la referencia de ese objeto queda disponible para ser recolectado por el garbage collector ya que apunta ahora al objeto q, el cual tiene sus atributos nulos.

### 21. What is the output of executing the following class?
```
1:  public class Salmon {
2:     int count;
3:     { System.out.print(count+"- "); }
4:     { count++; }
5:     public Salmon() {
6:        count = 4;
7:        System.out.print(2+"- ");
8:     }
9:     public static void main(String[] args) {
10:       System.out.print(7+"- ");
11:       var s = new Salmon();
12:       System.out.print(s.count+"- "); } }
```
* D. 7- 0- 2- 4- 

Primero se ejecuta el main en la línea 10 mostrando 7, después se crea el objeto en la la línea 11, ejecutando la línea 3 el cuál muestra el valor por defecto de count que es 0. Posteriormente se ejecuta el constructor, el cual asigna 4 a count e imprime 2, después volvemos al método main en la línea 12 el cual imprime el valor de count del objeto, el cual el constructor asignó 4.

### 22. Given the following class, which of the following lines of code can independently replace INSERT CODE HERE to make the code compile? (Choose all that apply.)
```
public class Price {
    public void admission() {
        INSERT CODE HERE
        System.out.print(amount);
        } }
```
* C. int amount = 0xE;
* F. int amount = 0b101;
* G. double amount = 9_2.1_2;

En java, el prefijo 0x indica que el valor es un número hexadecimal, y 0b indica que es binario. El guión bajo no debe estar antes ni después del punto decimal. Java distingue entre mayúsculas y minúsculas.

### 23. Which statements about the following class are true? (Choose all that apply.)
```
1:  public class River {
2:     int Depth = 1;
3:     float temp = 50.0;
4:     public void flow() {
5:        for (int i = 0; i < 1; i++) {
6:           int depth = 2;
7:           depth++;
8:           temp- - ;
9:        }
10:       System.out.println(depth);
11:       System.out.println(temp); }
12:    public static void main(String... s) {
13:       new River().flow();
14: } }
```
* A. Line 3 generates a compiler error.
* D. Line 10 generates a compiler error.

La línea 3 genera error de compilación porque los valores con punto decimal por defecto son double si no se pone el sufijo f. La línea 10 genera error de compilación porque se quiere imprimir una variable que no existe en el scope actual.