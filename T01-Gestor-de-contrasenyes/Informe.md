# Fase 1: Anàlisi i Justificació (Document d'Informe)

## Introducció i Justificació:

### · Explicació de per què les contrasenyes febles o reutilitzades són un risc crític per a l'empresa.

**Les contrasenyes febles o reutilitzades** representen un **risc crític** per a la seguretat empresarial. Atacs com els diccionaris o el credential stuffing permeten als atacants provar milions de combinacions de contrasenyes filtrades en altres serveis.

Això pot derivar en que si tens contrasenyes com "123456" o "contraseña" pugui acabar en accessos no autoritzats, robatori d’informació confidencial o segrest de comptes.

### · La funció crucial d'un gestor de contrasenyes per mitigar aquests riscos.

Per mitigar aquests riscos, els gestors de contrasenyes permeten generar i emmagatzemar credencials úniques i robustes de manera segura, xifrada i centralitzada.

###  Bitwarden — Anàlisi Tècnica Detallada

| **Aspecte** | **Descripció** |
|--------------|----------------|
| ** Sincronització (Extensions de Navegador)** | Chrome ✅ · Edge (Vora) ✅ · Safari ✅ · Firefox ✅ · Opera ✅ · Brave ✅ · Vivaldi ✅ · Tor ⚠️ (funciona amb limitacions, no suport oficial) |
| ** Facilitat d’Accés des de Múltiples Dispositius** | Windows ✅ · macOS ✅ · Linux ✅ · App Store (iOS) ✅ · Google Play (Android) ✅ |
| ** Model de Seguretat** | Xifratge **extrem a extrem (E2EE)**. Derivació de claus amb **PBKDF2 SHA-256** o **Argon2id**, segons configuració de l’usuari. Model de **coneixement zero**: només l’usuari pot desxifrar les dades. |
| ** Cost / Model Freemium** | Versió gratuïta amb funcions essencials. Plans **Teams (4 €/mes/usuari)** i **Enterprise (6 €/mes/usuari)** amb opcions avançades de gestió, polítiques i integració SSO. |

---

###  KeePassXC — Anàlisi Tècnica Detallada

| **Aspecte** | **Descripció** |
|--------------|----------------|
| ** Emmagatzematge Local de l’Arxiu (KDBX)** | KeePassXC desa totes les credencials en un fitxer **local xifrat (.kdbx)** compatible amb **KeePass** (versions KDBX3 i KDBX4). Aquest arxiu pot contenir noms d’usuari, contrasenyes, notes, fitxers adjunts i claus TOTP. |
| ** Independència del Núvol** | No depèn de cap servidor ni servei extern. L’usuari manté el **control total** sobre les seves dades i pot decidir si vol sincronitzar manualment el fitxer (p. ex. amb un núvol privat o USB). |
| ** Model Open Source** | Projecte **de codi obert** sota llicència **GPLv3**, amb el codi font disponible a GitHub. Auditat per la comunitat, sense rastrejadors, anuncis ni subscripcions. Transparència total i seguretat verificada per tercers. |
| ** Portabilitat de l’Arxiu** | El fitxer `.kdbx` és **altament portable** i pot moure’s o copiar-se fàcilment entre sistemes (Windows, macOS, Linux). També pot sincronitzar-se mitjançant serveis com Nextcloud o Syncthing o guardar-se en una clau USB xifrada. |
| ** Funcions Principals (Resum)** | - Creació i gestió de bases de dades KDBX.<br> - Generador de contrasenyes integrat.<br> - Integració amb navegadors (Chrome, Firefox, Edge, Vivaldi, Brave, Tor).<br> - Importació des de Bitwarden, 1Password, Proton Pass, etc.<br> - Emmagatzematge TOTP i suport per YubiKey/OnlyKey.<br> - Sincronització amb KeeShare i integració SSH Agent. |
| ** Cost / Model** | 100 % **gratuït** i **lliure**, sense cap tipus de pla premium, publicitat ni subscripció. |

---

## ⚖️ Avantatges i Inconvenients

###  Model Online – Bitwarden

| **Aspecte** | **Avantatges** | **Inconvenients** |
|--------------|----------------|-------------------|
| **Seguretat** | - Xifratge extrem a extrem (E2EE) i model de coneixement zero.<br>- Suport per 2FA, SSO i polítiques d’accés corporatives.<br>- Possibilitat d’autoallotjament del servidor per major control. | - Dependència del núvol i de la connectivitat a Internet.<br>- Exposició potencial si el servei al núvol és compromès (encara que les dades estiguin xifrades). |
| **Usabilitat** | - Sincronització automàtica entre dispositius i navegadors.<br>- Extensió de navegador molt intuïtiva.<br>- Aplicacions modernes i multiplataforma. | - Pot requerir subscripció per accedir a totes les funcions d’equip.<br>- Necessitat de mantenir una connexió activa per accedir a noves dades. |
| **Continuïtat del Negoci** | - Facilita la col·laboració d’equips i la gestió centralitzada de credencials.<br>- Escalabilitat i suport empresarial. | - Dependència d’un servei extern per a la disponibilitat del sistema.<br>- Possible cost recurrent per usuari o equip. |

---

###  Model Offline – KeePassXC

| **Aspecte** | **Avantatges** | **Inconvenients** |
|--------------|----------------|-------------------|
| **Seguretat** | - Les dades romanen completament locals i xifrades (AES-256).<br>- No depèn de cap servidor extern.<br>- Compatible amb claus físiques (YubiKey/OnlyKey). | - Si es perd el fitxer `.kdbx` o la contrasenya mestra, no hi ha forma de recuperació.<br>- Les còpies de seguretat depenen exclusivament de l’usuari. |
| **Usabilitat** | - Interfície clara i senzilla per a usuaris tècnics.<br>- Pot funcionar sense Internet.<br>- Gran flexibilitat per personalitzar l’estructura i les categories. | - Sincronització manual entre dispositius.<br>- Pot ser menys còmode per a usuaris no tècnics. |
| **Continuïtat del Negoci** | - No hi ha risc per caigudes de serveis externs o tancament de proveïdors.<br>- El fitxer pot emmagatzemar-se o transferir-se fàcilment entre sistemes. | - Cal establir polítiques internes per gestionar còpies de seguretat i sincronització manual. |

---

## 🧭 Recomanació Final

Després de comparar ambdós models, la recomanació és adoptar **KeePassXC** com a gestor de contrasenyes.

### 🔍 Justificació:

- **Control total de les dades:** Les contrasenyes s’emmagatzemen localment i no es transfereixen a cap servidor extern, fet que redueix el risc de filtracions.  
- **Independència del núvol:** Ideal per a entorns tècnics o xarxes internes sense connexió a Internet.  
- **Codi obert i transparent:** Permet auditories de seguretat i personalització segons les necessitats de l’empresa.  
- **Cost nul i manteniment baix:** No requereix subscripcions ni dependències externes.  
- **Alta portabilitat:** El fitxer `.kdbx` pot emmagatzemar-se en dispositius xifrats, còpies de seguretat o sistemes compartits de manera segura.


---

▶️Fes click aqui per anar a la secció de [GUIA](Guia.md)

◀️Torna a [Enrera](README.md)

