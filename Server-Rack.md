EMC KTN-STL3 Disk Enclosure DAE, 15 Schächte, SAS 6G, LFF [https://pro-jex.de/EMC-KTN-STL3-Disk-Enclosure] 50€

DELL H200E 6Gbps SAS FW:P20 (LSI 9200-8E) IT Mode ZFS FreeNAS unRAID NoROM [https://www.ebay.de/itm/144253855010?chn=ps&_ul=DE&google_free_listing_action=view_item] 30€

10 x EMC 3.5 Zoll HDD Caddy 100-563-430 mit SAS/FC Hot Swap Festplatte Caddy [https://www.ebay.de/itm/204147447947] 40€

1x  ICY DOCK EZConvert Lite MB882SP-1S-3B - 2,5 Zoll (6,4cm) zu 3,5 Zoll (8,9cm) SATA SSD/HDD Konverter 

Kabel: Mini SAS 4x SFF-8088 auf SFF 8088 Datenkabel 25€

Rackgehäuse: 12U 57€

1U Mehrfachsteckdose (Anschluss hinten)



Versand: Kostenlos.



Serverrack 12U Gehäuse Multiplex Zukunftsplan:

HE,Komponente,Status,Anmerkung für die Zukunft
12,Mikrotik Switch,Leer,Anschlüsse nach vorne für schnelles Patching.
11,Bürsten Kabelöffnung,Leer,Verbindung von Switch (vorne) zu FW/FB (hinten).
10,Firewall,Leer,Anschlüsse nach hinten.
09,Fritzbox 7590,Leer,Anschlüsse nach hinten.
08,Steckdosenleiste,Belegt,Zentraler Stromknotenpunkt (Anschlüsse hinten).
05 - 07,3HE Disc Enclosure,Belegt,Stabiler Mittelbau.
01 - 04,4HE Server,Belegt,Das schwere Fundament.

Der Server existiert schon:
Mainboard: Supermicro X10DRH-iT (Dual LGA2011-3, 10G LAN)
CPUs: 2× Intel Xeon E5-2680 v4 → 28C / 56T gesamt, 2.4–3.3 GHz
RAM: 64 GB DDR4 ECC Registered (8×8 GB, 2400 MHz)
CPU-Kühler: 2× Noctua NH-D9L
Gehäuse: Inter-Tech 4HE 19" Rack-Servergehäuse
Netzteil: be quiet! Pure Power 11 FM, 850 W, 80+ Gold


Aber ich möchte nun Storage Upgraden. Grund war ursprünglich weil sich in meinem kleinen Case nur sehr schlecht Festplatten unterbringen lassen.


Dinge die es zu beachten gibt:

1. Sektor Formatierung
EMC-Festplatten und Disk Enclosures kommen nativ oft mit einer Sektorgröße von 520 Bytes (statt der üblichen 512 Bytes für Consumer/Standard-Enterprise oder 4096 Bytes für Advanced Format).

- Das Problem: Windows, unRAID oder ZFS können mit 520-Byte-Sektoren nichts anfangen. Die Platten werden zwar vom Controller erkannt, lassen sich aber nicht einbinden.

- Die Lösung: Die Festplatten müssen per Kommandozeile (z. B. via Linux/Ubuntu Live-Stick) mit dem Tool sg_format auf 512 Bytes umformatiert werden. Das ist zwingend notwendig.


2. Interposer und Caddies 
10 Caddies für 15 Schächte sind eingeplant. Achtung:

- Die KTN-STL3 benötigt oft spezielle Interposer-Boards (kleine Platinen im Caddy), wenn du SATA-Platten in diesem SAS-Enclosure betreiben willst.

- Reine SAS-Platten, werden direkt gesteckt. Bei den Caddies muss ein Interposer dabei sein, falls normale SATA-Festplatten verbaut werden.



Dinge die ich überprüfen sollte bei dem Caddies Angebot: Ist dort der grüne Interposer Chip verbaut?

Ich denke die Festplatten auf 512 Bytes zu formatieren ist überhaupt nicht das Problem oder?

