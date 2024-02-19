# Wizzard-Bot

### Begriffe
- eine Runde = Stiche Ansagen, alle Stiche Spielen (niemand hat am Ende mehr Karten auf der Hand)
- ein Spiel = Runde 1, Runde 2, ...
- ein Stich =  jeder Spieler spielt genau eine Karte

### Grundkonzept
- ConsoleApp
- language: C
- test-framework: https://aceunit.sourceforge.net/glossary
- algorithm: Minimax/Alpha-Beta-Pruning
- concept: Wahrscheinlichkeitsbasierte Entscheidung

### Algorithmus
- #### Bid-Phase
  - https://en.wikipedia.org/wiki/Wizard_(card_game)#First_hand_probabilities
  - Stichansagen der anderen Spieler werden nicht mit einbezogen
  - Wenn letzter, optimal versuchen, sonst einen weniger
- #### Tricks-Phase
  - Berücksichtigen, ob man z.B eine Karte "loswerden" muss
  - Anhand vorheriger gespielter Stiche/Karten in der Runde die Wahrscheinlichkeiten berechnen (entlang der Pfade im Baum)
- #### Round Decisions
  - Schauen ob geschoben oder gezogen wird, je nachdem zuerst versuchen Stiche zu machen, oder zu vermeiden
- #### Game Decisions
  - Betrachtung des Leaderboards um dann gegebenenfalls gezielt gegen die Spieler vor sich zu spielen
#### Game-Graph einer Runde
- ungerichtet
- ##### Knoten
  - repräsentiert einen hypothetisch gespielten Stich
  - gespielte Karten
  - Position als wie vielter gespielt wird
- nach einem Stich werden alle Knoten, die mindestens eine der im gemachten Stich verwendeten Karten enthalten, entfernt
- zwei Knoten sind immer dann verbunden, wenn die zwei repräsentierten Spielstände aufeinander folgen können
 
### Units (+ Tests)
- optimale Anzahl Stiche ermitteln (für Runden-Begin)
- Anzahl Karten die von einer Karte gestochen werden berechnen
- Wahrscheinlichkeit Stich zu bekommen
- Nutzereingabe lesen und speichern
- Game-Graph generieren
- Game-Graph um einen Stich reduzieren
- Wahrscheinlichkeit für einen Kantenzug im Game-Graph berechnen
- Wahrscheinlichkeit berechnen, mit der eine Karte im Spiel ist

### Anmerkung
GameTree statt GameGraph, da die im Vorfeld gespielten Kartein einen Einfluss auf die Wahrscheinlichkeit haben 
und jede gespielte Karte dazu führt, dass die Verzweigungen im nachfolgendem Baum abnehmen
* man muss nochmal schauen, weil bei einem GameTree könnte es zu duplizierten Spielständen kommen
