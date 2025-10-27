# Guia d’Ús Professional de KeePassXC

## 1. Generació de Contrasenyes Segures

KeePassXC incorpora un **generador de contrasenyes integrat** que permet crear claus complexes i úniques per a cada compte.

### 1.1 Accés al Generador
- Durant la creació o edició d’una entrada, fes clic al botó **“Generar contrasenya”** situat al costat del camp de contrasenya.  
- També és possible obrir el generador des del menú principal:  
  **Eines → Generador de contrasenyes**.

### 1.2 Paràmetres del Generador
El generador permet personalitzar diferents aspectes de la contrasenya:

| Paràmetre | Descripció | Recomanació |
|------------|-------------|-------------|
| **Longitud** | Nombre total de caràcters de la contrasenya. | Com a mínim 16 caràcters (idealment 20 o més). |
| **Majúscules (A–Z)** | Inclou lletres majúscules. | Activat. |
| **Minúscules (a–z)** | Inclou lletres minúscules. | Activat. |
| **Dígits (0–9)** | Inclou números. | Activat. |
| **Caràcters especials (`!@#%&...`)** | Afegeix símbols addicionals per augmentar la complexitat. | Activat. |
| **Evitar caràcters similars** | Exclou caràcters fàcilment confusibles (O/0, l/I). | Recomanat per contrasenyes que s’hagin d’introduir manualment. |

Després de generar la contrasenya:
- Pots copiar-la al porta-retalls (es pot configurar per esborrar-se automàticament després d’uns segons).  
- O inserir-la directament al camp corresponent de la nova entrada.  

**Consell:** KeePassXC pot generar contrasenyes úniques per a cada servei, evitant la reutilització de credencials.

---

## 2. Exemples d’Ús i Emplenament Automàtic

### 2.1 Desar una Credencial d’un Compte de Correu Electrònic
1. Clica **Afegeix entrada nova (+)** dins de la base de dades.  
2. Omple els camps següents:
   - **Nom d’usuari:** adreça de correu electrònic.  
   - **Contrasenya:** enganxa o genera una contrasenya segura.  
   - **URL:** adreça del servei, per exemple `https://mail.google.com`.  
   - **Comentaris:** opcionalment, afegeix informació addicional (per exemple, “Compte personal” o “Compte laboral”).  
3. Desa l’entrada.

### 2.2 Desar una Credencial d’una Aplicació o Servei Web
1. Repeteix el procediment anterior.  
2. Indica el nom o la URL del servei (per exemple, `https://github.com` o `https://www.netflix.com`).  
3. Afegeix una icona o etiqueta per identificar ràpidament el servei dins la base de dades.

### 2.3 Ús de l’Extensió del Navegador per a l’Emplenament Automàtic
KeePassXC permet l’emplenament automàtic de credencials mitjançant l’extensió **KeePassXC-Browser**, compatible amb Firefox, Chrome, Brave i Edge.

**Configuració pas a pas:**
1. Instal·la l’extensió **KeePassXC-Browser** des de la botiga oficial del teu navegador.  
2. A KeePassXC, obre **Eines → Configuració → Integració del navegador**.  
3. Activa el navegador que utilitzes i fes clic a **“Connectar”**.  
4. El navegador demanarà autorització per connectar-se amb KeePassXC; confirma-la.  
5. A partir d’aquest moment, quan visitis una pàgina d’inici de sessió, apareixerà la icona de KeePassXC al camp de contrasenya.  
6. Clica la icona i selecciona el compte desitjat.  
   - KeePassXC emplenarà automàticament els camps d’usuari i contrasenya.  
   - També pots configurar l’emplenament automàtic automàticament per dominis de confiança.

Aquesta funcionalitat permet accedir als serveis de manera ràpida i segura, sense exposar les contrasenyes al porta-retalls ni escriure-les manualment.

---

## 3. Gestió de Còpies de Seguretat (Backup i Exportació)

### 3.1 Còpia de Seguretat del Fitxer `.kdbx`
El fitxer `.kdbx` conté totes les contrasenyes i dades xifrades. És fonamental mantenir-ne còpies de seguretat actualitzades.

**Procediment:**
1. Localitza el fitxer principal de la base de dades (`nom_base_dades.kdbx`).  
2. Copia’l manualment a una ubicació segura o utilitza **Fitxer → Desa com...** per generar una nova còpia, per exemple:  
   `Contrasenyes_backup_2025-10-24.kdbx`.  
3. Comprova que la còpia s’ha realitzat correctament i que és accessible.

### 3.2 Exportació de Dades
KeePassXC permet exportar el contingut de la base de dades a altres formats, però aquesta operació **només s’ha de fer amb finalitats puntuals** (com migracions o revisions), ja que pot reduir el nivell de seguretat.

**Per exportar:**
1. Obre **Fitxer → Exporta**.  
2. Selecciona el format desitjat (`.kdbx` per mantenir el xifrat o `.csv` per ús temporal).  
3. Si s’utilitza `.csv`, assegura’t d’eliminar el fitxer un cop acabada la tasca, ja que no està xifrat.

### 3.3 Recomanacions d’Emmagatzematge Segur
- **No emmagatzemis la còpia al mateix dispositiu** on tens l’original.  
- **Opcions recomanades:**
  - **Dispositiu USB xifrat:** crea un volum segur amb VeraCrypt o LUKS i desa-hi la còpia.  
  - **Emmagatzematge al núvol xifrat:** utilitza serveis com Nextcloud, Tresorit o un fitxer `.zip` protegit amb contrasenya forta.  
- **Freqüència recomanada:** crea una còpia de seguretat cada mes o després de realitzar canvis importants.

Aquestes pràctiques asseguren la disponibilitat i confidencialitat de la informació en cas de pèrdua o dany de l’arxiu principal.

---

## 4. Recomanacions Addicionals
- Mantén KeePassXC actualitzat a l’última versió per garantir la correcció d’errors i millores de seguretat.  
- Configura el **bloqueig automàtic** de la base de dades després d’un període d’inactivitat.  
- No comparteixis mai la contrasenya mestra ni el fitxer `.kdbx` amb tercers.  
- Fes servir **autenticació de doble factor (2FA)** als serveis més crítics, combinada amb KeePassXC.  
- Considera guardar el fitxer `.kdbx` en un sistema de còpia automàtica xifrada (com un NAS segur o unitats amb encriptació per maquinari).  

---

## 5. Conclusions
KeePassXC és una eina potent i segura per gestionar contrasenyes de manera eficient.  
Permet generar contrasenyes úniques i complexes, guardar-les de forma xifrada i accedir-hi fàcilment mitjançant l’extensió del navegador.  
Amb una gestió adequada de les còpies de seguretat i bones pràctiques d’emmagatzematge segur, garanteix la protecció integral de les credencials digitals.
