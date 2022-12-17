# Generalisierung und Spezialisierung Beispiel 2
## Generalisierung:
PKW, LKW → Fahrzeug
  
```java
//Oberklasse:

abstract class Fahrzeug {
    
    protected String farbe; //protected -> verfügbar in unterklassen

    public Fahrzeug(String farbe) { //Konstruktor der Klasse "Fahrzeug"
        this.farbe = farbe;
    }
}

//Unterklassen:

class LKW extends Fahrzeug {
    
    private double maxGewicht;

    public LKW(String farbe, double maxGewicht) { //Konstruktor der Klasse LKW
        super(farbe); //ruft den Konstruktor der Klasse "Fahrzeug" auf
        this.maxGewicht = maxGewicht;
    }
}

class PKW extends Fahrzeug {

    private int tueren;

    public PKW(String farbe, int tueren) { //Konstruktor der Klasse PKW
        super(farbe); //ruft den Konstruktor der Klasse "Fahrzeug" auf
        this.tueren = tueren;
    }

}
```
  
## Spezialisierung:
Haus → Schule, Krankenhaus
  
```java
//Oberklasse

abstract class Haus {
    
    protected boolean fenster; //protected -> verfügbar in unterklassen
    
    public Haus(boolean fenster) {
        this.fenster = fenster;
    } 
}

//Unterklassen

class Schule extends Haus {

    private int tueren;

    public Schule(boolean fenster, int tueren) {
        super(fenster);
        this.tueren = tueren;
    }
}

class Krankenhaus extends Haus {

    private int betten;

    public Krankenhaus(boolean fenster, int betten) {
        super(fenster);
        this.betten = betten;
    }
}

```
  
  
> Beides ist das Gleiche. Spezialisierung kann auch als Generalisierung angesehen werden. Die Implementation ist identisch. <br>Spezialisierung → Eine Klasse, die in mehrere spezialisiert wird.<br>
Generalisierung → mehrere Klassen die in eine vereinfacht/zusammengefasst werden (diese Klasse hat dann die gemeinsamen Attribute und Methoden)