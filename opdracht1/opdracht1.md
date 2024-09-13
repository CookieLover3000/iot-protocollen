1. Wat zijn de verschillen tussen een Zigbee-router een een Zigbee end-device?

    Een zigbee router is, zoals de naam zeg, een router. Dit betekent dat hij constante stroom nodig heeft en een netwerk maakt/uitbreid. Ook is dit apparaat vaak wat sterker dan een end device omdat het meer rekenkracht nodig heeft.

    Een zigbee end device daarentegen is een (vaak zwakker) apparaat dat communiceert met de router om een taak uit te voeren (bijvoorbeeld als smart thermostaat)

2.  Waar zijn de navolgende parameters voor: JV, NJ,CE, DH/DL, SM, SP, SO, OP, CH?

    JV: wordt gebruikt voor channel verificatie
    NJ: Wordt gebruikt voor het joinen van een netwerk
    CE: Stuurt aan of het apparaat een coordinator is
    DH: bestuurt of leest de hoogste 32 bits of het 64-bit destinatie adres
    DL: bestuurt of leest de lagere 32 bits of het 64-bit destinatie adres
    SM: bestuurt de sleep mode van de zigbee
    SP: bepaalt de duratie van de sleep mode
    SO: bepaalt wat het apparaat doet in sleep mode
    OP: Leest de 64-bit extended PAN ID
    CH: Kanaal nummer lezen die gebruikt wordt om data te versturen en ontvangen tussen RF apparaten

3. Wat zijn de twee operation modes van de XBee? 

    Transparent Modus
    API Modus

4. Wat is het verschil tussen de ze twee modes

    De Transparent Modus werkt als een vervanging voor de serial line terwijl de api modus werkt op een frame-based manier

5. Wat is de default operation mode van de XBee?

    transparent modus

6. Hoe wijzig je tussen de twee operation modes?

    AP 1 = api modus
    AP 0 = transparent modus

7. Wat is de default waarde voor NJ? En wat gebeurt er als je de NJ waarde op 0xFF zet? (255 sec. is een fout antwoord!)

    3C is de default mode
    Wanneer NJ op 0xFF kan het device altijd joinen

8. Wat betekent het als je 16-bits adres 0xFFFE is?

    Het betekent dat het adres ongedefinieerd is.

9. Hoe kom je in de "command-mode" om at-commando's te geven?

    je moet `+++` invoegen en dan 1 seconde wachten

10. Welke parameters moeten minimaal gelijk zijn om twee XBees met elkaar te kunnen laten communiceren?

    PAN ID
    Channel
    DL
    DH


11. Wat is het verschil tussen de "Link key" (KY) en "Trust Center Network key" (NK)?

    Link key wordt gebruikt voor het joinen van een netwerk en de trust center network key is voor het het encrypten van de data

12. Wat is de minimale CT waarde? Hoeveel sec. is dit? Wat gebeurt er als je atct0 invoert?
    
    min: 2. Dit is 0,2 seconden
    
    Met atct0 zegt het programma error

13. Druk Alt+X in de XCTU die met de ZR verbonden is en klik Read.
Kijk naar de ‘Operating Network Parameters’.

    a. Is de ZR nu met een netwerk verbonden?

    ja

    b. Zo ja, met welk netwerk (met welke ZC)?

    Met Qing

    c. Wat is de waarde van het 16-bits netwerk adres (MY)?

    F8C8

14. Druk Alt+X in de XCTU die met de ZR verbonden is en klik Read. Kijk naar de ‘Operating Network Parameters’.

    a. Is de ZR nu met een netwerk verbonden?

    ja

    b. Zo ja, met welk netwerk (met welke ZC)?

    Met Qing

    c. Wat is de waarde van het 16-bits netwerk adres (MY)?

    F8C8

15. Bekijk het plaatje (sla het op in het word-document). Als je klaar bent: Stel in: AP : Transparant Mode [0] om weer naar de standaard modus terug te gaan.


![alt text](<netwerk.jpeg>)