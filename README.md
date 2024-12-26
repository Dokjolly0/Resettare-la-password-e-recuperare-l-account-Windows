# Resettare la password utente Windows e recuperare i dati

## Passaggi da fare:

- Scaricare Rufus
```
https://rufus.ie/it/
```
- Scarica una iso linux
```
https://www.linuxmint.com/edition.php?id=316
```
- Avvia rufus e installa l'iso in una chiavetta
- Avvia il pc utilizzando come boot la pennetta usb
- Imposta la tastiera in italiano
```
setxkbmap it
```
- Installa chntpw
```
sudo apt install chntpw
```
- Diventa super user
```
sudo su
```
- Elenca tutti i dischi del sistema
```
fdisk -l
```
- Ti dara le seguenti opzioni, scegli il disco di windows:
    - /dev/sda1/ -> Boot
    - /dev/sda2/ -> Disco di windows
    - /dev/sda3/ -> Runtime di windows

- Monta il disco di windows (non sempre è sda2, il comando di prima serve per verificarlo)
```
mount -t ntfs /dev/sda2/ mnt
```
- Spostati nella cartella mnt
```
cd /mnt
```
- Visualizza tutti i file all'interno
c
- Spostati dentro la cartella config
```
cd Windows
cd System32
cd config
```
- Trova tutti i file che iniziano con la S
```
ls -l S*
```
- Resetta la password per l'utente desiderato
```
chntpw -u nomeutente SAM
1 (clean password)
q (quit)
y (save file)
```
- Riavvia il pc
```
reboot
```
- Apri un cmd come amministratore
- Imposta una nuova password
```
net user nomeutente passwordscelta
exit
```
- Lavoro finito!

