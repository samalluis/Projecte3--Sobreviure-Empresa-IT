# T07: Instal·lant un servidor de noms

## Breu descripció

Després de l’exitosa experiència a nivell de formació, els clients de **Digicore** estan tan satisfets amb la nostra feina que ens encarreguen la **implantació des de zero dels seus serveis de DNS interns**.

Actualment, l'agència fa servir **adreces IP** per accedir als seus servidors de desenvolupament, bases de dades i eines de gestió interna. Aquest mètode és ineficient i propens a errors:

- **Usabilitat deficient:** Els empleats han de memoritzar o buscar constantment adreces IP complexes (p. ex., `192.168.10.25`).
- **Manteniment feixuc:** Si un servidor canvia la seva IP, cal notificar i actualitzar manualment la configuració a tots els equips i aplicacions que s'hi connecten.
- **Manca de professionalitat:** En un entorn professional, tots els serveis haurien de ser accessibles mitjançant noms fàcils de recordar.

Per tant, la missió és **implementar un Sistema de Noms de Domini (DNS) intern robust**, de manera que els servidors i aplicacions de l’agència es puguin accedir utilitzant noms de domini amigables (p. ex., `bbdd.digicore.lan` o `wiki.digicore.lan`).

---

## El vostre repte

La recomanació com a consultora és utilitzar **BIND9**, l'estàndard de facto de servidor de noms a Linux, per la seva **fiabilitat i flexibilitat**.

La missió serà **instal·lar i configurar un servidor DNS primari (màster)** amb **BIND9** en un sistema Linux.  
Haureu de crear una **Zona Directa (Forward Zone)** i una **Zona Inversa (Reverse Zone)** per al domini privat de DigiCore, garantint que:

- Els **noms es resolguin a IPs**  
- Les **IPs es resolguin a noms**

Per a la prova de concepte, s’utilitzarà el domini `digicore-XX.test`, on **XX** serà el vostre número de llista.

---

## Pas previ

Configurar un **Ubuntu Server** amb:

- 4 GB de RAM  
- 20 GB de disc  
- Una interfície **adaptador pont** (la configuració s’indicarà a l’inici del repte)  
- Una segona interfície en **host-only**

Un cop configurat:

1. Instal·lar el paquet **bind9**.  
2. Instal·lar el servei **ssh** al servidor, ja que després caldrà exportar els arxius de configuració al vostre repositori de **GitHub**.

---

## Accions a realitzar

### 1. Configuració de `named.conf.options`

- Permetre consultes recursives de la xarxa local.
- Utilitzar com a reenviador la IP `8.8.8.8`.
- Mostrar la captura de configuració.
- Reiniciar el servei i comprovar-ne el funcionament (mostra l’estat).

### 2. Configuració del client

- Utilitzar una màquina client (p. ex. **Zorin**), canviant l’adaptador a **adaptador pont**.  
- Assignar com a servidor de noms (DNS) la **IP del vostre servidor DNS**.
- Comprovar que el client té **resolució a Internet** (obrint una pàgina web o amb `dig google.com`).

### 3. Configuració de zones

Editar l’arxiu `named.conf.local` per definir:

- La **zona directa** del domini `digicore-XX.test`
- La **zona inversa** de la xarxa local (adreça utilitzada a la prova)

#### Zona directa

- Crear la carpeta `/etc/bind/zones`  
- Crear el fitxer de zona copiant `db.local`  
- Configurar els registres següents:
  - **SOA** amb les dades correctes  
  - **NS** amb el vostre servidor  
  - **A** per `server` amb la IP del servidor  
  - **A** per `dbserver` amb la IP del client  
  - **CNAME** amb nom `data` apuntant a `dbserver`

#### Zona inversa

- Crear el fitxer corresponent copiant `db.127` a `/etc/bind/zones`  
- Configurar:
  - **SOA** i **NS** adients  
  - **PTR** corresponents a `server` i `dbserver`

### 4. Verificació

- Reiniciar el servei **bind9**
- Fer comprovacions des del client:
  - Consultes **directes**
  - Consultes **inverses**

### 5. Transferència de zona

- Editar `named.conf.local` per **permetre la transferència** de la zona directa als companys de l’equip.
- Configurar una **zona secundària** del domini d’un altre company.
- Forçar la transferència i comprovar el funcionament des del client.

---

## Activitat d’avaluació del repte

Per demostrar la competència tècnica, caldrà **superar una avaluació pràctica final**.  
Durant aquesta avaluació només es permetrà l’ús d’un **full manuscrit amb anotacions personals**, que s’haurà d’entregar en finalitzar la prova.

