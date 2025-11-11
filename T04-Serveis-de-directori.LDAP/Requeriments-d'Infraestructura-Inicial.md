## 2. Requeriments d'Infraestructura Inicial

**R.INF.01** -
Configuració de la màquina Server (Server Hostname). server.innovatechXX.test 

- Configuracio de la maquina:
  
<img src="img/sistemamaquina.png" width="500">

<img src="img/xarxasmaquina.png" width="500">

<img src="img/confmaquina.png" width="500">

- Actualitza:
```
sudo apt install && sudo apt upgrade -y
```

<img src="img/actualitza.png" width="500">

- Hostname:

```
sudo nano /etc/hosts
```

<img src="img/innovatech.png" width="500">

<img src="img/compinnovatech.png" width="500">

Comanda per si necesitas canviar el nom del server: 
```
sudo hostnamectl set-hostname nom
```

**R.INF.02** -
Interfície de Xarxa Pública. NAT (Per accés a Internet i descàrrega de paquets).

**R.INF.03** -
Interfície de Xarxa Privada. Host-Only (Per a comunicació privada amb el Client virtual  i la màquina física).

Comandes:
```
sudo nano /etc/netplan/50-cloud-init.yaml
```
```
sudo netplan apply
```
- Configuracio xarxa

<img src="img/confnetplan.png" width="500">

<img src="img/netplanapply.png" width="500">

- Comprovació
<img src="img/ping.png" width="500">

<img src="img/ipa.png" width="500">

---

Click aqui per anar a [TASQUES D'IMPLEMENTACIO I CONFIGURACIO DEL SERVIDOR LDAP](Tasques-d'Implementació-i-Configuració-del-Servidor-LDAP.md)

Click aqui per anar a [INTEGRACIÓ DE CLIENT](Integració-de-Client.md)

Click aqui per anar a [HOME](...)

Click aqui per anar a [README](README.md)
