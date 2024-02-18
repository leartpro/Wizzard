# Wizzard-Bot

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
  - Anhand vorheriger gespielter Stiche/Karten in der Runde die Wahrscheinlichkeiten berechnen
- #### Round Decisions
  - Schauen ob geschoben oder gezogen wird, je nachdem zuerst versuchen Stiche zu machen, oder zu vermeiden
- #### Game Decisions
  - Betrachtung des Leaderboards um dann gegebenenfalls gezielt gegen die Spieler vor sich zu spielen
 
### Units (+ Tests)
- Anzahl Karten die von einer Karte gestochen werden
- Wahrscheinlichkeit Stich zu bekommen
- ...
