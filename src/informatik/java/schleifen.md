# Schleifen

1. [if else](#if-else)
2. [for loops](#for-loops)
3. [while schleifen](#while-schleifen)
4. [do while schleifen](#do-while-schleifen)
5. [scanner](#scanner)
 
## if else

Falls wir code schreiben wollen, der von einer Bedingung abhängig ist, nutzten wir `if` und `else`
```java
boolean test = true;
if (test) {
    System.out.println("<test> ist true!");
} else {
    System.out.println("<test> ist false!");
}
```
In der ersten Zeile sehen wir nach `if` direkt die Bedingung in Klammern. Hier, der boolean "test". Auch hier wird alles in geschwungenen Klassen ausgeführt. Bei dem Beispiel oben ist auch "else" zu sehen. Das wird ausgeführt, falls die erste Bedingung nicht wahr ist, (false), dann wird else ausgeführt.
 
> Wichtig: else ist optional. Wir können auch nur eine `if` Bedingung haben. If kann alleine stehen, aber **else steht niemals ohne if davor!**
 
Wir können auch mehrere Bedingungen aneinander reihen:
```java
int kekse = 2;

if (kekse == 0) {
    System.out.println("keine Kekse mehr da :(");

} else if (kekse == 1) {
    System.out.println("Ein Keks ist noch da! :)");

} else {
    System.out.println("Genug Kekse für mich! :>");
}
```
Hier benutzte ich einfach `else if (Bedingung)`.

## for loops

wenn wir eine Aktion x-mal ausführen wollen, benutzten wir eine for Schleife.
```java
for (int i = 0; i < x; i++) {
    System.out.println(i); // 0, 1, 2, 3 ... x-1
}
```
In der ersten Zeile der `for` Schleife ist die Bedingung `(int i = 0; i < x; i++)` zu sehen. Hier passieren 3 Sachen:
1. Wir erstellen eine **Laufvariable** i mit `int i = 0;`
2. wir überprüfen, ob i kleiner ist als x (unsere Stopp-zahl. z.B. 10) mit `i < x;` 
3. Falls die Bedingung in Schritt 2 wahr ist (`i < x`) wird alles in den
geschwungenen Klammern ausgeführt (hier: `System.out.println(i);`). Danach wird 1
zu i mit `i++` addiert und die Schleife springt zu Schritt 2. Falls die Bedingung
in Schritt 2 falsch ist, wird die Schleife abgebrochen.
 
## While schleifen

While schleifen nutzen wir, wenn wir etwas so lange ausführen wollen, bis eine Bedingung wahr ist.
```java
boolean hunger = true;
while(hunger) {
    essen();
}
```
Die Methode `essen()` wird so lange aufgerufen, bis hunger `false` ist.
 
> Wichtig: While schleifen können unendlich laufen, wenn man nicht aufpasst. z.B., wenn die Bedingung `true` ist und sich nie ändert.
 
Mehr Informationen ist in unserer Präsentation auf Teams.

## do while Schleifen

do while Schleifen sind ähnlich wie [while Schleifen](#while-schleifen), aber der code wird erst ausgeführt, und *danach* die Bedingung überprüft:
```java
boolean hunger = false;
do {
    essen(); // "essen" wird mindestens 1 mal ausgeführt, auch wenn hunger == false ist.
} while (hunger);
```
 
## Scanner

der Scanner ist eine Klasse, die benutzt werden kann, um Daten vom User einzulesen. Dabei müssen wir erst das Objekt erstellen.
```java
Scanner eingabe = new Scanner(System.in);
```
 
> Für die Arbeit am Montag müssen wir **nicht** ein Scanner Objekt erstellen können. Uns wird das Scanner-Objekt zur Verfügung gestellt. (hier: `eingabe`)  

```java
private String username = scanner.nextLine();
private int alter = scanner.nextInt();
scanner.nextLine(); // muss hier stehen, da nach nextInt(); nicht der Buffer gelöscht wird.
private String lieblingsfarbe = scanner.nextLine();
```
