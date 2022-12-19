# Vaja7-PWM-STM32F4

ODGOVORI NA VPRAŠANJA -->

b) V levem Pinout oknu razširite nabor možnosti za Timers ter za časovnik TIM1. Clock Source nastavite kot Internal Clock. Prvi kanal aktivirajte kot PWM Generation CH1. 
--> Kateri pin ste omogočili?  PE9
--> Kaj se izpiše poleg pina?  TIM1_CH1.

d) V Oknu Configuration kliknemo za TIM1 Vrednost Prescaler v zavihku Counter Settinngs določite tako, da bo časovnik delal s frekvenco 1 MHz.
--> Koliko je vrednost Perscaler (namig; delitelj) ?  16.

e) Parameter Counter Period nastavimo na 100 in s tem še dodatno znižamo takt časovnika.
--> Koliko znaša sedaj?  100kHz.

f) V PWM Generation Chanel nastavite Pulse (16 bits value) na 50. Kaj pomeni ta parameter? Namig – največja vrednost je lahko 100 odstotkov (znak za odstotek v polja ne pišemo).
--> Parameter spreminja dolžino periode.

3. Programiranje v IDE:

b) Poiščite prenastavljeni parameter Pulse (ki je 50) v vaši kodi in prepišite ukaz, ki ga je generiral CubeMX:
--> uint16_t dutyCycle

5. Dodatne nastavitve kode v programu IDE:
a) V kodi spremenite vrednost širine pulza na 25 %. Zapišite popravljeni ukaz v kodi:
--> sConfigOC.Pulse = x;
--> sConfigOC.Pulse = 25;

Zapišite kaj počnejo ukazi v 1.,2. in 3. vrstici (v user code begin 3):

--> 1. Pošlje signal na pin.
--> 2. Poveča dutyCycle za 10.
--> 3. Previri dutyCycle nad 90 in ga spremeni za 10.

KOMENTAR NA DELOVANJE --> 

![Pinout mikroprocesorja]()
![Slika vezave]()
![Slika na osciloskopu]()
![Tim1_del1]()
![Tim1_del2 ]()
![Video 1]()
![Video 2]()
![Video 3]()
