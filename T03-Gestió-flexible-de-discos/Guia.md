# **Guia: Gestió d’emmagatzematge amb Storage Spaces a Windows 11**

---

## 2.1 Creació del Pool d’emmagatzematge

### **Objectiu**
Crear un *Storage Pool* utilitzant tres discos virtuals de 10 GB de manera inicial com a base per a la resta de configuracions.

### **Procediment Creació Maquina**
1. Crear la maquina amb **4 GB de RAM** i **2 processadors**.

<img src="img/hardware.png" width="600">

3. Anem a l'apartat **d'Emmagatzematge** i a l'opcio de **Controlador: SATA** seleccionem l'opcio de **Afegeix disc dur** hi ha **Crea**.

<img src="img/controladorSATA.png" width="600">

<img src="img/creadiscdur.png" width="600">
 
4. Canviem el nom a disc01 o similar i assignem **10 GB d'espai**.

<img src="img/espaidiscos.png" width="600">
   
6. Creem i l'escollim. I repetim aquest proces dos cops mes per tenir el pool inicial.

<img src="img/pool.png" width="600">

### **Captura de pantalla resultat final**

<img src="img/maquina3.png" width="600">

### **Procediment Creació d'un Grup**

#### Objectiu
Apendre a com crear un grup d'emmagatzematge

1. Entrem a la maquina, obrim **Tauler de control → Sistema i seguretat → Espais d’emmagatzematge**.

<img src="img/taulerdecontrol.png" width="600">

<img src="img/sistemaiseguredad.png" width="600">

<img src="img/configuracioalmacenamiento.png" width="600">

2. Seleccionem **Crea un grup nou i un espai d’emmagatzematge nou**.

<img src="img/creargrup.png" width="600">

3. Seleccionar els discos necesaris de **10 GB cadascun** i creem el grup.

<img src="img/selecciomirroging.png" width="600">

---

## 2.2 Resiliència de mirall doble (Two-Way Mirror)

### **Objectiu**
Configurar un espai amb **mirall doble** per garantir la disponibilitat de les dades en cas de fallada d’un disc.

### **Procediment**
Discos necesaris:

<img src="img/A.png" width="600">


#### 1. Entrem al **"Administrador de discos"** e inicialitzarem un disc seleccionan els 3 discos que hem creat anteriorment utilitzant l'estil de particio **GPT**.

<img src="img/B.png" width="600">

#### 2. Ara entrem a **"Espacios de almacenamiento"** i crearem un nou grup i espai d'emmagetzematge

<img src="img/C.png" width="600">

#### 3. Seleccionem dos discos i creem el grup.

<img src="img/D.png" width="600">

#### 4. Configurar de la següent manera:
   - Tipus de resiliència: `Mirall doble (Reflejo doble)`  
   - Mida: `10 GB`  
   - Lletra d’unitat: `E:`

Com a de quedar:

<img src="img/E.png" width="600">

Un cop el tinguem configurat creem el grup.

<img src="img/F.png" width="600">


#### 5. Copiar alguns fitxers de prova a la unitat `E:`.

<img src="img/G.png" width="600">

#### 6. Deshabilitar un dels discos del pool per **simular una fallada**, per aixo tancarem la maquina i eliminarem un disc del pool

<img src="img/H.png" width="600">

<img src="img/J.png" width="600">


#### 8. Verifiquem que els fitxers continuen accessibles.

<img src="img/I.png" width="600">

#### 10. Tornar a habilitar el disc i comprovar la **reconstrucció automàtica**, per aixo anem a **"Espacios de almacenamiento"**, anem al grup i seleccionem l'opcio de afegir un disc al grup.


<img src="img/K.i.png" width="600">


<img src="img/L.png" width="600">

- Eliminem del grup el disc que te la fallada, per aixo tindrem que esperar un rato fins que hens sorti l'opcio de **"Quitar"**.

<img src="img/M.png" width="600">

<img src="img/N.png" width="600">

<img src="img/O.png" width="600">

- I finalment comprovem que la recontruccio s'aixi fet correctament, que es pot veure que s'ha fet correctament, ja que al afegir el tercer disc aquest a copiat tot el fitxers que tenia el primer, utilitzant el mateix espai de disc que el primer.

<img src="img/P.png" width="600">


---

## 2.3 Resiliència de paritat

### **Objectiu**
Crear un espai amb **resiliència de paritat** per mantenir les dades amb menys espai dedicat a còpies.

### **Procediment**
Discos que utilitzarem:

<img src="img/AP.png" width="600">

#### 1. Igual que abans anem a l'apartat de **"Espacios de almacenamiento"**, creem un nou grup i ara seleccionarem 3 discos.

<img src="img/BP.png" width="600">

#### 2. Configurem el grup de la següent manera:  
   - Tipus: `Paritat`  
   - Mida: `18 GB`  
   - Lletra d’unitat: `E:`

Com a de quedar: 

<img src="img/CP.png" width="600">

Un cop tenim a configuracio correcta creem el grup.

<img src="img/DP.png" width="600">

#### 3. Copiar fitxers de prova a la unitat.

<img src="img/EP.png" width="600">

#### 4. Deshabilitar un disc per simular una fallada, per aixo tanquem la maquina i eliminem un dels discos del pool.

<img src="img/FP.png" width="600">

<img src="img/HP.png" width="600">


#### 6. Verificar que les dades segueixen accessibles tot i la fallada.

<img src="img/GP.png" width="600">

#### 8. Reactivar el disc i comprovar la reconstrucció. Tanquem la maquina, afegim un nou disc al pool, obrim la maquina, anem a l'apartat **"Espacios de almacenamiento"**, al grup de paritat i seleccionem l'opcio de afegir un disc al grup.

<img src="img/IP.png" width="600">

<img src="img/JP.png" width="600">

- En aquesta captura es pot veure com el disc que acabem d'afegir ja s'esta utilitzant, recronstuint la informació que tenia el disc de la fallada:

<img src="img/KP.png" width="600">

- Eliminem el disc amb la fallada:

<img src="img/LP.png" width="600">

<img src="img/MP.png" width="600">

- I comprovem que la informació esta correcta:

<img src="img/NP.png" width="600">

---

## 2.4 Resiliència de mirall triple (Three-Way Mirror)

### **Objectiu**
Configurar un espai amb **mirall triple** per protegir les dades davant la fallada simultània de dos discos.

### **Procediment**
Discos que utilitzarem:

<img src="img/AT.png" width="600">

#### 1. Creem un nou grup en el qual seleccionarem 5 discos.

<img src="img/BT.png" width="600">

#### 3. La configurem de la seguent manera:  
   - Tipus: `Mirall de tres vies (Three-way mirror)`  
   - Mida: `10 GB`  
   - Lletra d’unitat: `E:`
Com a de quedar:

<img src="img/CT.png" width="600">

<img src="img/DT.png" width="600">

#### 2. Copiar fitxers de prova a la unitat.

<img src="img/ET.png" width="600">
  
#### 4. Deshabilitar un disc per simular una fallada (aquest podria soportar fins a dues fallades de disc). El proces es el mateix que els dos anteriors, apagar maquina, eliminem disc del pool.

<img src="img/GT.png" width="600">

#### 6. Verificar que els fitxers continuen accessibles.

<img src="img/FT.png" width="600">

#### 8. Reactivar els discos i comprovar la reconstrucció. apaguem la maquina, afegim un disc nou al pool, obrim la maquina, anem al grup i afegim el disc al grup.

<img src="img/HT.png" width="600">

<img src="img/IT.png" width="600">

<img src="img/JT.png" width="600">

<img src="img/KT.png" width="600">

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





