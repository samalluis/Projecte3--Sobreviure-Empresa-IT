# Fase Pràctica: Diagnosi de Noms (Auditoria amb CLI)

## Introducció

En aquesta pràctica s’ha realitzat una auditoria DNS emprant diferents eines de diagnosi en entorns Linux/macOS (amb `dig`) i Windows (amb `nslookup`).  
També s’han efectuat proves de resolució local per comprovar el funcionament de noms dins la xarxa interna.

L’equip utilitzat és un Zorin OS configurat amb dues interfícies de xarxa:
- Interfície 1 (NAT) per accés a Internet.  
- Interfície 2 (Pont) amb IP 192.168.7.1/24.

![imatge](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T06-Fonaments-del-servei-DNS/img/Captura%20de%20pantalla%202025-11-04%20165408.png)

![imat](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T06-Fonaments-del-servei-DNS/img/Captura%20de%20pantalla%202025-11-04%20165418.png)

![ima](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T06-Fonaments-del-servei-DNS/img/Captura%20de%20pantalla%202025-11-04%20165427.png)

---

## A. Diagnosi Avançada amb `dig` (Linux / macOS)

### Comanda 1: Consulta Bàsica de Registre A

**Comanda executada:**
```bash
dig xtec.cat A
```

**Captura de pantalla:**

![hola](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T06-Fonaments-del-servei-DNS/img/Captura%20de%20pantalla%202025-11-04%20165527.png)

**Anàlisi:**
- IP de resposta:  
- Valor TTL:  
- Servidor que ha respost:  
- Comentari: Explica breument què indica el registre A i per a què serveix.

---

### Comanda 2: Consulta de Servidors de Noms (NS)

**Comanda executada:**
```bash
dig tecnocampus.cat NS
```

**Captura de pantalla:**

![amsda](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T06-Fonaments-del-servei-DNS/img/Captura%20de%20pantalla%202025-11-04%20165613.png)

**Anàlisi:**
- Servidors de noms autoritatius:  
- Comentari: Explica què són els servidors autoritatius i quina funció tenen dins el DNS.

---

### Comanda 3: Consulta Detallada SOA

**Comanda executada:**
```bash
dig escolapia.cat SOA
```

**Captura de pantalla:**

![asdads](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T06-Fonaments-del-servei-DNS/img/Captura%20de%20pantalla%202025-11-04%20165644.png)

**Anàlisi:**
- Correu de l’administrador:  
- Número de sèrie del domini:  
- Comentari: Explica la importància del registre SOA i de cadascun dels seus camps principals.

---

### Comanda 4: Consulta de Resolució Inversa

**Comanda executada:**
```bash
dig -x 147.83.2.135
```

**Captura de pantalla:**

![nono](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T06-Fonaments-del-servei-DNS/img/Captura%20de%20pantalla%202025-11-04%20165720.png)

**Anàlisi:**
- Nom associat a la IP:  
- Tipus de registre obtingut (PTR):  
- Comentari: Quina utilitat té una resolució inversa i en quins casos s’utilitza?

---

## B. Comprovació de Resolució amb `nslookup` (Multiplataforma)

### Comanda 1: Consulta Bàsica no Autoritativa

**Mode interactiu:**
```bash
nslookup
> set type=A
> tecnocampus.cat
```

**Captura de pantalla:**

![sisi](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T06-Fonaments-del-servei-DNS/img/Captura%20de%20pantalla%202025-11-04%20174203.png)

**Anàlisi:**
- Resposta no autoritativa: Explica què significa que la resposta no sigui autoritativa.  
- Servidor que ha respost:  
- Comentari: Indica d’on prové la informació i per què pot ser considerada “no autoritativa”.

---

### Comanda 2: Consulta Autoritativa

**Mode interactiu:**
```bash
nslookup
> server [IP_del_primer_servidor_de_noms_obtingut]
> set type=A
> tecnocampus.cat
```

**Captura de pantalla:**

![ioioio](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T06-Fonaments-del-servei-DNS/img/Captura%20de%20pantalla%202025-11-04%20174149.png)

**Anàlisi:**
- Resposta obtinguda:  
- Diferències amb la consulta no autoritativa:  
- Comentari: Explica per què ara la resposta és autoritativa i com ho pots verificar.

---

## C. Resolucions Locals

### Proves de resolució local

**Objectiu:** Verificar que el sistema resol correctament noms definits al fitxer de configuració local (`/etc/hosts` o `C:\Windows\System32\drivers\etc\hosts`).

**Passos realitzats:**

1. Edició del fitxer de resolució local:  
   - Exemple Linux/macOS:  
     ```bash
     sudo nano /etc/hosts
     ```
   - Exemple Windows:  
     ```text
     192.168.1.10   servidorlocal.test
     ```

2. Comprovació amb `ping` o `nslookup`:
   ```bash
   ping servidorlocal.test
   ```

**Captura de pantalla:**

![adada](https://github.com/samalluis/Projecte3--Sobreviure-Empresa-IT/blob/main/T06-Fonaments-del-servei-DNS/img/Captura%20de%20pantalla%202025-11-04%20174436.png)

**Anàlisi:**
- Nom i IP resolts:  
- Comentari: Explica com el sistema prioritza la resolució local abans del DNS públic.

---

## Conclusions

Resum de les principals observacions:
- Diferències entre respostes autoritatives i no autoritatives.  
- Utilitats i avantatges de cada eina (`dig` i `nslookup`).  
- Importància de la resolució inversa i local.  
- Verificació de la configuració de xarxa i resolució de noms en entorns mixtos.

---

## Annexos

- Captures de pantalla completes.  
- Fitxers de configuració (si escau).  
- Observacions addicionals del professor o tècnic.

