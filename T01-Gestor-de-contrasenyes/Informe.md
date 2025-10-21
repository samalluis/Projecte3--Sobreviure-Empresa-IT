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

