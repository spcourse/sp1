# Onderling-priem

Schrijf een programma `onderlingpriem.py` dat de kans berekent dat twee willekeurig gehele getallen geen gemeenschappelijke deler hebben. Zo'n paar wordt **onderling-priem** genoemd. De Engelse term daarvoor is **coprime**.

    #python onderlingpriem.py
    De kans dat twee random getallen geen gemeenschappelijke deler hebben is:
        - voorspelling (wiskunde): 0.xxx
	    - empirisch (Python): 0.xxx 

Hoewel we jullie in deze extra opdrachten zoveel mogelijk vrij willen laten (er is ook geen `checkpy`) zullen we voor deze eerste extra opdracht nog een aantal tussenstappen aangeven. 

### Definitie van onderling-priem en voorspelling vanuit getaltheorie
	    
In de informatie over de definitie van [co-primes](https://en.wikipedia.org/wiki/Coprime_integers) op wikipedia lezen we dat we kunnen uitrekenen wat de kans is dat *n* willekeurige getallen géén gemeenschappelijke deler hebben. 

Deze kans is: $$1/\zeta(n)$$, waarbij $$\zeta(n)$$ de beroemde [Riemann zeta functie](https://en.wikipedia.org/wiki/Riemann_zeta_function) is.

**Specifiek geval: twee getallen (n=2)**:

De kans dat twee willekeurige getallen géén gemeenschappelijke deler hebben is: 

$$1/\zeta(2) \approx 0,608$$.

In deze opdracht gaan we controleren of dit wel klopt. We gaan eerst uitzoeken hoe we kunnen bepalen of twee getallen een gemeenschappelijke deler hebben en door dit daarna voor een groot aantal willekeurige getallen-paren te doen kunnen we de kans bepalen dat twee van zulke getallen onderling-priem zullen zijn. En daarmee controleren of de voorspelling uit de getaltheorie wel of niet klopt.

### Zelf de oplossing vinden

Er zijn verschillende manieren om dit problem aan te pakken. Volg voor deze opdracht de onderstaande oplossingsmethode en tussenstappen, omdat we daarmee tijdens het nakijken goed kunnen zien hoe ver je bent gekomen.

#### stap 1: lijst met priemfactoren

Elk getal is op een unieke manier te schrijven als het product van priemgetallen:

        34 = 2 x 17
        88 = 2 x 2 x 2 x 11
     79220 = 2 x 2 x 5 x 17 x 233

Schrijf een functie `PriemFactoren(getal)` die voor een bepaald getal de lijst met de priemfactoren (de delers) vindt en op het scherm kan printen.

    python> Priemfactoren(79220) 
            Priemfactoren  79220  =  [2, 2, 5, 17, 233]

Zorg ook dat de functie de lijst met priemgetallen als output teruggeeft (als return). In de rest van het programma zullen we deze functie meer gaan gebruiken
 
#### stap 2: op zoek naar gemeenschappelijke delers van twee getallen

Schrijf een functie `AantalDelers(n1, n2)` die voor twee getallen aangeeft of er een gemeenschappelijke deler is of niet. Gebruik hierbij de functie `Priemfactoren()` om voor elk van de getallen eerst de priemfactor-lijst te vinden en ga vervolgens op zoek naar getallen die in beide lijsten voorkomen.

Op dit moment is het niet van belang om het precieze aantal gemeenschappelijke delers te bepalen. Voor deze opgave is het alleen belangrijk om te weten of er *géén* gemeenschappelijke delers zijn. De functie moet dan als return argument 0 teruggeven.

#### stap 3: hypothese testen voor groot aantal paren

Om de fractie van paren te bepalen waarin er geen gemeenschappelijke deler is moeten we:

   1. een groot aantal getallen-paren maken (willekeurig)

   2. voor elk getallen-paar kijken of er wel of niet een gemeenschappelijke deler is

   3. evalueren welke fractie van de getallen-paren geen gemeenschappelijke deler had  

Maak een functie `Experiment()` die deze stappen implementeert en die deze fractie op het scherm print en ook teruggeeft als return argument.

Specificaties:

    - gebruik getallen (n1 en n2) tussen de 10.000 en 100.000

    - gebruik 10.000 getallen-paren


**Python tip:**

Een van de dingen die we nodig hebben, het trekken van een willekeurig getal, is iets waar we pas in module 2 mee gaan werken. In dit geval is het nog specifieker, namelijk een willekeurig *geheel* getal. 

Plaats bovenaan je programma de volgende regel die je in staat stelt de `random-bibliotheek` te gebruiken in je programma. Deze bibliotheek bevat allerlei functies die random getallen maken.
 
        from random import *
        
De functie die wij nodig hebben is `randint(Nmin,Nmax)` die een random geheel getal teruggeeft tussen `Nmin` en `Nmax`. In onze opgave gebruiken we Nmin=10000 en Nmax = 100000. Om in je code een random geheel getal `n` te krijgen gebruik je de volgende regel: 

         n = randint(Nmin, Nmax)        
        

#### stap 4: theoretische voorspelling

Schrijf een functie `Voorspelling(n)` die de theoretisch voorspelde kans uitrekent dat er geen gemeenschappelijke deler is voor `n` getallen. Dit is niet veel meer dan zelf de Riemann zeta functie uitrekenen en daarmee de kans bepalen. Geef deze kans terug als returnwaarde.

#### stap 5: Gooi alles bij elkaar

Door nou de twee functies `Experiment()` en `Voorspelling()` aan te roepen valt alles samen. Op het scherm moet dan verschijnen (met drie decimalen):

    De kans dat twee random getallen geen gemeenschappelijke deler hebben is:
        - voorspelling (wiskunde): 0.xxx 
        - empirisch (Python): 0.xxx

## Checkpy

Er is voor deze opdracht geen checkpy oplossing aanwezig. You're on your own.
