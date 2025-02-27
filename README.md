# Arch Installation on HP Laptop

Questo repository serve per me per ricordarmi cosa faccio durante l'installazione di arch linux, comprendendo anche tutte le cose che faccio anche dopo l'installazione.

## Installazione di Arch

Inserisci il dvd di arch e fai partire il disco.

Una volta arrivato il prompt dei comandi, connetti il laptop alla rete.

### Connessione alla rete

...

### archinstall

Dopo la connessione a internet, esegui:

```sh
archinstall
```

Ricordati di:
- Cambiare il layout della tastiera.
- Selezionare systemd-boot come boot loader (è il più veloce).
- Usa un profilo minimale. Evita di installare un desktop environment.
- Come packages aggiuntivi ricordati di includere: git vim
- Per l'audio installa pipewire

## Post installazione

Per il post installazione, esegui questo comando per installare cosmic:

```sh
sudo pacman -S cosmic
```

Dopo l'installazione di cosmic, apri cosmic eseguendo il comando:

```sh
start-cosmic
```

Se viene aperto cosmic, ricordati di modificare il file .zshrc con il seguente comando da terminale:

```sh
vim ~/.zshrc
```

E poi alla fine del file inserisci:

```sh
# My code, in order to run cosmic when I log in
if [ -z "$DISPLAY" ] && [ "$(tty)" = "/dev/tty1" ]; then
  start-cosmic
fi
```

Se non vuoi inserire la riga manualmente, puoi aprire questo repository e eseguire:

```sh
sudo pacman -S stow
stow zsh
```

Così viene copiato il link a quel file della cartella zsh.

### git config

Per configurare git e per fare i commit devi eseguire il seguente comando:

```sh
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

Sostituisci John Doe con il tuo nome e cognome, e sostituisci la mail correttamente.

### software per il software development

Installa i software con il seguente comando:

```sh
yay -S visual-studio-code-bin
```

### Software per le utilities

```sh
sudo pacman -Sy vlc
sudo pacman -S rclone fastfetch ranger
yay -S discord telegram-desktop
```

### Per installare Mega

```sh
sudo pacman -S wget
wget https://mega.nz/linux/repo/Arch_Extra/x86_64/megasync-x86_64.pkg.tar.zst && sudo pacman -U "$PWD/megasync-x86_64.pkg.tar.zst"
```

### Per installare i filesystem

```sh
sudo pacman -S ntfs-3g
sudo pacman -S exfat-utils exfatprogs
```
