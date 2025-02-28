# Formattare il disco

Per formattare il disco esterno appena collegato al tuo laptop con Arch Linux tramite terminale, segui questi passaggi:

1. **Identifica il dispositivo**: Apri il terminale e digita `lsblk` per visualizzare tutti i dispositivi di archiviazione collegati. Cerca il nome del dispositivo che corrisponde al tuo hard disk esterno, ad esempio `sdb`.

2. **(Opzionale) Crea una nuova tabella delle partizioni**: Se desideri rimuovere tutte le partizioni esistenti e crearne di nuove, utilizza `fdisk`:

   ```bash
   sudo fdisk /dev/sdb
   ```


   Nel prompt di `fdisk`, puoi utilizzare i seguenti comandi:

   - `n`: Crea una nuova partizione
   - `d`: Elimina una partizione esistente
   - `p`: Visualizza la tabella delle partizioni corrente
   - `w`: Scrive le modifiche e esce

   Per una guida dettagliata sull'uso di `fdisk`, consulta la [Guida alla formattazione dei dischi con fdisk](https://guide.debianizzati.org/index.php/Guida_alla_formattazione_dei_dischi_con_fdisk).

3. **Formatta la partizione**: Una volta creata o identificata la partizione desiderata (ad esempio, `/dev/sdb1`), puoi formattarla con il filesystem desiderato. Ecco alcuni esempi:

   - **ext4**: Ideale per sistemi Linux

     ```bash
     sudo mkfs.ext4 /dev/sdb1
     ```

   - **NTFS**: Utile per compatibilità con Windows

     ```bash
     sudo mkfs.ntfs /dev/sdb1
     ```

   - **FAT32**: Compatibile con la maggior parte dei dispositivi

     ```bash
     sudo mkfs.vfat -F 32 /dev/sdb1
     ```

   Nota: Per formattare in NTFS o FAT32, potrebbe essere necessario installare i pacchetti `ntfs-3g` e `dosfstools` rispettivamente.

4. **Monta la partizione**: Dopo aver formattato la partizione, crea un punto di mount e monta il dispositivo:

   ```bash
   sudo mkdir -p /mnt/external
   sudo mount /dev/sdb1 /mnt/external
   ```


   Ora puoi accedere al disco esterno tramite la directory `/mnt/external`.

5. **(Opzionale) Aggiorna `/etc/fstab` per il mount automatico**: Se desideri che il disco venga montato automaticamente all'avvio, aggiungi una riga al file `/etc/fstab`:

   ```bash
   /dev/sdb1  /mnt/external  ext4  defaults  0  2
   ```


   Assicurati di sostituire `ext4` con il filesystem utilizzato e di creare un backup di `/etc/fstab` prima di apportare modifiche.

Seguendo questi passaggi, potrai formattare e accedere al tuo disco esterno tramite terminale su Arch Linux. 