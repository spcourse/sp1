# Student

Als twee studenten dronken zijn en ze elkaar uit het oog verliezen wordt het erg onwaarschijnlijk dat ze elkaar nog terugvinden. Schrijf een programma dat het gedrag van twee dronken student simuleert.

![](AnimationRandomWalkDouble.gif)

## Specificatie

Schrijf een programma `student.py` waarin je de animatie van de **twee** studenten op het scherm laat zien. Geef op het scherm aan hoe lang de gebruiker van je programma nog moet wachten tot het
programma afgelopen is.

## Analyse

Een dronken student neemt elke seconde een stap. De grootte van de stap is steeds hetzelfde ($$R = 1$$), maar de richting waarin hij die stap neemt is volledig willekeurig. Kies bij elke stap in de tijd een random hoek $$\alpha$$ en bepaalt vervolgens de nieuwe $$x$$-positie en $$y$$-positie. Dit staat bekend als een *random walk*.

Je zou eens kunnen proberen of je ook met pen en papier iets kan zeggen over de gemiddelde afstand die de studenten van elkaar verwijderd zijn als functie van het aantal stappen dat ze nemen. Je hoeft dit niet in te leveren, maar overleg eens met je collega-studenten hoe je dit zou aanpakken.


## Hints

Start, om klein te beginnen, met een animatie van een enkele student:

![](AnimationRandomWalk.gif)

## Tip

Zelf een filmpje opslaan? Gebruik een tool als [GifGrabber](http://www.gifgrabber.com) om een animated gif te maken. Die kan je in een webbrowser bekijken.

## Testen

Dit programma is helemaal visueel en kan niet worden getest met `checkpy`. Je moet het laten aftekenen tijdens het practicum.
