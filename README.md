# Python-Tutorial
Tutorial f. Video u. Blog

---

##  Disclaimer

Diese Informationen sind primär für mich gedacht.<br/>
Jedoch biete ich diese auch jeden anderen an. ;-)

Diese Niederschrift soll mir in Zukunft helfen Twitch-Videos, Youtube-Tutorials und Blogbeiträge strukturiert zu erstellen.

---

## Warum Python?

### Vorteile

- Plattformunabhängig
- Universell einsetzbar
- viele Bibliotheken
- OpenSource (Quelloffen)

### Nachteile

- stark unterschiedlicher Syntax zu anderen Sprachen
- Geschwindigkeit

## Grundlagen

### Kommentar

Kommentare werden verwendet um den Code zu dokumentieren.
Hierbei werden komplexe Formeln sowie auch allgemeine Infos notiert.

```python
# Diese Zeile wird von Python ignoriert

"""
Diese Zeilen
werden ebenfalls
von Python ignoriert
"""
```

### Variable

Variable sind Platzhalter für bestimmte Werte.
Egal ob es numerische oder Texte gespeichert werden sollen.

 Wert | dt. Bezeichnung | engl. Bezeichnung
 --- | --- | --- 
 23 | ganze Zahl | Integer 
 1234.56 | Fließkommazahl | Float (Double)
 “Max“ | Text (Buchstaben, Zahlen, Zeichen) | String
 'm' | einzelnes Zeichen | Character
 true | Wahrheitswert | Boolean
 
```python
name = "Max"
alter = 23
maennlich = true
```

Wichtig ist, dass Python keinen logische Grenzen von Werten kennt.
In anderen Programmierstprachen hat z.B.: 
In C++ der Integer: -2.147.483.648 bis 2.147.483.647
Ähnliches Grenzen gelten auch in C, C#, Java und vielen weiteren Sprachen.
Python hingegen sieht es etwas flexibler und erlaubt von Grund auf gößere Werte.
Für Integer liegt dieser bei 9.223.372.036.854.775.807.

### Ausgabe

Um in der Konsole / im Terminal eine Ausgabe zu machen,
wird der Befehl "print()" benötigt.
Dieser gibt einen Text aus umd macht anschließend einen Zeilenumbruch.

```python
# Ausgabe: 
#   Hallo User!
#   2. Ausgabe
print("Hallo User!")
pritn("2. Ausgabe")
```
___

Um eine Ausgabe ohne Zeilenumbruch zu machen ist folgender Code notwendig.

```python
# Ausgabe: 
#   Hallo User!2. Ausgabe
print("Hallo User!", end="")
pritn("2. Ausgabe")
```

___

Um Variablen (siehe nächstes Kapitel) auszugeben:
Hierzu ist eine Verkettung mit "+" notwendig.
Hinzu kommt, das Python in der Regel immer nur Zeichenketten (Sting) ausgeben kann.
daher ist eine Konvertierung in einem String (kurz: str) notwendig.

```python
# Variabe:
name = "Max"
alter = 23

# Möglichkeit #1:
print(name + " ist " + str(alter) + " Jahre alt.")

# Möglichkeit #2:
print(name, "ist", alter, "Jahre alt.")
```

### Eingabe

Um mit dynamischen Werten zu arbeiten braucht man früher oder später eine Benutzereingabe.
Standartmäßig wird immer ein String eingelesen.

```python
print("Ihre Alter: ", end="")
text = input()
print(str(text))
```

Benötigt man jedoch einen anderen Typ (Integer, Double, ...):
```python
print("Ihre Alter: ", end="")
age = int(input())
print("Ihr Alter: " + str(age))

# ---

print("Ihre Kontostand: ", end="")
money = float(input())
print("Ihr Kontostand: " + str(money))
# oder:
print("Ihr Kontostand: ", money)
```

### Verzweigung

Um mehr Logik in den Quellcode zu bekommen ist es erforderlich "wenn das, dann tue" zu implementieren. Diese nennt man Verzweigungen.

Folgende Vergleichsoperatoren gibt es:
Operator | Bedeutung
--- | ---
< | kleiner
<= | kleiner (oder) gleich
\> | größer
\>= | größer (oder) gleich
== | gleich
!= | ungleich

