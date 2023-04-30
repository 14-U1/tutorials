# Java Basics

1. [Attribute](#attribute)
2. [Methoden](#methoden)
3. [OOP und Klassen](#objekt-orientierung-und-zugriffsmodifikatoren)

## Attribute

In Java können wir durch Attribute Werte in dem RAM abspeichern und darauf zugreifen.
Hier sind einige Beispiele, wie man Attribute deklariert:

```java
String name;
int alter;
double literWasser;
```

Wie man im Beispiel sehen kann, werden Attribute mit `Datentyp + name + ;` deklariert.
Diesen Attributen wurden Standardwerte zugeordnet (siehe [Standardwerte](./arrays.md#standardwerte)).
Um Attributen neue Werte zu geben, benutzt man den Zuweisungsoperator.
Dem Attribut links wird der Wert rechts zugeswiesen:

```java
name = "Florian";
alter = 16;
literWasser = 5.2;
```
 
Man kann die Attribute auch direkt bei der Deklaration initialisieren, was für erhöhte
Lesbarkeit sorgt:

```java
String name = "Florian";
int alter = 16;
double literWasser = 5.2;
```

Der Name eines Attributes kann sich nicht ändern.

## Methoden 

Klassen können neben Attributen, Methoden enthalten.
Methoden sind Codestücke, die von anderen Methoden aus aufgerufen werden können.
Beim Aufrufen einer Methode können wir ihr auch Werte übergeben:

```java
private int addieren(int a, int b) {
    int c = a + b;
    return c;
}
```
 
Jede Methode hat eine Methodensignatur.
Diese besteht aus der ersten Zeile der Methode, in welcher Zugriffsmodifikatoren,
Rückgabetyp, Name der Methode und Parameter angegeben werden.
Darunter ist der Methodenrumpf (alles in den geschweiften Klammern), welcher den Code
enthält, der beim Aufrufen der Methode ausgeführt wird.

Die Beispielmethode oben nimmt 2 Integer Werte an und gibt einen Integerwert zurück.
Sie kann mit `addieren(1, 2)` von der gleichen Klasse aus aufgerufen werden.
Falls das Ergebnis gespeichert werden soll, muss es einer Variable oder einem Attribut
zugewiesen werden: `int summe = objekt.addieren(1, 2)` (siehe [Attribute](#attribute)).
 
Bei manchen Methoden gibt es kein Ergebnis, also geben sie nichts zurück.
Diese haben dann `void` als Rückgabetyp.
Beispielsweise die Main Methode `public static void main(String[] args) {}` gibt nichts
zurück.

Eine Methode ist immer Teil einer Klasse.
Die Zugriffsmodifikator bestimmt die Sichtbarkeit.
Zugriffsmodifikatoren werden im Nächsten Abschnitt
[OOP und Zugriffsmodifikatoren](#objekt-orientierung-und-zugriffsmodifikatoren) erklärt.
 
## Objekt Orientierung und Zugriffsmodifikatoren

Nachdem Attribute und Methoden verstanden sind, sind Klassen an der Reihe.
Der Datentyp `String` ist zum Beispiel eine Klasse.
Klassen werden **immer** großgeschrieben.
So wird zum Beispiel `String` großgeschrieben und `int` klein, weil `int` ein primitiver
Datentyp ist.
Klassen sind Behälter für Attribute und Methoden.
Ein Objekt ist eine Ausprägung einer Klasse mit Attributwerten.
Eine Klasse ist ein Weg, Attribute und Methoden zu bündeln und abzukapseln.
Das bündeln kann die Programmierung vereinfachen und übersichtlicher machen.
Hier eine Beispielklasse "Konto":

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

Hier kommt auch das Prinzip von "Sichtbarkeit" ins Spiel.
Die Attribute "kontoNummer" und "name" sind `private`.
Das heißt, sie sind nur in dieser Klasse sichtbar.
Nicht außerhalb unseres "Bündels"
Unter den Attributwerten ist ein Beispiel Konstruktor.
Ein Konstruktor ist einfach eine besondere Methode, die wir nutzen, um unser Objekt zu erstellen.
Momentan ist unsere Klasse einfach ein Plan.
Der Konstruktor erstellt ein Objekt, wo alle Attributwerte und Methoden drin sind.
 
> In die Objekte können wir nicht reingucken, nur in die Klassen!
 
Danach kommt eine "getMethode" das ist eine einfache Methode, die einen privaten Wert zurückgibt. Diese ist `public`, da wir sie außerhalb unseres Objektes nutzen wollen.
Hier ein Beispiel, wo ich ein Objekt namens konto1 erstelle und danach benutzte:

```java
Konto konto1 = new Konto(1, "Florian");
konto1.getKontonummer() //rückgabe: 1
```

Der Konstruktor wird mit `new KLASSENNAME();` aufgerufen.
Hierbei ist zu beachten, dass wir das Konto genau wie einen normalen String oder integer
abspeichern. (`String name = "Florian"`).
Hier ist auch zu sehen, das wir die public Methode "getKontonummer" über einen Punkt
aufrufen.
Das Objekt `konto1` ist unser Bündel, wir haben nur noch Zugriff auf die `public`
Attribute und Methoden.
