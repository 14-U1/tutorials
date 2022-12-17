# Java Basics

1. [Syntax](#syntax)
2. [Methoden / Funktionen](#funktionen)
3. [OOP und Klassen](#objekt-orientierung-und-zugriffsmodifikatoren)

## Syntax
in Java können wir Werte in der RAM abspeichern und darauf zugreifen.
Hier sind einige Beispiele, wo wir Attribute deklarieren.
```java
String name;
int alter;
double literWasser;
```
Wie im Beispiel werden Attribute mit Datentyp + name + ; deklariert. Diesen Attributen wurden noch keine Attributwerte zugeordnet. Man könnte sie auch als "leeren Platz" bezeichnen, wo später etwas hingeschrieben werden kann. Um Attributen Werten zuzuschreiben, setzten wir sie einfach Gleich. Links ist gleich der wert Rechts.
```java
name = "Florian";
alter = 16;
literWasser = 5.2;
```
  
Man kann auch direkt beim Deklarieren Attributen Attributwerten zuordnen, das ist ordentlicher und lesbarer.
```java
String name = "Florian";
int alter = 16;
double literWasser = 5.2;
```
Die Namen der Attribute sind nur für uns, den Entwicklern. Diese werden sich nie ändern und geben uns nur Zugriff auf dem eigentlichen Wert. ("alter" bleibt immer gleich)
  

## Funktionen
neben einfachen Attributwerten haben wir auch Funktionen (bzw. Methoden). Methoden sind sozusagen code, der von woanders aufgerufen werden kann. Beim Aufrufen einer Methode können wir ihr auch Werte geben, womit sie arbeiten kann.

So sieht eine Beispielmethode aus:
```java
private int addieren(int a, int b) {
    int c = a + b;
    return c;
}
```
  
  
Jede Methode hat eine "Methodensignatur". Das ist die erste Zeile, wo Zugriffsmodifikator, Rückgabetyp, Name und Parameter stehen. Darunter ist der Methoden "Rumpf" zu sehen. Alles in den Klammern `{}` wird ausgeführt.

Die Beispielmethode oben nimmt 2 integer werte an und gibt einen zurück. Sie kann aufgerufen werden mit: `addieren(1, 2)` hier würden wir das Ergebnis aber nicht speichern. Falls das Ergebnis gespeichert werden soll, müssen wir angeben wo:`int summe = addieren(1, 2)`. Genau wie bei dem Deklarieren von Strings in dem Abschnitt [Syntax](#syntax)
  
Bei manchen Methoden gibt es auch gar kein Ergebnis (Rückgabetyp). Diese sind dann vom Typ `void`. Beispielsweise die Main Methode, `public static void main(String[] args) {}`

Methoden sind immer Teil von Klassen, und deren Zugriffsmodifikator bestimmt die Sichtbarkeit. Das wird im Nächsten Abschnitt [OOP und Zugriffsmodifikatoren](#objekt-orientierung-und-zugriffsmodifikatoren) erklärt.
  
  
## Objekt Orientierung und Zugriffsmodifikatoren
jetzt, wo wir der [Syntax](#syntax) und [Methoden](#funktionen) verstehen, können wir uns Klassen angucken. Der Datentyp `String` ist zum Beispiel eine Klasse. Klassen werden großgeschrieben. Deshalb wird `String` großgeschrieben und `int` klein.
Klassen sind nur "Bündel" voller Attributwerten und Funktionen. Eine Klasse ist also ein Weg, Werte und Methoden zu bündeln und abzukapseln. Das "bündeln" kann die Programmierung vereinfachen und übersichtlicher machen. Hier eine Beispielklasse "Konto":
```java
class Konto {
    private int kontoNummer;
    private String name;

    public Konto(int kontoNummer, String name) {
        this.kontoNummer = kontoNummer;
        this.name = name;
    }

    public int getKontonummer() {
        return this.kontonummer;
    }
}
```
Hier kommt auch das Prinzip von "Sichtbarkeit" ins Spiel. Die Attribute "kontoNummer" und "name" sind `private`. Das heißt, sie sind nur in dieser Klasse Sichtbar. Nicht außerhalb unseres "Bündels"
Unter den Attributwerten ist ein Beispiel Konstruktor. Ein Konstruktor ist einfach eine besondere Methode, die wir nutzen, um unser Objekt zu erstellen. Momentan ist unsere Klasse einfach ein Plan. Der Konstruktor erstellt ein Objekt, wo alle Attributwerte und Methoden drin sind.
  
> In die Objekte können wir nicht reingucken, nur in die Klassen!
  
Danach kommt eine "getMethode" das ist eine einfache Methode, die einen privaten Wert zurückgibt. Diese ist `public`, da wir sie außerhalb unseres Objektes nutzen wollen.
Hier ein Beispiel, wo ich ein Objekt namens konto1 erstelle und danach benutzte:
```java
Konto konto1 = new Konto(1, "Florian");
konto1.getKontonummer() //rückgabe: 1
```
Der Konstruktor wird mit `new KLASSENNAME();` aufgerufen.
Hierbei ist zu beachten, dass wir das Konto genau wie einen normalen String oder integer abspeichern. (`String name = "Florian"`).
Hier ist auch zu sehen, das wir die public Methode "getKontonummer" über einen Punkt aufrufen. Das Objekt `konto1` ist unser Bündel, wir haben nur noch Zugriff auf die `public` Attribute und Methoden.