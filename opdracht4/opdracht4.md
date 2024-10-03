1. Geef in je eigen woorden aan wat het verschil is tussen ABP en OTAA.

Een node met ABP kan direct zenden na het aanzetten van de node. Terwijl een Node die geconfigureerd is met OTAA pas kan communiceren nadat het een Join-Accept heeft ontvangen.

2. Welk commando moet je hiervoor invoeren? (factory reset) En wat is de response van de module?

- command: `sys factoryRESET`
- response: `RN2483 1.0.5 Oct 31 2018 15:06:52`

3. Welke 3 algemene commando categorieën zijn er in de Lora module?

- System Commands
- MAC Commands
- Radio Commands

4. Welk commando moet je geven om de bronspanning van de LoRa-module uit te lezen? Doe dit, en wat is de response van de module?

- command: `sys get vdd`
- response: `3294`

5. Welk commando moet je hiervoor invoeren (dev eui)? En wat is de response van de module?

- command: `mac get deveui`
- response: `0004A30B0020D345`

6. Welk commando moet je hiervoor invoeren (appEUI)? En wat is de response van de module?

- command: `mac set appeui 1234567891234567`
- response: `ok`

7. Welk commando moet je hiervoor invoeren (appKey)? En wat is de response van de module?

- command: `mac set appkey B4AAE301FF10E76E4EDA1BB3BCEB040A`
- response: `ok`

8. Waar wordt de ‘AppKey’ voor gebruikt?

    De appkey wordt gebruikt voor het versleutelen van berichten en voor device authentication.

9. Welk commando moet je hiervoor invoeren (bewaren in EEPROM)? En wat is de response van de module.

- command: `mac save`
- response: `ok`

10. Welke mode moet je hier gebruiken?

    Hiervoor moet `OTAA` gebruikt worden

11. Wat is er nu in TTN gebeurd bij ‘Live data’ op de device overview pagina?

    Daar is het join request komen te staan: 
![alt text](image.png)

12. Waarvoor en wanneer wordt het “Device Address” gebruikt?

    Het 'Device Address' wordt gebruikt voor het identificeren van de LoRaWan module en wordt gebruikt tijdens het versturen van berichten.

13. Waarvoor en wanneer wordt de “Network Session Key” gebruikt?

    De 'network session key' wordt gebruikt voor het berekenen en verifiëren van de 'Message Integrity Code' (bericht integriteit) en voor encryptie en decryptie van data tussen de node en de netwerkserver.

14. Waarvoor en wanneer wordt de “App Session Key” gebruikt?

    De 'App Session Key' wordt gebruikt voor encryptie en decryptie van data tussen de node en de applicatie server.

15. Leg nu eens in je eigen woorden uit hoe de data van de LoRa module op The Things Network is terechtgekomen?

    de node stuurt een bericht richting de gateway die dit doorstuurt naar de netwerk server, die dan het bericht weer doorstuurt naar de applicatieserver.

16. Kijk nu bij TTN op tabblad ‘Live data’ en klik op de regel uit met de ‘payload’ die je zojuist verstuurd hebt. Als het goed is, opent rechts een vak ‘Event details’. Vul hieronder de data in die je daar ziet:

- a. Frequentie: `867500000`
- b. Spreading factor: `12`
- c. Bandbreedte: `125000`
- d. Coding rate: `4/5`

17. Door hoeveel gateways is het bericht ontvangen?

    2 gateways

18. Geef het "gateway_id" en de signaalsterkte van de gateway die het sterkste signaal ontvangen heeft.

    hhs-hboict-nse-delft

19. Hoe lang heeft het geduurd om het bericht af te leveren (‘Consumed airtime’)?

    1.155072s

20. Kopieer de data uit ‘Event details’ en plak dit in een apart Word document.

