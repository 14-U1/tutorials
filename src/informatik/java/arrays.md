## Standardwerte

Verschiedene Typen haben verschiedene Standardwerte, die genutzt werden, wenn man ihnen keinen konkreten Wert zugewiesen hat. Hier eine Tabelle mit den Standardwerten:

|Typ    |Standardwert              |
|:-----:|--------------------------|
|byte   |`0`                       |
|short  |`0`                       |
|int    |`0`                       |
|long   |`0`                       |
|float  |`0.0`                     |
|double |`0.0`                     |
|boolean|`false`                   |
|char   |`0` (nicht das Zeichen 0) |
|Objekt |`null` (Zeiger auf nichts)|

## Erstellung

Ein leeres Array, bei dem der Speicherplatz mit dem Standardwert des Typen initialisiert wird, erstellt man so:

```java
Typ[] einArray = new Typ[10];
```

Das obere Array hat die Länge 10.
Wenn der Typ zum Beispiel `int` wäre, hätte jedes Element des Arrays nun den Wert `0`.

### Alternative 1

Alternativ kann man direkt Werte für das zu erstellende Array angeben:

```java
einArray = new int[]{1, 2, 3};
```

Das obere Array hat die Länge 3.

### Alternative 2

Bei der Deklaration einer Variable kann bei [Alternative 1](#alternative-1) das `new Typ[]` weggelassen werden:

```java
int[] einAnderesArray = {5, 10, 15};
```

Das obere Array hat die Länge 3.

## Länge

Um im Nachhin ein auf die Länge des Arrays zuzugreifen kann man auf das Attribut `length` des Arrays zugreifen:

```java
int[] einArray = new int[7];
int laenge = einArray.length; // 7
```

Die Länge des Arrays kann nicht im Nachhinein verändert werden.

## Zugriff auf Elemente

Auf die Elemente des Arrays kann so zugegriffen werden:

```java
int[] einArray = new int[]{1, 2, 3};
int erstesElement = einArray[0];
```

Das erste Element hat einen Index von `0`, das zweite einen von `1`, usw.

## Veränderung der Elemente

Um Elemente in dem Array zu verändern muss bei dem Zugriff ein neuer Wert gesetzt werden:

```java
int[] einArray = new int[]{1, 4, 3};
einArray[1] = 2;
```

`einArray` enspricht nun `{1, 2, 3}`.

