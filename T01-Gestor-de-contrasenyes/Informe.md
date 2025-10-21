# Fase 1: Anàlisi i Justificació (Document d'Informe)

Heu de redactar un informe que justifiqui tècnicament la decisió de la Direcció i comparin les opcions. 

## Introducció i Justificació:

### · Explicació de per què les contrasenyes febles o reutilitzades són un risc crític per a l'empresa.

**Les contrasenyes febles o reutilitzades** representen un **risc crític** per a la seguretat empresarial. Atacs com els diccionaris o el credential stuffing permeten als atacants provar milions de combinacions de contrasenyes filtrades en altres serveis.

Això pot derivar en accessos no autoritzats, robatori d’informació confidencial o segrest de comptes.

### · La funció crucial d'un gestor de contrasenyes per mitigar aquests riscos.

Per mitigar aquests riscos, els gestors de contrasenyes permeten generar i emmagatzemar credencials úniques i robustes de manera segura, xifrada i centralitzada.

### 🧩 Bitwarden — Anàlisi Tècnica Detallada

| **Aspecte** | **Descripció** |
|--------------|----------------|
| **🔄 Sincronització (Extensions de Navegador)** | Chrome ✅ · Edge (Vora) ✅ · Safari ✅ · Firefox ✅ · Opera ✅ · Brave ✅ · Vivaldi ✅ · Tor ⚠️ (funciona amb limitacions, no suport oficial) |
| **💻 Facilitat d’Accés des de Múltiples Dispositius** | Windows ✅ · macOS ✅ · Linux ✅ · App Store (iOS) ✅ · Google Play (Android) ✅ |
| **🔐 Model de Seguretat** | Xifratge **extrem a extrem (E2EE)**. Derivació de claus amb **PBKDF2 SHA-256** o **Argon2id**, segons configuració de l’usuari. Model de **coneixement zero**: només l’usuari pot desxifrar les dades. |
| **💰 Cost / Model Freemium** | Versió gratuïta amb funcions essencials. Plans **Teams (4 €/mes/usuari)** i **Enterprise (6 €/mes/usuari)** amb opcions avançades de gestió, polítiques i integració SSO. |

### 🧩 KeePassXC — Anàlisi Tècnica Detallada

| **Aspecte** | **Descripció** |
|--------------|----------------|
| **💾 Emmagatzematge Local de l’Arxiu (KDBX)** | KeePassXC desa totes les credencials en un fitxer **local xifrat (.kdbx)** compatible amb **KeePass** (versions KDBX3 i KDBX4). Aquest arxiu pot contenir noms d’usuari, contrasenyes, notes, fitxers adjunts i claus TOTP. |
| **☁️ Independència del Núvol** | No depèn de cap servidor ni servei extern. L’usuari manté el **control total** sobre les seves dades i pot decidir si vol sincronitzar manualment el fitxer (p. ex. amb un núvol privat o USB). |
| **🧩 Model Open Source** | Projecte **de codi obert** sota llicència **GPLv3**, amb el codi font disponible a GitHub. Auditat per la comunitat, sense rastrejadors, anuncis ni subscripcions. Transparència total i seguretat verificada per tercers. |
| **📁 Portabilitat de l’Arxiu** | El fitxer `.kdbx` és **altament portable** i pot moure’s o copiar-se fàcilment entre sistemes (Windows, macOS, Linux). També pot sincronitzar-se mitjançant serveis com Nextcloud o Syncthing o guardar-se en una clau USB xifrada. |
| **⚙️ Funcions Principals (Resum)** | - Creació i gestió de bases de dades KDBX.<br> - Generador de contrasenyes integrat.<br> - Integració amb navegadors (Chrome, Firefox, Edge, Vivaldi, Brave, Tor).<br> - Importació des de Bitwarden, 1Password, Proton Pass, etc.<br> - Emmagatzematge TOTP i suport per YubiKey/OnlyKey.<br> - Sincronització amb KeeShare i integració SSH Agent. |
| **💰 Cost / Model** | 100 % **gratuït** i **lliure**, sense cap tipus de pla premium, publicitat ni subscripció. |