```json
{
    "name": "as.up.data.forward",
    "time": "2024-10-03T09:34:07.193189950Z",
    "identifiers": [
        {
            "device_ids": {
                "device_id": "unieke-naam",
                "application_ids": {
                    "application_id": "hhs-iot-id"
                },
                "dev_eui": "0004A30B0020D345",
                "join_eui": "1234567891234567",
                "dev_addr": "260B404E"
            }
        }
    ],
    "data": {
        "@type": "type.googleapis.com/ttn.lorawan.v3.ApplicationUp",
        "end_device_ids": {
            "device_id": "unieke-naam",
            "application_ids": {
                "application_id": "hhs-iot-id"
            },
            "dev_eui": "0004A30B0020D345",
            "join_eui": "1234567891234567",
            "dev_addr": "260B404E"
        },
        "correlation_ids": [
            "gs:uplink:01J98VNGK85XZVRBSNQ5EHTX2F"
        ],
        "received_at": "2024-10-03T09:34:07.167981284Z",
        "uplink_message": {
            "session_key_id": "AZJRsDNUWGE/vc0jOTtWbg==",
            "f_port": 1,
            "frm_payload": "AQ==",
            "rx_metadata": [
                {
                    "gateway_ids": {
                        "gateway_id": "hhs-hboict-nse-delft",
                        "eui": "C0EE40FFFF294119"
                    },
                    "time": "2024-10-03T09:34:06.930118083Z",
                    "timestamp": 2771817484,
                    "rssi": -43,
                    "channel_rssi": -43,
                    "snr": 5.5,
                    "location": {
                        "latitude": 52.0019449227654,
                        "longitude": 4.3672296126473675,
                        "altitude": 8,
                        "source": "SOURCE_REGISTRY"
                    },
                    "uplink_token": "CiIKIAoUaGhzLWhib2ljdC1uc2UtZGVsZnQSCMDuQP//KUEZEIyo2qkKGgwIjsr5twYQhMqnxgMg4J3J6dVQ",
                    "received_at": "2024-10-03T09:34:06.942077848Z"
                },
                {
                    "gateway_ids": {
                        "gateway_id": "eui-58a0cbfffe804e23",
                        "eui": "58A0CBFFFE804E23"
                    },
                    "time": "2024-10-03T09:34:06.930301904Z",
                    "timestamp": 176301548,
                    "rssi": -87,
                    "channel_rssi": -87,
                    "snr": 7.25,
                    "location": {
                        "latitude": 52.00200284022436,
                        "longitude": 4.366765022277833,
                        "source": "SOURCE_REGISTRY"
                    },
                    "uplink_token": "CiIKIAoUZXVpLTU4YTBjYmZmZmU4MDRlMjMSCFigy//+gE4jEOzLiFQaDAiOyvm3BhCIudXUAyDgw5DjkP8B",
                    "received_at": "2024-10-03T09:34:06.927822636Z"
                }
            ],
            "settings": {
                "data_rate": {
                    "lora": {
                        "bandwidth": 125000,
                        "spreading_factor": 12,
                        "coding_rate": "4/5"
                    }
                },
                "frequency": "867500000",
                "timestamp": 2771817484,
                "time": "2024-10-03T09:34:06.930118083Z"
            },
            "received_at": "2024-10-03T09:34:06.953725031Z",
            "confirmed": true,
            "consumed_airtime": "1.155072s",
            "network_ids": {
                "net_id": "000013",
                "ns_id": "EC656E0000000181",
                "tenant_id": "ttn",
                "cluster_id": "eu1",
                "cluster_address": "eu1.cloud.thethings.network"
            }
        }
    },
    "correlation_ids": [
        "gs:uplink:01J98VNGK85XZVRBSNQ5EHTX2F"
    ],
    "origin": "ip-10-100-14-223.eu-west-1.compute.internal",
    "context": {
        "tenant-id": "CgN0dG4="
    },
    "visibility": {
        "rights": [
            "RIGHT_APPLICATION_TRAFFIC_READ"
        ]
    },
    "unique_id": "01J98VNGTSB2S1HR7R3QJNJ6QM"
}
```

21. Kopieer alle data uit ‘Termite’ en plak dit in hetzelfde Word document.

    ik heb op clear geklikt dus moest ik dit even zelf nabouwen. Het kan zijn dat er een command mist, sorry voor dat. 

```
sys get ver
RN2483 1.0.5 Oct 31 2018 15:06:52

sys factoryRESET
RN2483 1.0.5 Oct 31 2018 15:06:52

sys get vdd
3294

mac get deveui
0004A30B0020D345

mac set appeui 1234567891234567
ok

mac set appkey B4AAE301FF10E76E4EDA1BB3BCEB040A
ok

mac save
ok

mac join otaa
ok
accepted

mac tx cnf 1 1
ok
mac_tx_ok
```

22. Zoek in de ‘Command Reference’ op hoe je frequenties uitleest uit de RN2483. Vraag de volgende frequenties/commando’s op en plak de uitvoer van ‘Termite’ naar het Word document:

- a. Frequenties van kanaal 0 t/m 8

```
mac get ch freq 0
868100000

mac get ch freq 1
868300000

mac get ch freq 2
868500000

mac get ch freq 3
867100000

mac get ch freq 4
867300000

mac get ch freq 5
867500000

mac get ch freq 6
867700000

mac get ch freq 7
867900000

mac get ch freq 8
0
```

- b. Frequentie van rx2 kanaal

```
radio get freq
867500000
```

- c. mac get ch status 8

```
mac get ch status 8
off
```

- d. `radio get pwr` welke waarde geeft dit en wat betekent de uitvoer? (zoek op)

```
radio get pwr
14
```

Dit nummer staat voor het power level van de module op een schaal van -3 tot 15.

- e. Vraag de ‘spreading factor’ op. Wat is het commando en wat is de waarde?

```
radio get sf
sf12
```

- f. Vraag de ‘coding rate’ op. Wat is het commando en wat is de waarde?

```
radio get cr
4/5
```

- g. Vraag de ‘bandwidth’ op. Wat is het commando en wat is de waarde?

```
radio get bw
125
```

- h. `mac set adr` on wat doet dit?

    Het zet adaptive data rate aan of uit.

- i. `mac get status` welke waarde geeft dit en wat betekent de uitvoer? (zoek op)

```
mac get status
00000810
```

Het geeft de status van het apparaat weer in hexadecimaal.

- j. `mac get ch dcycle 2` wat doet dit en wat betekent de uitvoer? (zoek op)

```
mac get ch dcycle 2
302
```

Geeft de duty cycle van channel 2.

23. Geef het lijstje commando’s waarmee de kanalen op de toegestane limieten worden ingesteld, rekening houdend met SF, BW, EIRP, duty cycle, modulatie. Welke commando’s moeten gegeven worden?

```
mac set ch freq 0 868100000
mac set ch drrange 0 0 5
mac set ch dcycle 0 302
mac save

mac set ch freq 1 868300000
mac set ch drrange 1 0 5
mac set ch dcycle 1 302
mac save

mac set ch freq 2 868500000
mac set ch drrange 2 0 5
mac set ch dcycle 2 302
mac save

mac set ch freq 3 867100000
mac set ch drrange 3 0 5
mac set ch dcycle 3 302
mac save

mac set ch freq 5 867500000
mac set ch drrange 5 0 5
mac set ch dcycle 5 302
mac save

mac set ch freq 6 867700000
mac set ch drrange 6 0 5
mac set ch dcycle 6 302
mac save

mac set ch freq 7 867900000
mac set ch drrange 7 0 5
mac set ch dcycle 7 302
mac save

mac set ch freq 8 868800000
mac set ch drrange 8 0 7
mac set ch dcycle 8 65535
mac save