# Online programmeren

Om online te kunnen programmeren maken wij gebruik van een online integrated development environment, de CS50 IDE. Om toegang te krijgen tot deze omgeving moet je wat stappen door. Daarna kun je gelijk aan de slag!

## Aanmaken van de CS50 IDE

> Op dit moment werkt de CS50 IDE alleen goed in Chrome en FireFox, en niet in Safari. Mocht je een leeg scherm te zien krijgen, probeer dan even van browser te wisselen.

Zorg dat je een GitHub-account hebt!

Ga vervolgens naar <https://ide.cs50.io/>. Je zal eerst worden doorverwezen naar GitHub, waar je moet inloggen met het account dat je hebt aangemaakt. Je zal gevraagd worden toestemming te geven bepaalde informatie door te sturen naar CS50. Maak je geen zorgen! CS50 is een vak van Harvard en ze zullen je niet lastigvallen met spam.

Na het aanmaken van de omgeving, zie je dit scherm in jouw browser:

![cs50](cs50.png)

We noemen dit een "ontwikkelomgeving", omdat je hier alles vindt wat je nodig hebt om programma's te ontwikkelen: een overzicht van je bestanden, een tekst-editor om programma-code in te tikken, en een plek om je programma's uit te proberen.

## Proefrit

Links bovenin zie je een map-icoontje met daarachter de tekst **~/**. Rechtsklik of ctrl+klik hierop en selecteer vervolgens **New Folder**. Noem deze map **week1**.

Onderin het scherm zie je de terminal, een omgeving waarin je commando's kan uitvoeren. Tik maar eens het volgende commando in achter de `$`:

    ls

Het commando `ls` is een afkorting van list. Dit commando geeft een lijst van alle bestanden en mappen in de "huidige" map. Standaard begint de terminal in de map `~/`, en door het uitvoeren van het commando `ls` zie je alleen de map `week1` die je net hebt aangemaakt. Laten we nu de "huidige map" veranderen door middel van het volgende commando:

    cd week1

Het commando `cd` is hier een afkorting van compact disc... uh, nee... *change directory*. Hiermee open je een andere directory in je terminal (in je terminal moet je alles intikken, zoals je merkt, in plaats van klikken met de muis). Als je dit intikt dan is je terminal gewisseld naar een andere map, in dit geval `week1`. Zou je nu `ls` nog een keer uitvoeren, dan zijn er geen resultaten (je krijgt dan ook letterlijk geen zichtbare resultaten). Laten we hier verandering in brengen door middel van het volgende commando:

    touch hello.py

Het commando `touch` kijkt of een bestand bestaat, en zo niet, dan wordt het bestand aangemaakt. Nu hebben we een bestand genaamd `hello.py` binnen de map `week1`. Gebruik nog een keer `ls` om dit te controleren.

Om de file `hello.py` te openen, ga je naar links bovenin je scherm waar je een map-icoontje ziet gevolgd door de tekst `~/`. Druk op het driehoekje ernaast om de map `~/` uit te klappen. Doe vervolgens hetzelfde bij de map `week1`, en dubbelklik dan op de file `hello.py`. Nu opent er een nieuwe tab genaamd `hello.py` en kunnen we meteen beginnen met programmeren!

Voer in het bestand `hello.py` de volgende regel code in:

    print("Hello, World!")

Sla `hello.py` vervolgens op. Dit is jouw eerste (Python-)programma, en deze kunnen we uitvoeren door het volgende commando in de terminal te voeren:

    python hello.py

Als het goed is zie je direct daaronder de woorden: `Hello, World!` staan.

## Extra tips

Handig om te weten is dat je via het commando `cd` ook een map "omhoog" kan via:

    cd ..

Hier staat `..` voor de map boven de huidige. Wil je verder omhoog? Dan kan dat via `../..`. Je kunt ook in één keer aangeven welke map je wil openen. Bijvoorbeeld:

    cd ~/week1

Dat brengt je meteen naar de map `week1` binnen `~/`.

## Installeren van Matplotlib en Checkpy

We gebruiken een programma om te checken of je opdrachten op de juiste manier werken. We vragen je om heel precies te zijn in het geven van de juiste uitvoer. Hiervoor hebben wij een programma geschreven dat `checkpy` heet en dit wordt niet standaard meegeleverd met de online ontwikkelomgeving. Daarnaast gaan we aan de slag met het plotten van grafieken, en hiervoor hebben we een Python module nodig genaamd `matplotlib`. Ook deze moeten we apart downloaden.

Om zowel `matplotlib` en `checkpy` te downloaden voer je in de terminal één voor één de volgende commando's uit:

    pip install matplotlib
    echo "backend : TkAgg" >> ~/.local/lib/python3.7/site-packages/matplotlib/mpl-data/matplotlibrc
    pip install checkpy
    checkpy -d uva/progns

Het kan best eventjes duren per commando, en er zal aardig wat tekst over je scherm ratelen (behalve bij het commando startend met `echo`). Mocht er weinig tekst staan, speur dan naar een eventuele foutmelding en vraag eventueel om hulp!

Om te testen of alles werkt, en of `hello.py` klopt, voer je het volgende commando in de terminal uit:

    checkpy hello

Kleurt alles groen en zie je alleen maar vrolijke smileys? Dan zit je goed, en heb je aan onze eisen voor de opdracht voldaan! Mocht er iets rood kleuren, geen paniek! Kijk goed na of je precies hebt gedaan wat er is gevraagd, en vraag gerust als je klem zit.
