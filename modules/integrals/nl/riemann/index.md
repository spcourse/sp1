# Riemann

Schrijf een functie die met behulp van een Riemann-som de integraal berekent van een willekeurige wiskundige functie met gespecificeerde integratiegrenzen. De wiskundige functie moet ook op het scherm weergeven worden.

## Achtergrond

Een van de manieren om een integraal te evalueren is door het te schrijven als de som van kleine rechthoekjes, de Riemannsom. Stel, het gaat om de volgende integraal:

$$ \int_a^b f(x)~dx $$

Dit gaat als volgt: verdeel het interval $$(a,b)$$ in $$N$$ intervallen van gelijke lengte $$\Delta x$$ en schrijf de integraal als de som van de deel-integralen op elk van deze intervallen:

$$ \int_a^b f(x)~dx = \sum_{i=0}^{N-1} \int_{x_i}^{x_{i+1}} f(x)~dx$$

Hierbij is $$x_i$$ het hoekpunt van een van de intervallen. Er zijn $$N+1$$ hoekpunten die lopen van $$x_0$$ tot en met $$x_{N}$$. Zie de grafiek in het plaatje hieronder.

![](../../assets/RiemannExample.png)

Nu we weten dat we op zoek zijn naar een flink aantal deel-integralen, gaan we ons verdere probleem flink versimpelen, door de deel-integralen te *benaderen*.

We stellen ze voor als een rechthoek. De breedte van de rechthoek is natuurlijk 
$$\Delta x = (x_{i+1} - x_{i})$$. Een (simpele) schatting van de hoogte van het rechthoek dat het best de integraal op dit kleine interval weergeeft is simpelweg het gemiddelde te nemen van de waarde van $$f(x)$$ op de linkerkant en de rechterkant van het interval. De integraal op het deelinterval is dan te schrijven als:

$$\int_{x_i}^{x_{i+1}} f(x)~dx = \frac{f_{i+1}+f_i}{2}~\Delta x$$

De volledige integraal is dan te schrijven als:

$$\int_a^b f(x)~dx = \frac{\Delta x}{2} (f_0 + 2 f_1 + 2 f_2 + ... +  2 f_{N-1} + f_N)~+~\mathcal{O}((\Delta x)^2)\\
                       ~~ \approx \Delta~x(f_1 + f_2 + ... +  f_{N-1}) ~+~ \frac{\Delta x}{2}(f_0+f_N) $$

In de evaluatie van de integraal $$\int_{0}^{\pi}sin(x)~dx$$ hebben we het integratiegebied in $$x$$ opgedeeld in 13 gebieden van gelijke grootte. We hebben dan dus in totaal 14 x-waardes. De hoogte van elk vcan de 13 rechthoeken is het gemiddelde van de waarde aan de linkerkant en de rechterkant van het kleine integratiegebied.

De truc is de volgende: de uiteindelijke integraal kunnen we evalueren door de oppervlaktes van alle rechthoeken op te tellen. Let op dat bij de berekening van de integraal de 'oppervlaktes' van de rechthoeken onder de y-as als negatief geteld worden. Als we de intervallen steeds kleiner maken, wordt de benadering van de integraal steeds preciezer! Daarom komt het goed van pas dat we met een computer werken.

## Specificatie

- Maak een nieuw bestand genaamd `riemann.py`.

- Schrijf een functie `riemann()` die integralen kan berekenen met behulp van de Riemannsom. 

- De functie `riemann()` moet vier argumenten accepteren:

	- `func` een functie waarvan we de integraal gaan bepalen
	- `a` het begin van het gebied
	- `b` het einde van het gebied
	- `n` hoeveel rechthoeken we gebruiken om de integraal te bepalen.

- De functie `riemann()` moet de juiste waarde van de integraal teruggeven als resultaat.

- De functie `riemann()` moet de wiskundige functie op het scherm laten zien.


## Tests

Test je procedure met de volgende functie, die je makkelijk analytisch kunt controleren:

	def functie1(x):
		return x**2

Test ook met de volgende functies. Sommige daarvan zijn "integreerbaar", andere kun je alleen numeriek benaderen.

$$\int_{0}^{1}x^2 dx$$

$$\int_{0}^{1}x^{x+\frac{1}{2}} ~dx$$

$$\int_{0}^{\pi}sin(x) dx$$

$$\int_{0.2}^{2.2} \tan(\cos(\sin(x))) ~dx$$

$$\int_{0}^{\pi} \sin(x^2) ~dx$$

Zet deze functies in je eigen programma en zorg dat je onderaan een aantal keer je `riemann()`-functie aanroept, om deze voorbeelden te controleren. Zo kun je `functie1()` van hierboven meegeven aan `riemann()` door aan te roepen:

    rieman(functie1, 0, 1, 10000)

## Hints

- Let op: als je het interval in $$N$$ stukjes verdeeld zijn er $$N+1$$ hoekpunten.

- Maak een plaatje van je grafiek zodat je duidelijk ziet welk gebied je aan het integreren bent. Je kunt in je `riemann()`-functie een stukje code opnemen om de grafiek te plotten.

- Test je functie altijd eerst op een integraal waarvan je de uitkomst kent. Dit is het geval voor een aantal van de functies die hierboven staan weergegeven. Pas als jouw functie die integralen goed uitrekent kan je met vertrouwen de onbekende nieuwe integraal aanpakken.


## Debuggen

Lijkt het niet te werken? 

- Check "op het oog" met een grafiek of de integraal überhaupt in de buurt komt van wat je mag verwachten.

- Als dat wel goed zit, kan het zijn dat het aantal stappen te klein is om tot een precies genoeg antwoord te komen. Probeer het aantal te verhogen en bekijk ook hoe dit de uitkomsten beinvloedt.


## Testen

	checkpy riemann
