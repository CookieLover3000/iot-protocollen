1. Copy/paste de “packet information” in je Word document”.

```
Explicit Addressing Command Frame (API 1)

7E 00 16 11 5C 00 13 A2 00 41 92 98 20 FF FE 00 00 00 31 00 00 00 00 5C 00 C8

Start delimiter: 7E
Length: 00 16 (22)
Frame type: 11 (Explicit Addressing Command Frame)
Frame ID: 5C (92)
64-bit dest. address: 00 13 A2 00 41 92 98 20
16-bit dest. address: FF FE
Source endpoint: 00
Dest. endpoint: 00
Cluster ID: 00 31
Profile ID: 00 00
Broadcast radius: 00 (0)
Transmit options: 00
RF data (HEX): 5C 00
RF data (ASCII): \
```

2. welke waarde in de frame is gewijzigd? Copy/paste de “packet information” in je Word document”.

```
Explicit Addressing Command Frame (API 1)

7E 00 16 11 8C 00 13 A2 00 41 92 98 20 FF FE 00 00 00 31 00 00 00 00 8C 00 68

Start delimiter: 7E
Length: 00 16 (22)
Frame type: 11 (Explicit Addressing Command Frame)
Frame ID: 8C (140)
64-bit dest. address: 00 13 A2 00 41 92 98 20
16-bit dest. address: FF FE
Source endpoint: 00
Dest. endpoint: 00
Cluster ID: 00 31
Profile ID: 00 00
Broadcast radius: 00 (0)
Transmit options: 00
RF data (HEX): 8C 00
RF data (ASCII): Œ
```

De waardes die zijn verandert zijn:
- RF data (HEX): 8C 00
- RF data (ASCII): Œ

3. Welke waarde moet je “AT command” en “Parameter value” geven om de LED aan te krijgen.

- AT = D2
- Parameter Value = 0x05

4. Copy/paste de “packet information” van deze frame in je Word-document Laat de docent zien dat je de LED aan/uit kunnen zetten

```
Remote AT Command Request (API 1)

7E 00 10 17 01 00 13 A2 00 41 92 98 20 FF FE 02 44 32 04 2E

Start delimiter: 7E
Length: 00 10 (16)
Frame type: 17 (Remote AT Command Request)
Frame ID: 01 (1)
64-bit dest. address: 00 13 A2 00 41 92 98 20
16-bit dest. address: FF FE
Command options: 02
AT Command: 44 32 (D2)
Parameter: 04
Checksum: 2E
```

5. Geef in je Word-document duidelijk aan welke instellingen je hebt gewijzigd. Zet nu de LED weer aan of uit.

- SM (Sleep Mode) = 0x04
- SP (sleep time) = 0x7D0
- ST (wake time) = 0xFA
- IR (IO Sampling Rate) = 0xC8
- SO (Sleep options) = 0x01

6. Verklaar waarom de LED niet direct of soms helemaal niet aangaat.

    Dit komt omdat de ZED meestal slaapt en dus geen berichten kan ontvangen in die tijd.

7. Welke parameter heb je aan moeten passen om het led altijd te laten werken?

    Hiervoor moet je ST (Wake Time) aanpassen naar 0x7D0 op de coördinator.