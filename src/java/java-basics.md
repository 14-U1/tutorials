# Java Basics

1. [Syntax](#syntax)
2. [Methoden / Funktionen](#funktionen)
3. [OOP und Klassen](#objekt-orientierung-und-zugriffsmodifikatoren)

## Syntax
In Java können wir Werte in der RAM abspeichern und darauf zugreifen.
Hier sind einige Beispiele, Wo wir Attribute deklarieren.
```java
String name;
int alter;
double literWasser;
```
Wie im Beispiel werden Attribute mit Datentyp + name + ; deklariert. Diesen Attributen wurden noch keine Attributwerte zugeordnet. Man könnte sie auch als "leeren Platz" bezeichnen, wo später etwas hingeschrieben kann. Um Attributen Werten zuzuschreiben, setzten wir sie einfach Gleich. links ist gleich der wert Rechts.
```java
name = "Florian";
alter = 16;
literWasser = 5.2;
```
  
Man kann auch direkt beim deklarieren Attributen Attributwerten zuordnen, das ist ordentlicher und lesbarer.
```java
String name = "Florian";
int alter = 16;
double literWasser = 5.2;
```
Die Namen der Attribute sind nur für uns, den Entwicklern. Diese werden sich nie ändern und geben uns nur Zugriff auf dem eigentlichen Wert. ("alter" bleibt immer gleich)
  

## Funktionen
neben einfachen Attributwerten, haben wir auch Funktionen (bzw. Methoden). Methoden sind sozusagen code, der von wo anders aufgerufen werden kann. Beim Aufrufen einer Methode können wir ihr auch Werte geben, womit sie arbeten kann.

So sieht eine Beispiel Methode aus:
```java
private int addieren(int a, int b) {
    int c = a + b;
    return c;
}
```
  
  
Jede Methode hat eine "Methodensignatur". Das ist die erste Zeile, wo Zugriffsmodifikator, Rückgabetyp, name und Parameter stehen. Darunter ist der Methoden "Rumpf" zu sehen. Alles in den Klammern `{}` wird ausgeführt.

Die Beispiel Methode oben nimmt 2 integer werte an und gibt einen zurück. Sie kann aufgerufen werden mit: `addieren(1, 2)` hier würden wir das Ergebnis aber nicht speichern. Falls das Ergebnis gespeichert werden soll, müssen wir angeben wo:`int summe = addieren(1, 2)`. Genau wie bei dem deklarieren von Strings in dem Abschnitt [Syntax](#syntax)
  
Bei manchen methoden gibt es auch gar kein Ergebnis (rückgabetyp). Diese sind dann vom typ `void`. Beispielsweise die Main methode, `public static void main(String[] args) {}`

Methoden sind immer Teil von Klassen, und deren Zugriffsmodifikator bestimmt die Sichtbarkeit. Das wird im Nächsten Abschnitt [OOP und Zugrifsmodifikatoren](#objekt-orientierung-und-zugriffsmodifikatoren) erklärt.
  
  
## Objekt orientierung und Zugriffsmodifikatoren
Jetzt, wo wir den [Syntax](#syntax) und [Methoden](#funktionen) verstehen, können wir uns Klassen angucken. der Datentyp `String` ist zum beispiel eine Klasse. Klassen werden groß geschrieben. Deshalb wird `String` groß geschrieben und `int` klein.
Klassen sind nur "Bündel" voller Attributwerten und Funktionen. Eine Klasse ist also ein Weg, Werte und Methoden zu bündeln und abzukapseln. Das "bündeln" kann die Programmierung vereinfachen und übersichtlicher machen. Hier eine Beispiel Klasse "Konto":
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
Hier kommt auch das Prinzip von "Sichtbarkeit" ins Spiel. Die Attribute "kontoNummer" und "name" sind `private`. Das heißt sie sind nur in dieser Klasse Sichtbar. Nicht außerhalb unseres "Bündels"
Unter den Attributwerten ist ein Beispiel Konstruktor. Ein Konstruktor ist einfach eine besondere Methode, die wir nutzen um unser Objekt zu erstellen. Momentan ist unsere Klasse einfach ein Plan. Der Konstruktor erstellt ein Objekt, wo alle Attributwerte und Methoden drin sind.
  
> In die Objekte können wir nicht reingucken, nur in die Klassen!
  
Danach kommt eine "getMethode" das ist eine einfache Methode, die einen privaten Wert zurückgibt. Diese ist `public`, da wir sie außerhalb unseres Objektes nutzen wollen.
Hier ein Beispiel, wo ich ein Objekt namens konto1 erstelle und danach benutzte:
```java
Konto konto1 = new Konto(1, "Florian");
konto1.getKontonummer() //rückgabe: 1
```
Der Konstruktor wird mit `new KLASSENNAME();` aufgerufen.
Hierbei ist zu beachten das wir das Konto genau wie einen normalen String oder integer abspeichern. (`String name = "Florian"`).
Hier ist auch zu sehen, das wir die public Methode "getKontonummer" über einen Punkt aufrufen. Das Objekt `konto1` ist unser Bündel, wir haben nur noch Zugriff auf die `public` Attribute und Methoden.