# Abstrakte Klassen
Wir können eine Klassen den `abstract` Modifizierer geben, damit kein Objekt von ihr erstellt werden Kann. Stellt euch eine abstrakte Klasse wie eine art "Vorlage Klasse" vor. Eine andere Klasse kann mit `extends` von der abstrakten Klasse abstammen (mehr dazu in "Klassenbeziehungen"). Dabei können wir einen Konstruktor mittels `super()` aufrufen, auf `protected` Attributen zugreifen und Methoden überschreiben. Hier ist ein Beispiel:

```java
abstract class VorlageKlasse {

    protected int testInt;
    abstract void testVoid();
    
    public VorlageKlasse(int testInt) {
        this.testInt = testInt;
    }
}
```
  
> Das ist das komplizierteste, was wir machen müssen. Viele Sachen die hier vorkommen, wurden in anderen Beiträgen erklärt. Es macht also Sinn, mindestens die folgenden: [Definitionen](./Definitionen.md), [Generalisierung 2](./Generalisierung.md) und [Klassenbeziehungen](./klassenbeziehungen.md) erstmal durchzulesen.
  

In der ersten Zeile sehen wir `abstract class VorlageKlasse {` hiermit deklarieren wir eine neue abstrakte Klasse namens `VorlageKlasse`.<br><br>
In der nächsten Zeile sehen wir einen `protected` integer namens testInt. `protected` ist ähnlich wie `private`. Das heißt, wenn eine Klasse unserer VorlageKlasse abstammt, hat diese Klasse (und ihr Objekt) zugriff auf diesen integer. von außen, kann man den Integer aber nicht erreichen. Das sieht man gleich am Beispiel am besten. Dazu könnt ihr mit NetBeans / Intellij Idea etwas rumspielen. So bekommt man dafür ein Gefühl.<br><br>
Nach dem protected integer, kommt `abstract void testVoid();`. Das ist eine abstrakte Methode. Besser gesagt, es ist die Signatur der abstrakten Methode. **Abstrakte Methoden haben keinen Methodenrumpf** wie normale [Methoden](./java-basics.md). Das ist so, weil diese Methode von unserer abstammenden Klasse implementiert werden soll. Wie bereits gesagt ist unsere abstrakte Klasse nicht mehr als eine "Vorlage". Das gleiche gillt für diese Methode. Sie ist eine Vorlage. Wie die implementiert werden soll sieht man gleich im Beispiel.<br><br>
Nach unseren Attributen kommt noch unser Konstruktor. Der dürfte allen bekannt vorkommen. Hier hat sich nichts geändert. Da wir aber kein Objekt von einer Abstrakten Klasse erstellen können, wird dieser mithilfe von `super()` in unserer abstammenden Klasse ausgeführt.<br><br>
Hier ist ein Beispiel, wie eine abstammende Klasse aussehen könnte;
```java
class abstammendeKlasse extends VorlageKlasse { //normale Klasse stammt der abstrakten VorlageKlasse ab.
    
    private String testString; //normales Attribut
    
    public abstammendeKlasse(int testInt, String testString){ //normaler Konstruktor der abstammendeKlasse
        super(testInt); //wir rufen den Konstruktor der Oberklasse "VorlageKlasse" auf
        this.testString = testString;
    }

    public void testVoid() { //Diese Methode ist die implementation der abstrakten Methode in VorlageKlasse. Diese hier MUSS implementiert werden!
        //beispiel leere Methode
    }

    public int getTestInt() { //getter für den protected wert der VorlageKlasse
        return this.testInt;  //wir haben in der abstammendeKlasse nirgendswo testInt deklariert. Wir können auf ihn trotzdem zugreifen, da er in der Oberklasse "VorlageKlasse" als protected deklariert wurde.
    }
}
``` 