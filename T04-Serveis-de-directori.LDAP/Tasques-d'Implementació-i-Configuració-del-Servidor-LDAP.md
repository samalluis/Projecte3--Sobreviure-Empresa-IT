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
