# **Guia: Gestió d’emmagatzematge amb Storage Spaces a Windows 11**

---

## 2.1 Creació del Pool d’emmagatzematge

### **Objectiu**
Crear un *Storage Pool* utilitzant tres discos virtuals de 10 GB de manera inicial com a base per a la resta de configuracions.

### **Procediment Creació Maquina**
1. Crear la maquina amb **4 GB de RAM** i **2 processadors**.

<img src="img/hardware.png" width="500">

3. Anem a l'apartat **d'Emmagatzematge** i a l'opcio de **Controlador: SATA** seleccionem l'opcio de **Afegeix disc dur** hi ha **Crea**.

<img src="img/controladorSATA.png" width="500">

<img src="img/creadiscdur.png" width="500">
 
4. Canviem el nom a disc01 o similar i assignem **10 GB d'espai**.

<img src="img/espaidiscos.png" width="500">
   
6. Creem i l'escollim. I repetim aquest proces dos cops mes per tenir el pool inicial.

<img src="img/pool.png" width="500">

### **Captura de pantalla resultat final**

<img src="img/maquina3.png" width="500">

### **Procediment Creació d'un Grup**

#### Objectiu
Apendre a com crear un grup d'emmagatzematge

1. Entrem a la maquina, obrim **Tauler de control → Sistema i seguretat → Espais d’emmagatzematge**.

<img src="img/taulerdecontrol.png" width="500">

<img src="img/sistemaiseguredad.png" width="500">

<img src="img/configuracioalmacenamiento.png" width="500">

2. Seleccionem **Crea un grup nou i un espai d’emmagatzematge nou**.

<img src="img/creargrup.png" width="500">

3. Seleccionar els discos necesaris de **10 GB cadascun** i creem el grup.

<img src="img/selecciomirroging.png" width="500">

---

## 2.2 Resiliència de mirall doble (Two-Way Mirror)

### **Objectiu**
Configurar un espai amb **mirall doble** per garantir la disponibilitat de les dades en cas de fallada d’un disc.

### **Procediment**
Discos necesaris:

![discos](img/A.png)

1. Entrem al **"Administrador de discos"** e inicialitzarem un disc seleccionan els 3 discos que hem creat anteriorment utilitzant l'estil de particio **GPT**.

![discos](img/B.png)

2. Ara entrem a **"Espacios de almacenamiento"** i crearem un nou grup i espai d'emmagetzematge

![discos](img/C.png)

3. Seleccionem dos discos i creem el grup.

![discos](img/D.png)

4. Configurar de la següent manera:
   - Tipus de resiliència: `Mirall doble (Reflejo doble)`  
   - Mida: `10 GB`  
   - Lletra d’unitat: `E:`

Com a de quedar:

![discos](img/E.png)

Un cop el tinguem configurat creem el grup.

![discos](img/F.png)


5. Copiar alguns fitxers de prova a la unitat `E:`.

![discos](img/G.png)

6. Deshabilitar un dels discos del pool per **simular una fallada**, per aixo tancarem la maquina i eliminarem un disc del pool

![discos](img/H.png)

![discos](img/J.png)


8. Verifiquem que els fitxers continuen accessibles.

![discos](img/I.png)

10. Tornar a habilitar el disc i comprovar la **reconstrucció automàtica**, per aixo anem a **"Espacios de almacenamiento"**, anem al grup i seleccionem l'opcio de afegir un disc al grup.


![discos](img/K.i.png)


![discos](img/L.png)

- Eliminem del grup el disc que te la fallada, per aixo tindrem que esperar un rato fins que hens sorti l'opcio de **"Quitar"**.

![discos](img/M.png)

![discos](img/N.png)

![discos](img/O.png)

- I finalment comprovem que la recontruccio s'aixi fet correctament, que es pot veure que s'ha fet correctament, ja que al afegir el tercer disc aquest a copiat tot el fitxers que tenia el primer, utilitzant el mateix espai de disc que el primer.

![discos](img/P.png)


---

## 2.3 Resiliència de paritat

### **Objectiu**
Crear un espai amb **resiliència de paritat** per mantenir les dades amb menys espai dedicat a còpies.

### **Procediment**
Discos que utilitzarem:

![discos](img/AP.png)

1. Igual que abans anem a l'apartat de **"Espacios de almacenamiento"**, creem un nou grup i ara seleccionarem 3 discos.

![discos](img/BP.png)

2. Configurem el grup de la següent manera:  
   - Tipus: `Paritat`  
   - Mida: `18 GB`  
   - Lletra d’unitat: `E:`

Com a de quedar: 

![discos](img/CP.png)

Un cop tenim a configuracio correcta creem el grup.

![discos](img/DP.png)

3. Copiar fitxers de prova a la unitat.

![discos](img/EP.png)
 
4. Deshabilitar un disc per simular una fallada, per aixo tanquem la maquina i eliminem un dels discos del pool.

![discos](img/FP.png)

![discos](img/HP.png)


6. Verificar que les dades segueixen accessibles tot i la fallada.

![discos](img/GP.png)

8. Reactivar el disc i comprovar la reconstrucció. Tanquem la maquina, afegim un nou disc al pool, obrim la maquina, anem a l'apartat **"Espacios de almacenamiento"**, al grup de paritat i seleccionem l'opcio de afegir un disc al grup.

![discos](img/IP.png)

![discos](img/JP.png)

- En aquesta captura es pot veure com el disc que acabem d'afegir ja s'esta utilitzant, recronstuint la informació que tenia el disc de la fallada:

![discos](img/KP.png)

- Eliminem el disc amb la fallada:

![discos](img/LP.png)

![discos](img/MP.png)

- I comprovem que la informació esta correcta:

![discos](img/NP.png)

---

## 2.4 Resiliència de mirall triple (Three-Way Mirror)

### **Objectiu**
Configurar un espai amb **mirall triple** per protegir les dades davant la fallada simultània de dos discos.

### **Procediment**
Discos que utilitzarem:

![discos](img/AT.png)

1. Creem un nou grup en el qual seleccionarem 5 discos.

![discos](img/BT.png)

3. La configurem de la seguent manera:  
   - Tipus: `Mirall de tres vies (Three-way mirror)`  
   - Mida: `10 GB`  
   - Lletra d’unitat: `E:`
Com a de quedar:

![discos](img/CT.png)

![discos](img/DT.png)

2. Copiar fitxers de prova a la unitat.

![discos](img/ET.png)
  
4. Deshabilitar un disc per simular una fallada (aquest podria soportar fins a dues fallades de disc).

![discos](img/GT.png)

6. Verificar que els fitxers continuen accessibles.

![discos](img/FT.png)

8. Reactivar els discos i comprovar la reconstrucció.

![discos](img/HT.png)

![discos](img/IT.png)

![discos](img/JT.png)

![discos](img/KT.png)

---

## Conclusió

Els resultats mostren que:
- El **mirall doble** ofereix protecció davant una fallada individual.  
- La **paritat** és més eficient en ús d’espai, tot i que més lenta en reconstrucció.  
- El **mirall triple** proporciona el màxim nivell de seguretat davant múltiples fallades.

En conclusió, **Storage Spaces** és una eina molt útil per a la gestió d’emmagatzematge amb redundància dins d’un entorn Windows professional.

---

Click aqui per anar a [README](README.md)

Click aqui per anar a [HOME](..)





