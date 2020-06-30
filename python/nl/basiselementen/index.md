# Basiselementen

Een **programma** is een reeks instructies die specificeren hoe een bewerking gedaan moet worden. Zo'n bewerking kan wiskundig zijn, zoals het oplossen van een stelsel vergelijkingen, of het vinden van de nulpunten van een polynoom. Maar het kan ook om een symbolische bewerking gaan, zoals het zoeken en vervangen van tekst in een document.

Hoewel de details verschillen, is er een beperkt aantal **instructies** dat in feite voorkomt in elke programmeertaal:

gegevensinvoer (input)
: Verkrijgen van gegevens van het toetsenbord, uit een bestand of bijvoorbeeld via het internet.

gegevensuitvoer (output)
: Laten zien van gegevens op het scherm, wegschrijven naar een databestand of op een andere manier.

berekeningen
: Uitvoeren van basale wiskundige bewerkingen zoals optellen en vermenigvuldigen.

voorwaardelijke actie (conditional execution)
: Controleren of aan een voorwaarde voldaan wordt en afhankelijk daarvan de juiste code uitvoeren.

herhaling (repetition)
: Een actie herhaaldelijk verrichten, vaak met wat variatie.

En geloof het of niet, maar dat is zo'n beetje alles wat je nodig hebt. Elk programma dat je ooit gebruikt hebt op de computer, hoe ingewikkeld ook, bestaat in de basis uit instructies van deze soort. **Programmeren** kun je zien als het opdelen van een grote, complexe taak in steeds kleinere subtaakjes, tot je een programma kunt **implementeren** in een programmeertaal, opgebouwd uit bovenstaande vijf elementen.

Hieronder vind je enkele van deze elementen zoals je ze in Python kunt terugvinden. De oplossing voor de eerste opdracht kun je straks met behulp van deze elementen implementeren.

# Printen

Als je een programma hebt geschreven kun je het uitvoeren (*runnen*). De computer loopt dan stap voor stap door je programma en voert de instructies uit die op elke regel staan.

Maak tekstbestand **oefening.py** (weet je nog hoe?) en zet er de volgende regels in:

    print("Hallo, wereld!")
    print("Hee, hallo daar.")
    print("Zo tikt het lekker door.")
    print("Grappig")
    print('Hee, print dit nog?')
    print("Ivo's computer doet het vandaag niet.")
    print('Hij zei: "Hallo."')

> Oefenen doe je in deze cursus door de voorbeelden letterlijk over te tikken. Gebruik niet de *copy-paste* functie, want dan maak je geen fouten en dan leer je veel minder. Tik dus alle voorbeelden over en verbeter ze als je een foutmelding krijgt!

Start nu het programma door in de Terminal in te geven:

    python oefening.py

Wat komt er uit? Heb je nog tikfouten gemaakt? En heb je gezien dat de aanhalingstekens soms verschillen? Je moet de reeks letters achter `print` starten en eindigen met aanhalingstekens (enkele of dubbele). Zo'n reeks noemen we een **string**.

We kunnen ook meerdere waarden op één regel printen. Standaard voegt het `print`-commando een **ENTER** toe aan de tekst, zodat de volgende `print` op een nieuwe regel doorgaat. Je kunt ook zorgen dat deze **ENTER** weggelaten wordt:

    print("De temperatuur is", end="")
    print(8, end="")
    print("graden")

Daarmee wordt de hele boodschap keurig op één regel geprint. Probeer vooral uit!

Je kan dit ook bereiken door meerdere waarden in één printstatement te stoppen:

    print("De temperatuur is", 8, "graden")

## Berekeningen

Voeg vervolgens ook nog de volgende regels toe:

    print(1)
    print(1 + 1)
    print(1 + 1 + 1)
    print(3 + 2)
    print(8)
    print(5 + 8 + 8 - 8)
    print("5 + 8 + 8 - 8")

Je kunt dus ook rekenen. Het *resultaat* van de berekening wordt naar het scherm geprint. Behalve die laatste dan: daar staat de formule (*expressie*) tussen aanhalingstekens. Net als hierboven bij de tekstjes. Dat is dus een string en geen formule die berekend kan worden.

> Krijg je een foutmelding als je je programma uitvoert? Dan is de kans groot dat je een tikfout hebt gemaakt waardoor Python niet meer begrijpt wat de bedoeling is. Kijk goed waar je de fout hebt gemaakt en probeer deze op te lossen. Kom je er niet uit, vraag dan vooral om hulp. Foutmeldingen leren begrijpen is een belangrijk onderdeel van deze cursus. Dat is ook waarom we heel graag willen dat je tijdens het oefenen fouten maakt!

## Operators

Hieronder vind je een lijstje van operators die je kunt gebruiken om formules samen te stellen.

| operator | uitleg                    |  
| -------- | ------------------------- |  
| `1 + 2`  | optellen                  |  
| `2 - 1`  | aftrekken                 |  
| `1 * 2`  | vermenigvuldigen          |  
| `2 / 1`  | delen                     |  
| `2 // 1` | delen van gehele getallen |  
| `2 % 1`  | modulus (rest bij deling) |  
| `2 ** 1` | machtsverheffen           |  

Let op: als je twee gehele getallen deelt met de `//`-operator, zal er altijd een geheel getal uitkomen. Dan is `3 // 2` niet `1.5`, maar `1`. Dat is waarom de `%`-operator er mooi bijpast; die geeft de "rest", ofwel wat overblijft.

# Variabelen

