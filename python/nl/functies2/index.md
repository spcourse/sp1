# Functies als argumenten

Het kan nuttig zijn om functies mee te geven als een argument aan een andere functie. Dit kan er, in eerste instantie, wat verwarrend uitzien. Neem het volgende voobeeld:

	def add(a, b):
		return a + b

	def mult(a, b):
		return a * b

	def repeat(my_function, x, y, z):
		total = my_function(x, y)
		total = my_function(total, z)
		return total

	added = repeat(add, 4, 3, 2)
	print(added)

	multiplied = repeat(mult, 4, 3, 2)
	print(multiplied)

Dit geeft de volgende output:

	9
	24

Hier wordt de functie `repeat()` gebruikt voor twee verschillende doeleindes. In de eerste aanroep worden alle getallen opgeteld. In de tweede aanroep worden ze vermenigvuldigd.

Het verschil in gedrag wordt bepaald door de parameter `my_function`. Deze specificeert een functie de twee keer wordt aangeroepen in `repeat`. Bij het aanroepen van `repeat` specificeren we wat `my_function` precies moet zijn. In het eerste geval is dat `add`. In het tweede geval `mult`.

In het voorbeeld worden alleen de functies `add` en `mult` gebruikt. Maar in principe zou je hier elke functie kunnen meegeven die twee getallen met elkaar combineert. Probeer zelf je eigen functies te definiëren om te gebruiken als input voor `repeat()`.

Het bovenstaande voorbeeld is een beetje kunstmatig, maar het geeft een volledig sjabloon voor het gebruik van functies als argumenten.
