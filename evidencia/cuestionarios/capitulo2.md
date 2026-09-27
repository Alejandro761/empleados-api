# Cuestionario del libro

## Capitulo 2

### 1. Which of the following Java operators can be used with boolean variables? (Choose all that apply.)
* A. ==
* D. !
* G. Cast with (boolean)

### 2. What data type (or types) will allow the following code snippet to compile? (Choose all that apply.)
```
byte apples = 5;
short oranges = 10;
_____ bananas = apples + oranges;
```
* A. int
* B. long
* D. double

### 3. What change, when applied independently, would allow the following code snippet to  compile? (Choose all that apply.)
```
3: long ear = 10;
4: int hearing = 2 * ear;
```
* B. Cast ear on line 4 to int.
* C. Change the data type of ear on line 3 to short.
* D. Cast 2 * ear on line 4 to int.
* F. Change the data type of hearing on line 4 to long

### 4. What is the output of the following code snippet?
```
3: boolean canine = true, wolf = true;
4: int teeth = 20;
5: canine = (teeth != 10) ^ (wolf=false);
6: System.out.println(canine+", "+teeth+", "+wolf);
```
* B. true, 20, false

### 5. Which of the following operators are ranked in increasing or the same order of precedence? Assume the + operator is binary addition, not the unary form. (Choose all that apply.)
* A. +, *, %, - - 
* C. =, ==, !

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

### 7. What is the output of the following code snippet?
```
int ph = 7, vis = 2;
boolean clear = vis > 1 & (vis < 9 || ph < 2);
boolean safe = (vis > 2) && (ph++ > 1);
boolean tasty = 7 <= - - ph;
System.out.println(clear + "- " + safe + "- " + tasty);
```
* D. true- false- false

### 8. What is the output of the following code snippet?
```
4: int pig = (short)4;
5: pig = pig++;
6: long goat = (int)2;
7: goat - = 1.0;
8: System.out.print(pig + " -  " + goat);
```
* A. 4 -  1

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

### 11. What is the output of the following code?
```
    11: int sample1 = (2 * 4) % 3;
    12: int sample2 = 3 * 2 % 3;
    13: int sample3 = 5 * (1 % 2);
    14: System.out.println(sample1 + ", " + sample2 + ", " + sample3);
```
* D. 2, 0, 5

### 12. The _________ operator increases a value and returns the original value, while the _______ operator decreases a value and returns the new value.
* D. post- increment, pre- decrement

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

### 14. Which of the following statements are correct? (Choose all that apply.)
* B. The inequality operator (!=) can be used to compare objects.
* E. The return value of an assignment operation expression is the value of the newly assigned variable.
* G. The logical complement operator (!) cannot be used to flip numeric values.

### 15. Which operators take three operands or values? (Choose all that apply.)
* D. ? :

### 16. How many lines of the following code contain compiler errors?
```
    int note = 1 * 2 + (long)3;
    short melody = (byte)(double)(note *= 2);
    double song = melody;
    float symphony = (float)((song == 1_000f) ? song * 2L : song);
```
* B. 1

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

### 18. Which of the following can be used to change the order of operation in an expression? (Choose all that apply.)
* C. ( )

### 19. What is the result of executing the following code snippet? (Choose all that apply.)
```
    3: int start = 7;
    4: int end = 4;
    5: end += ++start;
    6: start = (byte)(Byte.MAX_VALUE + 1);
```
* B. start is - 128.
* F. end is 12.

### 20. Which of the following statements about unary operators are true? (Choose all that apply.)
* A. Unary operators are always executed before any surrounding numeric binary or ternary operators.
* D. The post- decrement operator (- - ) returns the value of the variable before the decrement is applied.
* E. The ! operator cannot be used on numeric values.

### 21. What is the result of executing the following code snippet?
```
    int myFavoriteNumber = 8;
    int bird = ~myFavoriteNumber;
    int plane = - myFavoriteNumber;
    var superman = bird == plane ? 5 : 10;
    System.out.println(bird + "," + plane + "," + - - superman);
```
* E. - 9,- 8,9