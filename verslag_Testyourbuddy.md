
# Specificaties
## Gewenste functionaliteit
De speaker zendt een morse code uit met een bepaalde sequentie. Deze sequentie wordt voorafgegaan door een hoge toon. Wanneer op de button wordt gedrukt zal de morse code beginnen. De microfoon detecteert geluid van zodra de button wordt ingedrukt.

De speaker hangt vast, er kan dus niet rondgelopen worden met de telefoon. De microfoon staat aan de andere kant van de kamer, in een behuizing.

De speler(s) zullen eerst goed moeten luisteren naar de telefoon, waaruit de sequentie wordt verstuurd. Daarna zullen ze deze sequentie moeten nafluiten. Het is dus de bedoeling dat de 2 spelers goed communiceren, óf dat 1 speler de sequentie onthoudt.

Wanneer de juiste sequentie werd nagefloten verschijnt er een cijfer voor de Alohomora, en een tip voor de volgende tip (bijvoorbeeld de plaats waar de afstandsbediening ligt).

Idealiter luistert er 1 iemand naar de telefoon, en kan deze persoon de sequentie nazeggen. 

Van het zoeken naar de telefoon tot de tip die ze ontvangen wanneer de juiste sequentie werd nagedaan, rekenen we 10 minuten.

## Scope
Wat kan getest worden:


    - Juiste sequentie fluiten
    - Foute sequentie fluiten (er zal geen tip verschijnen)
    - Button indrukken en weer loslaten (al het vorige wordt gewist)
    - Signalen doorsturen via broker (tot nu toe nog niet helemaal on point)
    
    Omdat de MQTT nog niet op punt staat, kan de combinatie van de speaker en de micro niet volledig getest worden.
    
    Wat we wel graag zouden willen weten is of de lengte van de sequentie uit de speaker niet te lang/te kort is. Om dit te testen kan de puzzel worden uitgevoerd alsof de MQTT werkt, er zal geen tip verschijnen als de sequentie juist.
    
    De gefloten sequentie kan wel gecontroleerd worden adhv de letters die op Jeff zijn computerscherm verschijnen én de vertaling via de morse op het A4-papier.


## Mogelijke problemen
Mogelijke problemen zijn het achtergrondgeluid dat de sequentie verstoord. Het kan ook zijn dat de sequentie te lang wordt en dat het onmogelijk blijkt om deze te onthouden/door te zeggen. Connectie van de MQTT is ook nog niet volledig in orde, waardoor het nog niet mogelijk is om te communiceren tussen micro en speaker.

# Testing
De puzzel werd 3 keer getest op de volgende onderdelen:

    - het ontcijferen van het morse signaal (luidspreker)
    - nafluiten van het morse signaal (microfoon)
    - responsie van de display

Volgende feedback werd gegeven bij het testen van deze bovenstaande onderdelen:

Bij het fluiten van de morse sequentie is het moeilijk om korte tonen te fluiten. De duur van een kort en lang een lang signaal is soms moeilijk te onderscheiden. Daarnaast werd een visuele indicatie aangeraden wanneer een foute code werd nagefloten.

Wanneer de speaker de morse sequentie afspeelt is de tijd tussen elk beep signaal zeer kort wat het ontcijferen/nafluiten van de code wat moeilijk maakt. De deelnemers geven wel aan dat het haalbaar is wanneer de code opgeschreven kan worden. Indien dit niet toegestaan zou zijn (puur op gehoor) is het beter om dit tijdsinterval iets langer te maken.

Er is een kleine manier om de puzzel te omzeilen, namelijk door de speaker los te maken en dichtbij de speaker te houden. 

# Feedback
