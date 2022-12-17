## Generalisierung
Generalisierung => 2 Klassen werden "vereinfacht" und stammen
nun einer Oberklasse ab, die die gemeinsamen Attribute
beinhaltet
  
Spezialisierung => Eine Oberklasse wird "spezialisiert" mehrere
unterklassen stammen dieser ab und beinhalten neue Attribute.
Letztendlich ist es eine Frage der Perspektive, Generalisierung
und Spezialisierung werden identisch impementiert und in UML
notiert.
  
## implizite vererbung
"vermutende vererbung" Alle Klassen in java stammen von anderen
Klassen ab. auch unwissend. Falls eine Klasse nicht explizit
einer anderen abstammt, stammt sie dem Objekt in java ab.
  
## explizite vererbung
Bei der expliziten Vererbung wird genau definiert, wovon die
Klasse abstammt. Dies wird durch den `extends` modifier getan.
  
## abstrakte Klasse
Eine Abstrakte Klasse ist eine, die nicht instanziert werden
kann. Sie wird von anderen Klassen benutzt, die dieser
abstammen. Abstrakte Klassen werden genutzt um eine art
Hirachie von abstraktion zu schaffen, wobei diese Klasse eine
art Platzhalter darstellt.
  
## super() Methode
die `super` methode wird benutzt um den Konstruktor der Oberklasse aufzurufen.
falls super in einem Konstruktor einer Unterklasse verwendet
wird, muss dies in der ersten Zeile nach der Signatur erfolgen.