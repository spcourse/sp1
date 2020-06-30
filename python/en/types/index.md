# Data types

Python kent verschillende datatypes om mee te werken. `string`s en `int`s heb je al voorbij zien komen. Zo zijn `string`s rijtjes van "letters" (of andere tekens) en `int`s zijn gehele getalen. Afhankelijk van het datatype waar je mee werkt, kun je verschillende operaties doen. Kijk maar naar de operatie `*`:

- `3 * 5` geeft `15` (het resultaat is een integer)
- `"vijf" * 5` geeft `"vijfvijfvijfvijfvijf"` (het resultaat is een string)

En de operatie `-`:

- `9 - 4` geeft `5` (wederom een integer)
- `"negen" - 4` geeft een foutmelding!

Niet elke operatie kan dus met alle verschillende datatypes omgaan, en afhankelijk van het type komt er een ander soort resultaat uit. 

Naast integers zijn er ook floating-point-getallen (`float`s). Hiermee kunnen we dus kommagetallen gebruiken in Python. De meeste rekenkundige operaties kun je ook met floats doen: `3.0 / 2.0` geeft `1.5`.

Kijken we naar de interactie tussen `int`s en `float`s dan zien we iets eigenaardigs. Zo is `3 * 5` nog steeds `15`, maar is `3 * 5.0` ineens `15.0`. Ook is `1 / 2` gelijk aan `0` en `1 / 2.0` gelijk aan `0.5`. Python maakt namelijk van de uitkomst van een berekening waar zowel een `int` als een `float` in voorkomen automatisch een `float`. Vaak is dit ook wat je wilt, maar niet altijd.

Kommagetallen zijn namelijk lastig te representeren. Zou je bijvoorbeeld in ons decimaal stelsel het resultaat van `1/3` uitschrijven dan krijg je `0.3333...` tot in de oneindigheid. Hoe langer we doorgaan met het schrijven van 3-en, hoe preciezer de uitkomst van `1/3`, maar we kunnen het nooit precies opschrijven. In de binaire wereld van 0-en, en 1-en komt hetzelfde probleem voor, maar dan bij `1/10`. Dit betekent dat er ergens een compromis gesloten moet worden, en we noodgedwongen een klein afrondingsfoutje maken als we rekenen met `float`s. 

Probeer in de Python-shell maar eens de volgende regel uit: `print "%.100f" % (1.0 / 10)`. Deze regel laat Python 100 cijfers achter de komma printen. Om afrondingsfouten te voorkomen is het goed om berekeningen niet zomaar in `float`s uit te voeren! Waar mogelijk gebruik je een `int`. Je kan `float`s naar `int`s converteren door middel van de `int()` functie. Zo converteer je de `float` `4.9` naar de `int` `4` met `int(4.9)`.

# Reële getallen

We hebben geleerd dat je een geheel getal als volgt print:

    x = 100
    print "x heeft de waarde %d" % (x)

Zodra de computer de string naar het scherm print zet hij op de plek waar `%d` staat de waarde die in de variabele *x* opgeslagen staat. In ons geval 100. De vorm `%d` geeft aan dat het een *geheel* getal is.

Vaak is een variabele die je gebruikt helemaal geen geheel getal.

    breuk = 3./17.
    print "breuk = %d" % (breuk)

Als je dit print zal je zien dat, hoewel de variabele `breuk` de waarde 0.176471 heeft, dit programma toch de waarde 0 op het scherm print. Dat komt omdat je met `%d` hebt aangegeven dat je een geheel getal wil afdrukken. In Python worden dan de cijfers achter de komma simpelweg afgekapt.

Als je wilt dat de computer een reëel getal, een `float` in computertaal, print op het scherm, dan geef je dat aan met het `%f` karakter.

    breuk = 3./17.
    print "breuk = %f" % (breuk)

Nu zal wel de volledige waarde geprint worden op het scherm. In veel toepassingen wil je vaak maar een beperkt aantal decimalen weergeven. Als je 2 getallen achter de komma wilt aangeven dan gebruik je de volgende syntax:

    breuk = 3./17.
    print "breuk = %.2f" % (breuk)

Probeer een aantal opties. Net als bij het printen kan het ook misgaan als reële getallen en gehele getallen gemixt worden in je programma zelf. Lees zeker het onderstaande stukje over een van de bekende valkuilen en de manier waarop je die kan omzeilen.

> Het is handig om je probeersels op te slaan in een apart bestand, zodat je nog kunt terugkijken en stukjes code overnemen voor latere opdrachten. Dit testbestand hoef je niet in te leveren.

## Bekende valkuil: mix van gehele en reële getallen

Een veel voorkomende fout die gemaakt wordt in programma's is dat een computer denkt dat elke bewerking van gehele getallen zelf ook weer een geheel getal is. Het volgende programma zal aan de variabele z de waarde 1 toekennen, het eerste gehele getal onder de 1.3333. En dat is natuurlijk niet wat je bedoelde.

    x = 4
    y = 3
    z = x/y
    print z

Zodra een van de getallen in de wiskundige operatie een reëel getal is zal het resultaat ook een reëel getal zijn. De manier om de variabele z de waarde 1.3333 te geven is een van de variabelen (x of y of beide) een reëel getal te maken. De 2 meest gebruikte manieren om dat te doen:

Oplossing 1:

    x = 4.0
    y = 3
    z = x/y
    print z

Oplossing 2:

    x = float(4)
    y = 3
    z = x/y
    print z


## Een rij reële getallen met behulp van `numpy.arange()`

In Module 1 hebben we de for-loop gebruikt om een variabele steeds met 1 op te hogen. In de for-loop constructie gebruikten we daarvoor de `range()` functie. De getallen 1 tot (en niet tot en met) 10, printen op het scherm, ze in een lijst stoppen en die printen aan het eind van het programma deden we als volgt.

    L_x = []
    for x in range(1,10):
	   print "x heeft nu de waarde %d" % (x)
	   L_x.append(x)
	print L_x

In Module 1 hebben we tijdens het tekenen van grafieken gezien hoe we punten (een lijst met x-waardes en een lijst met y-waardes) op het scherm kunnen tekenen. Om een functie te tekenen met een hoge precisie, in ons geval sin(x) leerden we dat we als we de functie wilde tekenen tussen 0 en 2pi we kleine stapjes, stel 0.01 moeten nemen. In Python is er een standaard functie die dat voor je kan doen, de `arange()` functie. Het is een functie die opgenomen is in de numpy bibliotheek.

    import numpy as np               # numpy mdule: nodig voor arange-functie
    import math                      # math module: nodig voor sin()-functie
    L_x = []
    L_y = []
    
	# x loopt van 0 tot 2pi in stapjes van 0.01
    for x in np.arange(0,2*math.pi, 0.01):
        y = math.sin(x)
        L_x.append(x)
        L_y.append(y)		  

Als je bijvoorbeeld de getallen van 2 tot 3 op het scherm wilt printen in stapjes van 0.02 dan kan doe je dat als volgt:

    import numpy as np
	x_begin = 2
	x_eind = 3
    dx = 0.02
	for x in np.arange(x_begin, x_eind, dx):
	    print x

## Bekende valkuil: subtiel verschil tussen 'tot' en 'tot en met'

In het laatste voorbeeld zal het getal 2.0 wel, maar het getal 3.0 niet op het scherm geprint worden. In een van de opdrachten zal je wel degelijk het eindpunt moeten gebruiken. Let daarop. Probeer bovenstaande voorbeeld iets aan te passen zodat het eindpunt wel degelijk geprint wordt