Een **waarde** is een van de basale onderdelen in een programma. In de voorbeelden hierboven heb je bijvoorbeeld al reeksen letters en ook cijfers gezien. Tot nu toe zijn we alleen bezig geweest met **constante waarden**, die bij het schrijven van het programma al uitgespeld worden (in het bovenstaande geval ging het bijvoorbeeld om een tekstje `"Hello, world!"`). Maar als we bij het programmeren al weten wat het antwoord wordt, dan hebben we natuurlijk eigenlijk geen computer nodig! Laten we dus doen waar computers goed in zijn: rekenen.

Om resultaten van berekeningen te kunnen gebruiken in andere berekeningen, moeten we deze tijdelijk op zien te slaan. Als oplossing laat Python je namen toekennen aan waardes. Deze naam-waarde combinaties noemen we **variabelen**. Door middel van de `=` operator kunnen we een naam toekennen aan een waarde, en deze vervolgens ergens anders gebruiken.

![embed](https://player.vimeo.com/video/287248523)

## Types

Er zijn verschillende soorten waardes in Python; we noemen dat een **type**. In de tabel zie je drie belangrijke types:

| voorbeeld         | type  |                                                          |  
| ----------------- | ----- | -------------------------------------------------------- |  
| `'Hello, World!'` | str   | een reeks letters: een **string**                        |  
| `'3.2'`           | str   | wederom een string, want er staan aanhalingstekens       |  
| `17`              | int   | een geheel getal: een **integer**                        |  
| `3.2`             | float | een kommagetal: een **float**, een floating point number |  

Je kunt waarden ook **converteren** van het ene naar het andere type. Gebruik bijvoorbeeld `int()` om een waarde naar een integer om te zetten. Tenminste, als het kan, want anders wordt er geklaagd:

| conversie                 | resultaat                                                      |  
| ------------------------- | -------------------------------------------------------------- |  
| `print(int('32'))`        | `32`                                                           |  
| `print(int('Hello'))`     | `ValueError: invalid literal for int(): Hello`                 |  
| `print(int(3.99999))`     | `3` (let op! geen error, maar er gaat wel informatie verloren) |  
| `print(int(-2.3))`        | `-2`                                                           |  
| `print(float(32))`        | `32.0`                                                         |  
| `print(float('3.14159'))` | `3.14159`                                                      |  
| `print(str(32))`          | `'32'`                                                         |  
| `print(str(3.14159))`     | `'3.14159'`                                                    |  

Is het trouwens opgevallen dat kommagetallen op z'n Amerikaans worden geschreven? Met een punt dus! Dit is in vrijwel alle programmeertalen het geval.

# Invoer door een gebruiker

Behalve printen naar een gebruiker van jouw programma, kun je ook om invoer van een gebruiker vragen. Zo kun je **interactieve programma's** schrijven die op basis van gebruikersinvoer berekeningen doen. In Python zijn er verschillende functies om om invoer te vragen. Eén daarvan is `input()`, en deze gebruik je zoals hieronder:

    voornaam = input("Geef je voornaam: ")
    print("Hallo,", voornaam)

De string `"Geef je voornaam: "` die achter de functie `input` staat, zorgt dat meteen een bericht op het scherm wordt geprint. Dan wacht `input` totdat de gebruiker iets invult en op **enter** drukt. Wat de gebruiker heeft ingevuld krijgt nu een naam. In het voorbeeld hierboven wordt de invoer aan de naam `voornaam` gekoppeld. Op de volgende regel wordt de waarde van `voornaam` weer uitgeprint.

Nu komt uit `input` altijd een string. Maar soms wil je natuurlijk dat de gebruiker een getal invoert om daar een berekening mee te doen. Dan kun je de conversie-functies van hierboven gebruiken. Bijvoorbeeld:

    aantal_stoelen = input("Hoeveel stoelen moeten gereserveerd worden? ")
    aantal_stoelen = int(aantal_stoelen)

# Format

We hebben al gezien hoe je variabelen kan printen. Bijvoorbeeld:

    temperature = 1000
    print("De temperatuur is", temperature, "graden.")

Je kan dit ook op een andere manier te doen:

    print("De temperatuur is {} graden.".format(temperature))

De accolades, `{}`, in de string geven aan dat er nog een waarde ingevuld moet worden. Met `format` geef je vervolgens aan welke waarde dat moet zijn.

Dit kan vooral handig zijn voor het printen van meerdere variabelen:

    temperature = 1000
    pressure = 1.013
    print("Het is {} graden en de luchtdruk is {} bar.".format(temperature, pressure))

In dit geval zijn er twee placeholders, `{}`, die door `format` worden ingevuld.

# Commentaar

Als je in één bestand redelijk wat Python-code hebt geschreven, dan is het handig om duidelijk te maken *wat waar staat* (voor de lezer van de code zelf, niet voor de gebruiker van het programma). Daarom kun je regels commentaar toevoegen in je code. Die zien er zo uit:

    # berekening
    x = x + 1

of

    # uitvoer
    print(x)

Met zo'n hekje (`#`) laat je zien dat het geen instructie betreft, maar een stukje tekst waar de computer niets mee hoeft te doen. Het is gebruikelijk om een regeltje commentaar te zetten *boven* het stuk code waar het naar verwijst.

Naast commentaar voor een stukje code is het ook handig om helemaal bovenaan een bestand duidelijk te vermelden waar het voor dient. Voor **oefening.py** kun je denken aan het volgende:

    # Oefeningen met Python module 1
    # M. Stegeman
    # 24-8-2018

Voeg nu commentaar toe aan je bestand. Maak steeds met een regeltje commentaar duidelijk wat de verschillende onderdelen van je bestand doen.

Dat was het voor nu! Op naar de eerste opdracht.
