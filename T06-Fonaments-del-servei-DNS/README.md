# T06: Fonaments del servei DNS

## Descripció breu
Com a membres de l’equip tècnic d’**EverPia**, heu de resoldre un problema de **resolució de noms (DNS)** que afecta el client **DigiCore**, una empresa de màrqueting digital amb errors de connectivitat.  
La tasca consisteix a **auditar i explicar el funcionament del servei DNS**, tant en la seva part teòrica com pràctica.

---

## Objectius
- Entendre la **jerarquia i estructura** del DNS.  
- Comprendre el **procés de resolució** (iteratiu i recursiu).  
- Identificar **zones i registres DNS** (A, CNAME, MX, NS, SOA...).  
- Practicar amb **eines de diagnosi** com `dig` i `nslookup`.  
- Generar **materials formatius i tècnics** clars i útils per al client.

---

## Fase teòrica
Elabora una **píndola formativa (10-15 min)** que expliqui:
- L’estructura del DNS i el procés de resolució.  
- Tipus de zones: directa, inversa, primària i secundària.  
- Registres més comuns i conceptes essencials (TTL, SOA, resposta autoritativa, reenviadors, resolució local i mDNS).

---

## Fase pràctica
Demostra l’ús d’eines de diagnosi DNS en **Linux/macOS (dig)** i **Windows (nslookup)**.

### Exemples de comandes
```bash
dig xtec.cat A
dig tecnocampus.cat NS
dig escolapia.cat SOA
dig -x 147.83.2.135
```

---

Click aqui per anar al [VIDEO](Video.md)

Click aqui per anar a la [GUIA](guia.md)

Click aqui per tornar al [MENU PRINCIPAL](..)
