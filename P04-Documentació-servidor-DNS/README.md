# P04: Documentació servidor DNS

## Breu descripció

Molt benvinguts a la vostra nova tasca, consultors!

Com a membres de l'equip de sistemes d’**EverPia**, us heu enfrontat al repte de configurar un **servidor de noms** com a prova de concepte pel nostre client **Digicore**.  
Actualment, el resultat de la vostra feina es troba en una **màquina virtual**.

L’objectiu és poder **publicar aquestes configuracions a GitHub**, assegurant que quan es vulgui **replicar la configuració**, no caldrà començar des de zero: n’hi haurà prou amb **descarregar els arxius** dins del servidor Linux triat i **reiniciar el servei** per tenir el servidor completament operatiu.

---

## Fase 1: Preparació de la connectivitat i extracció dels arxius

Per poder copiar fitxers de la vostra màquina virtual **Ubuntu Server** a la màquina física de treball (**host**), heu d’assegurar la **connectivitat de xarxa**.

### Pas 1.1: Configuració de la interfície Host-Only

1. Afegiu una **segona interfície de xarxa** a la configuració de la màquina virtual Ubuntu Server.  
2. Assigneu-li el **mode Host-Only**.  
3. Configureu-la, activeu-la i **comproveu la connectivitat** des de la màquina física.

### Pas 1.2: Còpia segura dels fitxers clau amb SCP

Un cop establerta la connectivitat Host-Only, utilitzareu el protocol **SCP (Secure Copy Protocol)**, inclòs amb el servei **SSH**, per transferir els fitxers de configuració a la màquina física.

Els arxius a copiar són:

- `/etc/bind/named.conf.options`  
- `/etc/bind/named.conf.local`  
- Arxius de zones creats a la carpeta `/etc/bind/zones`

Per copiar els arxius a la màquina física, obriu un terminal al PC i executeu la comanda `scp`.  
> El punt (.) al final de la comanda indica que l’arxiu es copiarà al directori actual de la màquina física.

---

## Fase 2: Integració a GitHub

### Pas 2.1: Crear carpeta i arxiu README.md

1. Creeu la carpeta `producte04` i el fitxer `README.md`.  
   - Es pot crear directament des de GitHub, indicant el nom complet:  
     `producte04/README.md`  
   - La carpeta es crearà automàticament.  
2. A l’arxiu `README.md`, afegiu:
   - El **títol del producte**.  
   - Una **explicació del contingut** i la seva finalitat.

### Pas 2.2: Pujar arxius

- Pugeu els diversos **fitxers de configuració**.  
- Creeu prèviament la carpeta `zones` abans de pujar-hi els arxius corresponents.  
- Si cal, creeu un fitxer temporal `zones/esborrar` per poder pujar la carpeta i després **esborreu-lo**.

---

## Objectius específics de la tasca / Finalitat de la tasca

- **Usar GitHub** per documentar configuracions de servidors.  
- **Valorar els avantatges** de poder replicar configuracions de manera **ràpida i segura** (*repetibilitat*).  
- Facilitar la **traçabilitat i manteniment** dels serveis DNS configurats.
