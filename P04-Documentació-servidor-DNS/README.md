# P04: Documentació servidor DNS

## Breu descripció

Molt benvinguts a la vostra nova tasca, consultors!

Com a membres de l'equip de sistemes d'**EverPia**, us heu enfrontat al repte de configurar un servidor de noms com a prova de concepte pel nostre client **Digicore**.  
Ara mateix, el resultat de la vostra feina es troba en una màquina virtual, però l’objectiu és **publicar aquestes configuracions a GitHub**.  

D’aquesta manera, quan es vulgui replicar la configuració, **no caldrà començar des de zero**: només caldrà descarregar els arxius al servidor Linux triat i reiniciar el servei per tenir el servidor completament operatiu.

---

## Fase 1: Preparació de la connectivitat i extracció dels arxius

### Pas 1.1: Configuració de la interfície Host-Only

1. Afegiu una **segona interfície de xarxa** a la vostra màquina virtual **Ubuntu Server**.  
2. Assigneu-li el mode **Host-Only**.  
3. Configureu-la i **activeu-la**.  
4. Comproveu que **teniu connectivitat** des de la màquina física (host).

---

### Pas 1.2: Còpia segura dels fitxers clau amb SCP

Un cop establerta la connectivitat *Host-Only*, utilitzareu el protocol **SCP (Secure Copy Protocol)**, que és segur i ve inclòs amb el servei SSH, per transferir els fitxers de configuració a la màquina física.

Els arxius a copiar són els que heu editat o creat en la tasca del servidor DNS:


