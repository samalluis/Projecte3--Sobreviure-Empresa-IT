## 3. Tasques d'Implementació i Configuració del Servidor LDAP
   
La Consultora EverPia ha de complir estrictament amb les següents tasques d'instal·lació i configuració:
### 3.1. Instal·lació i Configuració Base d'OpenLDAP
   
**T.LDAP.01** -
Instal·lació del servei OpenLDAP.
S'ha de mostrar el resultat de la comanda slapcat per validar la instal·lació base.

- Comanda per instalar ldap:
```
sudo apt install slapd ldap-utils -y
```

![hfgh](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T04-Serveis-de-directori.LDAP/img/Captura%20de%20pantalla%202025-10-21%20162439.png?raw=true)

Despres de introduir la comanda fiquem la contraseña `p@ssw0rd` i com a nom de l'organització `inovatechXX.test`, per exemple, en el meu cas es `innovatech07.test`

- Verificacio de la instalacio base:
```
sudo slapcat
```

![gdfg](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T04-Serveis-de-directori.LDAP/img/Captura%20de%20pantalla%202025-10-21%20162608.png?raw=true)

```
systemctl status slapd
```

![dasda](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T04-Serveis-de-directori.LDAP/img/Captura%20de%20pantalla%202025-10-21%20162529.png?raw=true)

**T.LDAP.02 i T.LDAP.03** 
Configuració de la base de dades.
Nom del Domini: innovatechXX.test

Configuració de la contrasenya d'administrador.
Contrasenya: p@ssw0rd

Si en el pas anterior hens hem equivocat utilitzarem la seguent comanda:
```
sudo dpkg-reconfigure slapd
```

Diem que no volem cancel·lar la configuracio de la BDD, atès que és el que volem fer.

Posem el nom corresponent al directori que volem crear.

![sdfsd](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T04-Serveis-de-directori.LDAP/img/Captura%20de%20pantalla%202025-11-11%20162702.png?raw=true)

Introduim el nom de l'organització que a de ser `innovatechXX.test`.

![sdf](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T04-Serveis-de-directori.LDAP/img/Captura%20de%20pantalla%202025-11-11%20162718.png?raw=true)

Contrasenya de l'adrministrador que ha de ser `p@ssw0rd`

![sdfsf](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T04-Serveis-de-directori.LDAP/img/Captura%20de%20pantalla%202025-11-11%20162738.png?raw=true)

I acceptem les dos seguents opcions de configuració

**T.LDAP.04** -
Creació d'Unitats Organitzatives (OU) inicials.
S'han de crear dues OUs: users i groups mitjançant un fitxer .ldif.

- Creem els fitxers:

![fs](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T04-Serveis-de-directori.LDAP/img/Captura%20de%20pantalla%202025-10-22%20183317.png?raw=true)

![dad](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T04-Serveis-de-directori.LDAP/img/Captura%20de%20pantalla%202025-10-22%20183327.png?raw=true)

- Els editem:

![dasd](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T04-Serveis-de-directori.LDAP/img/Captura%20de%20pantalla%202025-11-18%20151754.png?raw=true)

![dadad](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T04-Serveis-de-directori.LDAP/img/Captura%20de%20pantalla%202025-11-18%20151809.png?raw=true)

- I els afegim:

![sSaa](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T04-Serveis-de-directori.LDAP/img/Captura%20de%20pantalla%202025-10-22%20183335.png?raw=true)

![dadadda](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T04-Serveis-de-directori.LDAP/img/Captura%20de%20pantalla%202025-10-22%20183347.png?raw=true)

**T.LDAP.05** -
Validació de les Unitats Organitzatives.
Realitzar una consulta amb ldapsearch que mostri totes les OUs creades al directori.

- Consultem si esta correcta:
  
![dadsadasdad](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T04-Serveis-de-directori.LDAP/img/Captura%20de%20pantalla%202025-10-22%20183651.png?raw=true)

- I si necesitem eliminarlos es de la seguent manera:

![dadadadsad](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T04-Serveis-de-directori.LDAP/img/Captura%20de%20pantalla%202025-10-22%20184130.png?raw=true)

![zcxzczczc](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T04-Serveis-de-directori.LDAP/img/Captura%20de%20pantalla%202025-10-22%20184317.png?raw=true)

### 3.2. Gestió i Administració (LAM)

**T.LAM.01** -
Instal·lació del Gestor d'Usuaris LDAP (LAM).
S'ha de documentar la comanda d'instal·lació.

**T.LAM.02** -
Accés Remot i Configuració.
Connectar a LAM des de la màquina física utilitzant l'adreça IP de la interfície Host-Only.

**T.LAM.03** -
Configuració per defecte.
Establir la configuració predeterminada perquè els nous usuaris s'ubiquin a l'OU users i els nous grups a l'OU groups.

**T.LAM.04** -
Creació de Grups.
Crear dos grups de seguretat al directori: tech i manager.

**T.LAM.05** -
Creació d'Usuaris de Prova.
Crear un usuari per a cada grup: tech01 (membre de tech) i manager01 (membre de manager).

---


Click aqui per anar a [ 1. REQUERIMENTS D'INFRASTRUCTURA](Requeriments-d'Infraestructura-Inicial.md)

Click aqui per anar a [ 3. INTEGRACIÓ DE CLIENT](Integració-de-Client.md)

Click aqui per anar a [HOME](..)

Click aqui per anar a [README](README.md)


