## Generalisierung und Spezialisierung
Generalisierung → 2 Klassen werden "vereinfacht" und stammen
nun einer Oberklasse ab, die die gemeinsamen Attribute
beinhaltet
  
Spezialisierung → Eine Oberklasse wird "spezialisiert" mehrere
Unterklassen stammen dieser ab und beinhalten neue Attribute.
Letztendlich ist es eine Frage der Perspektive, Generalisierung
und Spezialisierung werden identisch implementiert und in UML
notiert.
  
## Implizite Vererbung
"vermutende Vererbung" Alle Klassen in Java stammen von anderen
Klassen ab. Auch unwissend. Falls eine Klasse nicht explizit
einer anderen abstammt, stammt sie dem Objekt in Java ab.
  
## Explizite Vererbung
bei der expliziten Vererbung wird genau definiert, wovon die
Klasse abstammt. Dies wird durch den `extends` Modifizierer getan.
  
## Abstrakte Klasse
eine abstrakte Klasse ist eine, die nicht instanziiert werden
kann. Sie wird von anderen Klassen benutzt, die dieser
abstammen. Abstrakte Klassen werden genutzt, um eine Art
Hierarchie von Abstraktion zu schaffen, wobei diese Klasse eine
Art Platzhalter darstellt.
  
## super() Methode
die `super` Methode wird benutzt, um den Konstruktor der Oberklasse aufzurufen.
Falls super in einem Konstruktor einer Unterklasse verwendet
wird, muss dies in der ersten Zeile nach der Signatur erfolgen.