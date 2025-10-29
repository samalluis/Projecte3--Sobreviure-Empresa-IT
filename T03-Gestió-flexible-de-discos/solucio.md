# 2. Part Windows: Espais d'Emmagatzematge (Storage Spaces)

### Configuració inicial: Creació d'un Storage Pool: 

Per començar crearem un pool d'emmagatzematge inicial amb tres discos de 10 GB cada un, per poder fer aixo entrarem al emmagetzematge de la nostra maquina i a l'apartat Controlador Sata crearem un de nou [capture] , aquest l'hi ficarem un nom com disc01 i seguidament l'hi assignarem els 10 GB d'emmagetzematge, aquest process el repetirem 2 cops mes.

captures d'exemple de com ha de quedar:

<img src="img/maquina2.png" alt="Texto" width="500" height="400">

<img src="img/maquina3.png" alt="Texto" width="500" height="400">

### Estudi de Configuracions: Demostrar i documentar la creació d'un Espai d'Emmagatzematge utilitzant:

Un cop ja tenim el pool fet arranquem la maquina, feu la instal·lació del windows11 i un cop ja a dins entrem al tauller de control, seguretat i sistemas, gestio d'emmagetzematge, [captures] quant arribem a la gestio d'emmagetzematge aquest ens deixara crear els grups de discos i fer la gestio que necesitem. [captura]

#### Resiliència de Mirall (Mirroring):
Per poder fer el sistema d'emmagetzematge del mirroging començarem seleccionant els discos, en aquest cas hem seleccionat 2, pero es poden seleccionar mes si es requereixes [captura] un cop seleccionats i creats haurem de triar quina gestio volem fer per aquest grup de discos i la capacitat que l'hi donarem, a la gestio escollirem la de doble mirall i assignarem una capacitat de 10 GB [Captures] 

#### Mirall triple: 

#### Resiliència de Paritat (Parity):




