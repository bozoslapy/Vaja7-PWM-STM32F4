# Vaja7-PWM-STM32F4

ODGOVORI NA VPRAŠANJA -->

Postopek inicializacije periferije.

a) Zaženite STM32CubeIDE in ustvarite nov STM32 projekt (pod zavihkom information Center). V zavihku Board selector s pomočjo filtrov Vendor, Type in MCU/MPU Series izberite ustrezno razvojno ploščo (v našem primeru STM32F401C-Discovery), kliknite Next, projekt poimenujte vaja7_PWM in kliknite Finish (na možnosti opcije za prenastavitev periferije izberite Yes, izbrana naj bo tudi opcija perspektive za STM32CubeMX).

b) V levem Pinout oknu razširite nabor možnosti za Timers ter za časovnik TIM1. Clock Source nastavite kot Internal Clock. Prvi kanal aktivirajte kot PWM Generation CH1. Kateri pin ste omogočili? __________. Kaj se izpiše poleg pina? ___________.

c) V Clock Configuration spremenimo takt časovnika APB1 Timer Clocks (MHz) na 16 MHz.

d) V Oknu Configuration kliknemo za TIM1 Vrednost Prescaler v zavihku Counter Settinngs določite tako, da bo časovnik delal s frekvenco 1 MHz. Koliko je vrednost Perscaler (namig; delitelj) ? _________________.

e) Parameter Counter Period nastavimo na 100 in s tem še dodatno znižamo takt časovnika. Koliko znaša sedaj? __________kHz.

f) V PWM Generation Chanel nastavite Pulse (16 bits value) na 50. Kaj pomeni ta parameter? Namig – največja vrednost je lahko 100 odstotkov (znak za odstotek v polja ne pišemo).

g) Na izbrani izhodni PWM pin priključite sondo osciloskopa (ne pozabite sondo ozemljiti na GND). Vključite osciloskop in ustrezno nastavite merilno območje za x in y os.

h) Sedaj generirajte kodo tako, da enostavno kliknete ikono Save in po potrebi še enkrat potrdimo generiranje kode.

3. Programiranje v IDE:

a) V skrajno levem oknu Project Explorer poiščemo main.c datoteko pod Core à Src à main.c (dvokliknite na datoteko, odpre se tekstovni urejevalnik za main.c).

b) Poiščite prenastavljeni parameter Pulse (ki je 50) v vaši kodi in prepišite ukaz, ki ga je generiral CubeMX: ________________________________________.

c) V User code begin 2 inicializiramo časovnik za PWM z ukazom:

HAL_TIM_PWM_Start(&TIM_HANDLE_TYPE, TIM_CHANNEL_1);

Ime tega paramtera boste našli v vrstici pod Private variables ----. Del zgornje kode v rdečem torej zamenjajte z imenom te ročice (TIM_HandleTypeDef XXXX; ). Drugi parameter je izbana številka kanala za generiranje PWM signala.

d) V User code begin 4 ne napišemo ničesar!!!

4. Naložitev kode (Run) in opazovanje delovanja:

a) Kodo preverite s tipko Build (ikona za kladivce - Debug). Ko je preverjanje končano lahko preverimo, če smo med pisnjem kode naredili kakšno napako sintakse, sicer se pod kodo v oknu Console izpiše 0 errors.

b) Priklopite STM32F4Discovery na vaš računalnik preko USB kabla.

c) S tipko Run (zelena ikona za play – Run as STM…) prenesete program na STM32F0Discovery.

d) V oknu Edit Configuration kliknemo OK. Nekaj sekund bo na ploščici STM izmenično utripala zelena in rdeča LED, ko je program naložen, sveti LED rdeče.

a) Z osciloskopom preverite izhodni signal (uporabite sondo za priklop na ustrezni pin, ne pozabite na GND) in delovanje posnemite s telefonom (MP4 datoteka).

5. Dodatne nastavitve kode v programu IDE:

a) V kodi spremenite vrednost širine pulza na 25 %. Zapišite popravljeni ukaz v kodi:

______________________________________ . Ponovno naložite program in s telefonom posnemite signal na zaslonu osciloskopa.

b) V User code begin 1 deklariramo spremenljivko :

uint16_t dutyCycle = 10;

V User code begin 3 prepišemo naslednje ukaze:

htim1.Instance->CCR1 = dutyCycle;

dutyCycle+=10;

if(dutyCycle>90) dutyCycle=10;

HAL_Delay(1000);

Ponovno naložite program in s telefonom posnamite signal na zaslonu osciloskopa.

Zapišite kaj počnejo ukazi v 1.,2. in 3. vrstici (v user code begin 3):

1. ___________________________________________________________________________ ___________________________________________________________________________ ___________________________________________________________________________

2. ___________________________________________________________________________ ___________________________________________________________________________ ___________________________________________________________________________

3. ___________________________________________________________________________ ___________________________________________________________________________ ___________________________________________________________________________

KOMENTAR NA DELOVANJE --> 

![Pinout mikroprocesorja]()
![Slika vezave]()
![Slika na osciloskopu]()
![Tim1_del1]()
![Tim1_del2 ]()
![Video 1]()
![Video 2]()
![Video 3]()
