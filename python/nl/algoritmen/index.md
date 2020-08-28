# Algoritmen

Computers laten pas echt zien wat ze kunnen als de oplossing van een probleem niet goed uitgedrukt kan worden door een formule. Bij programmeren werken we aan het verzinnen en uitschrijven van *algoritmes*, die precies specificeren hoe een probleem stap-voor-stap opgelost moet worden. Een belangrijk aspect van algoritmen is dat ze werken voor verschillende invoer. In het filmpje hieronder moet het algoritme het juiste antwoord opleveren als er 0, 1, 2, 3, 4, enz. mensen in de kamer zijn.

![embed](https://www.youtube.com/embed/6hfOvs8pY1k)

In het hoofdstuk [basiselementen](/python/basiselementen) heb je een aantal **instructies** (**statements**) geleerd waar Python mee om kan gaan:

- de `print`-instructie, om boodschappen aan de gebruiker door te geven
- de `input`-instructie, om informatie van de gebruiker op te vragen
- de `=`-operator, om variabelen te definiëren of te wijzigen

Daarnaast heb je kennis gemaakt met operators die gebruikt worden om expressies samen te stellen. Dit was al genoeg om een werkend programma te schrijven. We gaan het nu interessanter maken door uitzonderingen en herhaling toe te staan.

## Voorwaardelijke instructies

In de voorgaande programma's schreven we scriptjes die regel voor regel van boven naar beneden werden uitgevoerd. Een soort stapsgewijze handleiding. Programma's worden interessanter als we *uitzonderingen* willen beschrijven.

![embed](https://player.vimeo.com/video/287244672)

### Details

Een `if`-statement in Python kent de volgende structuur:

    if conditie:
        code

Een **voorwaarde (condition)** kent uiteindelijk maar twee mogelijke opties. In Python zijn dit `True` en `False` (dit noemen we "boolean" waardes, naar [George Boole](https://en.wikipedia.org/wiki/Boolean_algebra#Values)). In de code hierboven is deze boolean het resultaat de expressie `balance - expense > 0`. Hier wordt gebruik gemaakt van de vergelijkingsoperator `>`. Deze operator vergelijkt twee waarden, in dit geval de uitkomst van `balance - expense` en `0`, en produceert een boolean. Afhankelijk van de uitkomst, dat kan dus zijn `True` of `False`, wordt de code die bij de `if`-statement hoort uitgevoerd.

De `:` op regel 5 hierboven laat zien dat bij de `if` een **codeblok** hoort. Dat is dus precies het deel van de code dat slechts wordt uitgevoerd als aan de voorwaarde is voldaan. Zo'n blok bestaat vaak uit meerdere regels code, en om duidelijk te maken welke regels dat zijn, gebruik je **indentatie**. Dat is een aantal spaties of tabs van de kantlijn af. In de code hierboven hebben we vier spaties gebruikt om aan te geven dat regel 6 bij het `if`-statement hoort. Omdat regel 8 weer meer naar links staat, is die regel niet meer afhankelijk van de uitkomst van de conditie op regel 5. Die regel wordt dus *onvoorwaardelijk* uitgevoerd.

## Meer operatoren

Mocht je meer nodig hebben dan de vergelijkingsoperatoren hierboven:

- `==`  gelijk aan (let op: een enkele = is toekennen, een dubbele vergelijken!)
- `!=`  ongelijk aan
- `>` 	groter dan
- `>=`	groter of gelijk aan
- `<` 	kleiner dan
- `<=`	kleiner dan of gelijk aan

## Combinaties van voorwaarden

Je kunt verschillende voorwaarden combineren. Als je wilt weten of een getal zich in een bepaald bereik bevindt (bijvoorbeeld tussen de 3 en de 39) dan kun je dat doen met `and`:

    x = 15
    x_min = 3
    x_max = 39
    if x > x_min and x < x_max:
        print("het getal", x, "bevindt zich tussen", x_min, "en", x_max)

Hier zijn de drie operators om voorwaarden te combineren:

- `not` ontkenning
- `and` combinatie (allebei moeten `True` zijn)
- `or` combinatie (één van beide moet `True` zijn)
