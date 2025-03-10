# ToDos

- [ ] lazygit 
- [ ] node 
- [ ] npm 
- [ ] bun (script personalizzato)
- [ ] gitui 
- [ ] Kitty 

pacman
- [ ] tree
- [ ] GHC
- [ ] erlang 


yay
- [ ] todoist-appimage 
- [ ] clockify-desktop 


## Things to put in the arch-commands

### Rimuovere timeout kernel
Per rimuovere il ritardo di tre secondi nel menu di avvio di systemd-boot, devi modificare il valore di Timeout nel file di configurazione di systemd-boot.

Procedura:

1. Apri un terminale e accedi come superutente (se necessario).


2. Modifica il file di configurazione di systemd-boot:

sudo nano /boot/loader/loader.conf


3. Trova la riga che contiene Timeout=3 (o un altro valore).


4. Modificala o aggiungila per impostare il timeout a 0:

Timeout=0


5. Salva il file (se usi nano, premi CTRL+X, poi Y, e infine Invio).


6. Riavvia il sistema per applicare le modifiche:

sudo reboot



Dopo questa modifica, il sistema dovrebbe avviarsi immediatamente senza mostrare il menu di scelta del kernel.


### connect arch while installation

To connect to WiFi while installing Arch Linux, follow these steps:

1. Check for Wireless Interface

Run the following command to list available network interfaces:

iwctl device list

Your WiFi interface is usually named wlan0 or something similar.

2. Start iwctl

Enter the interactive mode:

iwctl

3. Scan for Networks

Inside iwctl, run:

station wlan0 scan

Then list available networks:

station wlan0 get-networks

4. Connect to WiFi

To connect to a WiFi network, use:

station wlan0 connect "SSID"

Replace "SSID" with your actual network name. If the network requires a password, it will prompt you to enter it.

5. Check Connection

Exit iwctl by typing:

exit

Then verify internet connectivity with:

ping -c 5 archlinux.org

If you see successful responses, your WiFi is working.

Let me know if you run into any issues!

### boot fast hp laptop

If you see that the job is trying to run, and it's called dev/tmprm0, then run this command:

sudo systemctl mask dev-tpmrm0.device

### burn iso on linux

sudo pacman -S xfburn
xfburn

### vedere le partizioni in linux

sudo fdisk -l

