# Appel

Schrijf een programma dat de beweging van een appel beschrijft als die op een hoogte van 100 meter wordt losgelaten.

    0.00 s tot de appel de grond raakt
    000.0 km/uur is de snelheid waarmee de appel de grond raakt
    0.00 s duurt het tot de appel 100 km/uur gaat


## Achtergrond

In het natuurkundig onderzoek wordt veel gewerkt met problemen die niet  analytisch, met de hand, zijn op te lossen. Toch zijn er allerlei technieken die, vaak met een omweg, voor dit soort problemen een oplossing kunnen genereren. In de meeste gevallen is zo'n techniek wel heel arbeidsintensief en worden altijd computers gebruikt om ze toe te passen.

Bij simuleren neem je stapjes in de tijd en bereken je wat er in die tijd grofweg is gebeurd: bijvoorbeeld de beweging van een object. De truc die je dan eigenlijk alleen met een computer handig kan toepassen, is dat je de tijdstapjes zó klein maakt, dat je de beweging steeds "vloeiender" aan het doorrekenen bent. Uiteindelijk beschrijft de simulatie dan bijna precies het daadwerkelijke gedrag. Tenminste, als de simulatie van de juiste aannames uit gaat!


## Specificatie

Maak een bestand `appel.py` en schrijf daarin een functie `appel()` die de benodigde berekeningen doet. Zorg dat de volgende resultaten geprint worden door deze functie:

1. Na hoeveel seconden raakt de appel de grond?

2. Met welke snelheid (km/u) raakt de appel de grond?

3. Na hoeveel seconden heeft de appel een snelheid van $$100$$ km/u bereikt? Is
    een vallende appel daarmee sneller dan Bugatti Veyron ($$2.46$$ seconden) of niet?

De uitvoer moet heel precies zijn en alleen de gevraagde waarden bevatten zoals in het voorbeeld bovenaan.


## Probleemanalyse

![](GravityOverzicht.png)

Zorg dat je programma kleine stapjes in de tijd maakt ($$\Delta t=0.01$$ seconden) en hou steeds bij op welke hoogte de appel zich bevindt ($$x$$) en met welke snelheid deze beweegt ($$v$$).

Bereken voor elke nieuw stapje in de tijd in deze volgorde:

1. de kracht $$F$$ die op de appel werkt
2. de versnelling $$a$$ die de appel daardoor krijgt
3. de nieuwe snelheid $$v$$ die de appel daardoor krijgt, waarbij $$v_{\rm nieuw} = v + a \Delta t$$
4. de nieuwe positie $$x$$ van de appel, waarbij $$x_{\rm nieuw} = x + v \Delta t$$

Stap 1 en 2 kun je combineren, waardoor je in deze simulatie niet hoeft te weten wat de massa van de appel is!

Je hebt dan alle informatie berekend over een bepaald punt in de tijd. Vervolgens kun je een stapje verder in de tijd maken en deze cyclus herhalen.


## Hints

- Gebruik bovenstaande formule en start de appel dus op x = $${\rm R_{earth}}$$ + 100 meter. Als je wilt weten hoe hoog de appel is, gebruik dan h = x - $${\rm R_{earth}}$$.
- Let goed op het *teken* van de krachten en snelheden. Je begint bij positieve $$x$$ en beweegt dan naar $$x=0$$ toe.
- In dit voorbeeld kan je de antwoorden ook zelf uitrekenen met behulp van pen en papier.
- Bereken alles eerst in m/s en reken dan voor punt 2 de snelheid om naar km/uur.


## Testen

	checkpy appel
