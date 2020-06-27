# Spiraal

Schrijf een programma dat een spiraliserende stip animeert met behulp van Matplotlib. De stip draait met een bepaalde hoeksnelheid rond en met elke stap in de tijd verandert niet alleen de hoek, maar wordt ook de straal steeds kleiner tot hij uiteindelijk precies in het midden stilstaat:

![](AnimationInspiral.gif)

## Specificatie

Schrijf een programma `spiraal.py` waarin de stip geanimeerd wordt zoals hierboven beschreven.

## Hints

Poolcoordinaten: een punt kan worden beschreven middels de coordinaten $$(x,y)$$, maar je
kunt ook twee andere variabelen gebruiken ($$\alpha$$,R), waarbij $$\alpha$$ de
hoek is met de positieve $$x$$-as en $$R$$ de afstand tot de oorsprong. De
variabelen kunnen in elkaar omgeschreven worden zoals in de volgende grafiek is
aangegeven.

![](UitlegPolarCoordinates.png)

Details voor de animatie:

- hoek $$\alpha$$ varieert van $$0$$ tot $$20$$ radialen in stappen van $$0.1$$
- straal $$R$$ hangt af van $$\alpha$$, namelijk $$R=10-0.5\alpha$$

## Testen

Dit programma is helemaal visueel en kan niet worden getest met `checkpy`. Je moet het laten aftekenen tijdens het practicum.
