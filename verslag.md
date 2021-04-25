# Morse

## Doel en verhaal
Wanneer er voldoende energie werd opgewekt bij de vorige puzzel (fitnesstracker), wordt ook meteen duidelijk dat de Russen via morse code belangrijke informatie doorsturen. Deze informatie kan ook gebruikt worden bij de klinische testen van ónze virologen. Deze klinische testen vinden zogezegd plaats in een ruimte naast de escape room. Daarom moeten ze de morse informatie doorgeven, via een fluitje, aan de onderzoekers van de klinische testen.

Wanneer de sequentie juist werd nagefloten, zal er op een display een cijfer verschijnen én een tip voor de volgende proef. Het cijfer kan gebruikt worden bij de Alohomora-puzzel.

De bedoeling van onze puzzel is om een uitgezonden morse code na te fluiten aan de andere kant van de kamer. Een microfoonsensor zal dit geluid opvangen en het zal nagaan of het nagebootste gefluit overeenkomt met het uitgezonden ritme. Om een morse code uit te zenden maken we gebruik van een speaker. Deze speaker is geïmplementeerd in een telefoon.

Om aan de spelers te laten weten wat er juist moet gebeuren met het fluitje zal er een blad naast de micro liggen waarop, deels in morse, de uitleg staat.

## Blokschema



## Hardware
### Speaker

### Micro
Op de PCB-plaat voorzien we een aansluiting voor een externe display, een externe microfoon en een externe button. Deze 3 elementen worden via pinheaders aangesloten. Om de ESP te programmeren, wordt een extra pinheader voorzien. Aangezien de ESP32 maar 1 keer geprogrammeerd moet worden, is dit de meest efficiënte manier. 

De ESP32 zal gevoed worden met een powerbank van 5V. Deze 5V is nodig om de display aan te sturen. Via de LDO zal 5V omgezet worden naar 3.3V. De program header, de microfoon en de ESP32 worden aangesloten aan de 3.3V.

De enable butten en reset button worden voorzien van een pull-up weerstand, net zoals (?)de transmit-pin en de VSPI-pin (GIO5)(?).Vaak wordt ook een pull-up weerstand van 4k7 voorzien voor SCL en SDA aansluiting. Deze is al voorzien in de externe display, de MH-sensor (? sensor?).

De display maakt gebruik van I2C communicatie. Hiervoor maken we gebruik van de SDA- en SCL-poorten. Via de SDA-poort sturen we data van en naar de display, vanuit de ESP32. Deze 2 poorten zijn active low. Daarom werden pull-up weerstanden voorzien op het display zelf. De pull-up weerstanden moeten dus niet op onze eigen PCB aangesloten worden.

Het centrale element, ESP32, voorzien we, naast de verschillende componenten die nog volgen, ook van een LEDlichtje. Hiermee kunnen we gemakkelijk controleren of het solderen gelukt is.
<p align="center">
  <img src=https://user-images.githubusercontent.com/78847177/115971593-9707d280-a549-11eb-82d4-021c228c60fe.png>
</p>

De micro-USB voorziet een voltage van 5 volt. De andere pinnen worden niet gebruikt. De programmatie van de ESP32 gebeurt namelijk via een pinheader.
<p align="center">
  <img src=https://user-images.githubusercontent.com/78847177/115971624-c9b1cb00-a549-11eb-8010-be407baed09c.png>
</p>

De level shifters verhogen de voltage van 3.3 volt, afkomstig van de ESP32 naar 5 volt.
<p align="center">
  <img src=https://user-images.githubusercontent.com/78847177/115971693-2e6d2580-a54a-11eb-963d-52924a602175.png>
</p>


De verschillende pin headers zorgen voor de aansluiting van de externe componenten. We gebruiken mannetjes zodat de pinnen niet kunnen plooien als de PCB verplaatst wordt.
<p align="center">
  <img src=https://user-images.githubusercontent.com/78847177/115971717-62e0e180-a54a-11eb-96f8-1c58a65d20aa.png>
</p>

## Software
### Speaker
### Micro

## Communicatie
Eerst en vooral moet er gecommuniceerd worden met de vorige puzzel, de fitnesstracker, en met de volgende puzzel, 5G-proef. Wanneer de opdracht van de fitnesstracker werd volbracht, mag de speaker beginnen met het uitzenden van de morse code.
Wanneer de spelers klaar zijn met onze proef, zal er een start signaal gegeven worden naar de afstandsbediening van de 5G-proef.

Daarnaast wordt over de broker ook de juiste morse-sequentie doorgegeven door de speaker aan de microfoon. Hierdoor weet de microfoon met welke sequentie het ontvangen fluitsignaal moet vergeleken worden.

En als laatste zorgt de broker ook voor een start-, pauze- en stopsignaal. Wanneer we een pauzesignaal ontvangen, zal de button van de microfoon niet werken, de speaker zal stoppen met geluid uitzenden.


## Mogelijke errors
Mogelijke errors zijn debouncing van de button. Op voorhand hebben we verschillende buttons getest om te zien welke de meeste kans heef top debouncing. We kozen voor de button die weinig tot geen debouncing vertoonde.
Een andere factor die fout kan veroorzaken is het achtergrondgeluid. Om dit tegen te gaan, werkten we met een button die ingedrukt moet worden tijdens het fluiten. Zo weet de microfoon dat het ontvangen geluid gefluit zal zijn. Als het relatief stil is op de achtergrond, heeft de microfoon geen moeite om achtergrondgeluid te onderscheiden van het gefluit. Enkel wanneer er veel geluid is op de achtergrond, kan het zijn de microfoon foute signalen ontvangt.
