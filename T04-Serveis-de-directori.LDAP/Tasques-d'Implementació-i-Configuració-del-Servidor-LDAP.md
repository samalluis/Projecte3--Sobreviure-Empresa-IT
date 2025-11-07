## 3. Tasques d'Implementació i Configuració del Servidor LDAP
   
La Consultora EverPia ha de complir estrictament amb les següents tasques d'instal·lació i configuració:
### 3.1. Instal·lació i Configuració Base d'OpenLDAP
   
**T.LDAP.01** -
Instal·lació del servei OpenLDAP.
S'ha de mostrar el resultat de la comanda slapcat per validar la instal·lació base.

**T.LDAP.02** -
Configuració de la base de dades.
Nom del Domini: innovatechXX.test

**T.LDAP.03** -
Configuració de la contrasenya d'administrador.
Contrasenya: p@ssw0rd

**T.LDAP.04** -
Creació d'Unitats Organitzatives (OU) inicials.
S'han de crear dues OUs: users i groups mitjançant un fitxer .ldif.

**T.LDAP.05** -
Validació de les Unitats Organitzatives.
Realitzar una consulta amb ldapsearch que mostri totes les OUs creades al directori.

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
