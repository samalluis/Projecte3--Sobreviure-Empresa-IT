# Guia d’Ús de KeePassXC

## 1. Instal·lació i Configuració Inicial

### 1.1 Descàrrega i Instal·lació
1. Accedeix al lloc web oficial: [https://keepassxc.org](https://keepassxc.org).  
2. Descarrega la versió adequada per al teu sistema operatiu (Windows, macOS o Linux).  
3. Instal·la l’aplicació seguint les instruccions del sistema.  
   - En entorns Linux, també es pot instal·lar mitjançant el gestor de paquets:
     ```bash
     sudo apt install keepassxc
     ```

### 1.2 Creació de la Base de Dades Principal
1. Obre KeePassXC i selecciona **“Nova base de dades”**.  
2. Introdueix un nom i selecciona una ubicació segura per guardar el fitxer, per exemple:  
   `Documents/Seguretat/Contrasenyes.kdbx`.  
3. Defineix una **contrasenya mestra** forta. És l’única contrasenya que cal recordar.  
4. Opcionalment, afegeix un **fitxer de clau** (key file) per augmentar el nivell de seguretat.  
5. Desa la configuració per finalitzar la creació de la base de dades principal.

---

## 2. Generació de Contrasenyes Segures

KeePassXC disposa d’un generador integrat que permet crear contrasenyes complexes i personalitzades.

### 2.1 Accés al Generador
- Quan es crea o s’edita una entrada, es pot accedir al generador mitjançant el botó **“Generar contrasenya”**.  
- També és possible obrir-lo des del menú: **Eines → Generador de contrasenyes**.

### 2.2 Paràmetres Recomanats
- **Longitud:** mínim 16 caràcters (es recomana 20 o més).  
- **Tipus de caràcters:**  
  - Majúscules (A–Z)  
  - Minúscules (a–z)  
  - Dígits (0–9)  
  - Caràcters especials (`!@#%&...`)  
- **Opcions addicionals:**  
  - Evitar caràcters similars (O/0, l/I) per facilitar la lectura.  
  - Definir la política de longitud i complexitat segons les necessitats del servei.  

La contrasenya generada pot copiar-se al porta-retalls o inserir-se automàticament al camp corresponent.

---

## 3. Exemples d’Ús i Emplenament Automàtic

### 3.1 Desar una Credencial d’un Compte de Correu Electrònic
1. Clica **Afegeix entrada nova (+)** dins de la base de dades.  
2. Omple els camps següents:
   - **Nom d’usuari:** adreça de correu electrònic.  
   - **Contrasenya:** enganxa o genera una contrasenya segura.  
   - **URL:** adreça del servei (per exemple, `https://mail.google.com`).  
   - **Comentaris:** informació addicional, si escau.  
3. Desa l’entrada.

### 3.2 Desar una Credencial d’una Aplicació o Servei Web
1. Repeteix el procediment anterior.  
2. Indica el nom o la URL del servei (per exemple, `https://github.com` o `https://www.netflix.com`).  
3. Afegeix una icona o etiqueta per identificar ràpidament el servei dins la base de dades.

### 3.3 Ús de l’Extensió del Navegador
1. Instal·la l’extensió **KeePassXC-Browser**, disponible per Firefox, Chrome, Brave i Edge.  
2. A KeePassXC, obre **Eines → Configuració → Integració del navegador** i activa l’opció corresponent al navegador utilitzat.  
3. Connecta el navegador amb KeePassXC (la primera vegada caldrà autoritzar la connexió).  
4. Quan visitis una pàgina d’inici de sessió, clica la icona de KeePassXC al navegador i selecciona el compte desitjat.  
   El gestor emplenarà automàticament els camps d’usuari i contrasenya.

---

## 4. Gestió de Còpies de Seguretat (Backup)

### 4.1 Creació d’una Còpia de Seguretat
1. Localitza el fitxer principal de la base de dades (`nom_base_dades.kdbx`).  
2. Copia’l manualment o utilitza **Fitxer → Desa com...** per generar una còpia, per exemple:  
   `Contrasenyes_backup_2025-10-24.kdbx`.  
3. També és possible exportar les dades, però **no es recomana utilitzar formats sense xifrar** (com `.csv`) excepte per tasques puntuals.

### 4.2 Bones Pràctiques de Seguretat
- No guardis la còpia al mateix dispositiu o carpeta que l’arxiu original.  
- Opcions recomanades:
  - **Dispositiu USB xifrat**, creat amb eines com VeraCrypt o LUKS.  
  - **Emmagatzematge al núvol xifrat**, mitjançant serveis com Nextcloud, Tresorit o un fitxer `.zip` protegit amb contrasenya.  
- Realitza còpies periòdiques, especialment després d’afegir o modificar entrades importants.  

---

## 5. Recomanacions Addicionals
- Mantén KeePassXC actualitzat a l’última versió disponible.  
- Configura el bloqueig automàtic de la base de dades després d’un període d’inactivitat.  
- No comparteixis mai la contrasenya mestra ni el fitxer `.kdbx`.  
- Combina l’ús de KeePassXC amb l’autenticació de doble factor als serveis més crítics.

---

▶️Torna al [Informe](Informe.md)

🏚️Torna a la [Pagina principal](..)

