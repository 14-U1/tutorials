# Klassenbeziehungen
die folgenden Beispielklassen wurden nur vereinfacht implementiert. Echte Klassen haben weitere Attribute, andere Zugriffsmodifikator und Konstruktoren. Auch Namen ändern sich.
Hier ist eine gute quelle, [Klassenbeziehungen uni-Leipzig](https://www.informatik.uni-leipzig.de/~stjaenicke/mup1/s2.pdf)
  
## Aggregation
bei einer Aggregation existieren beide Klassen unabhängig, eine ist jedoch teil der anderen.
Das Kann in Java so implementiert werden. Hier wird ein Auto als Hauptklasse (dem Ganzen) und eine "Reifen" Klasse als teil Klasse benutzt:
```java
class Reifen {

}

class Auto {
    private Reifen r1;
    
    public Auto(Reifen reifen) {
        this.r1 = reifen;
    }
}
```
Im Konstruktor des Autos wird der Reifen übergeben. Der Reifen existiert außerhalb des Autos, ist aber Teil von diesem.
Die Autoklasse kann so instanziiert werden: `new Auto(einReifenObjekt);` 
  
## Komposition
die Komposition ist eine "verstärkte" Aggregation. Hier ist die teil Klasse fester Bestandteil der Hauptklasse. (dem Ganzen)
hier zum Beispiel ein Haus als ganzes und ein Raum als teil. Der Raum kann nicht ohne Haus existieren.
```java
class Raum {

}

class Haus {
    private Raum raum;

    public Haus() {
        this.raum = new Raum();
    }
}
```
Das Raum-Objekt wird innerhalb des Konstruktors der Haus-Klasse erzeugt. So muss kein Objekt übergeben werden, und jedes Haus erstellt automatisch ein Raum. Ein Haus kann instanziiert werden durch dem Konstruktor: `new Haus();`.
  
# Generalisierung und Spezialisierung
Generalisierung und Spezialisierung sind 2 Wege, um Klassen zu vereinfachen.
Beispielsweise haben wir eine `Küche` Klasse und eine `Wohnzimmer` Klasse.<br>
Beides sind Klassen, die wir Zusammenfassen könnten. Schließlich sind ja beides Räume.<br>
So könnte eine "Raum" Klasse aussehen:
```java
class Raum {
    boolean fenster;
    int tueren;
}
```
Bisher noch nichts Neues.<br>
Wir wollen aber nicht, das ein "Raum" Objekt erstellt werden kann. Diese Klasse soll ja nur als Vereinfachung der Unterklassen [`Kueche` und `Wohnzimmer`] dienen. Deshalb machen wir die Klasse `abstract`.
```java
abstract class Raum {...}
```  
Jetzt haben wir eine abstrakte Klasse um Räume darzustellen. Bisher haben wir aber noch gar nichts mit unseren Unterklassen gemacht. Wir müssen dem Java Compiler sagen, das die `Kueche` und `Wohnzimmer` Klassen die "Raum" Klasse erweitern. Das geht mit dem `extends` Modifikator:
```java
class Kueche extends Raum {...}
class Wohnzimmer extends Raum {...}
```
Das war die Generalisierung. Wir haben 2 Unterklassen und vereinfachen die in einer Oberklasse. Generalisierung und Spezialisierung sind das Gleiche. Nur aus einer anderen Sicht. Bei der Spezialisierung hätten wir eine Oberklasse und wollen die "spezialisieren". Es ist genau der gleiche code.