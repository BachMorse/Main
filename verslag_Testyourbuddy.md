
# Specificaties
## Gewenste functionaliteit
De speaker zendt een morse code uit met een bepaalde sequentie. Deze sequentie wordt voorafgegaan door een hoge toon. 
De microfoon detecteert geluid van zodra de button wordt ingedrukt.
De speaker hangt vast, er kan dus niet rondgelopen worden met de telefoon. De microfoon staat aan de andere kant van de kamer, in een behuizing.
De speler(s) zullen eerst goed moeten luisteren naar de telefoon, waaruit de sequentie wordt verstuurd. 
Daarna zullen ze deze sequentie moeten nafluiten. Het is dus de bedoeling dat de 2 spelers goed communiceren, óf dat 1 speler de sequentie onthoudt.
Idealiter luistert er 1 iemand naar de telefoon, en kan deze persoon de sequentie nazeggen. 
Van het zoeken naar de telefoon tot de tip die ze ontvangen wanneer de juiste sequentie werd nagedaan, rekenen we 10 minuten.

## Scope
Wat kan getest worden:

    - Juiste sequentie fluiten
    - Foute sequentie fluiten (er zal geen tip verschijnen)
    - Button indrukken en weer loslaten (al het vorige wordt gewist)
    - Signalen doorsturen via broker


## Mogelijke problemen
Mogelijke problemen zijn het achtergrondgeluid dat de sequentie verstoord.
Het kan ook zijn dat de sequentie te lang wordt en dat het onmogelijk blijkt om deze te onthouden/door te zeggen.