Nun eine kleine Abfrage ob man Kind, Jugendlicher oder Erwachsener ist:

```python
print("Ihr Alter: ", end="")
age = int(input())

if age < 12:		# wenn alter kleiner 12
  print("Kind")
elif alter < 18:	# ansonsten wenn alter kleiner 18
  print("Jugendlicher")
else:				# ansonsten
  print("Erwachsener")
```

Logische Verknüfungen gibt es auch.
Bsp: 
Wenn geschlecht gleich Männlich UND alter > 18 ...
if sex == m and age > 18:

folgende logische Operaten gibt es:
Operator | Bedeutung
--- | ---
and | und
or | oder
not | nicht

**and**
Das "and" sagt aus, dass beide Überprüfungen korrekt sein müssen, damit der nachfolgende Code ausgeführt wird.

**or**
Bein "or" muss mindestens eine überprüfung korrekt sein.

**not**
Bei "not" wird die Abfrage negiert.
```python
name = "Max"

# Ist Name gleich "Susi":
if name == "Susi":
  print("Name ist Susi")

# Ist Name ungleich "Susi":
if name != "Susi:
  print("Name ist nicht Susi")

# Ist nicht Name gleich "Susi":
if not(name == "Susi"):
  print("Name ist nicht Susi")
```

```python
# Variable
age = 23
name = "Max"

print("# AND")
if age == 23 and name == "Max":
  print("age = 23 UND name = Max")
else:
  print("kein UND")

if age == 23 or name == "Max":
  print("age = 23 ODER name = Max")
else:
  print("kein ODER")

if age not 23:
  print("age NICHT 23")
else:
  print("kein NICHT")
```

### Schleife

Wenn ein Durchlauf mehrmals wiederholt werden soll, sollte stehts eine Schleife verwendet werden.

**while**

Eine While-Schleife wird solange durchgeführt bis sie unterbrochen wird.
Beispielsweise wenn man einen Text Zeile für Zeile einlesen will und nicht weis wie viele Zielen dieser lang ist. Hier wird am Ende von der Datei die Schleife abgebrochen.

Bsp.: Ein Menü in der Console soll abgefragt werden bis der User "ende" eingibt.

```python
# Nur das Menü OHNE  weitere Programme...

eingabe = -1
while eingabe != 0:
  # Menü anzeigen
  print("[1] Textverarbeitung")
  print("[2] Taschenrechner")
  print("[3] Dateimanager")
  print("[0] Beenden")
  print("Menuewahl: ", end="")
  eingabe = int(input())

  # Menü-Logik
  if eingabe == 1:
    print("Textverarbeitung wird gestartet")
  elif eingabe == 2:
    print("Taschenrechner wird gestartet")
  elif eingabe == 3:
    print("Dateimanager wird gestartet")
  elif eingabe == 0:
    print("Programm wird beendet")
  else:
    print("Ungueltige EIngabe gemacht")
```

**for**

Die For-Schleife wird auch Zählschleife genannt. Da hier immer ein Zähler (direkt oder indirekt) zum Einsatz kommt.

Bsp.: 1x1 ausgeben...

```python
print("Ihre Eingabe: ", end="")
eingabe = int(input())

for i in range(0, 11):
  print(str(i) + " x " + str(eingabe) + " = " + str(i * eingabe))
```

**verschachtelte for-Schleifen**

Verschachtelte For-Schleifen kommen relativ häufig vor, daher sind diese sehr wichtig zu können.
Verschachtelte For-Schleifen werden verwendet wenn mehrere Dimensionen dargestellt werden müssen. Anwendungen finden sich in Schach (8x8 Felder), in Tabellen (Zeilen udn Spalten) oder auch in Simulatoren (3 Dimensonen bei Flugzeugen, Länge, Breite, Höhe) und vielen mehr.

```python
laenge = 6
hoehe = 4

for h in range(hoehe):
  for l in range(laenge):
    print(str(l) + "/" + str(h) + " ", end="")
  print()
```

### Liste

### .txt Dateien

### .csv Dateien

### Funktion

### Klasse

## Datenbank

## GUI
