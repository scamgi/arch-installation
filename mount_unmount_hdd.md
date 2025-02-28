Per accedere a un hard disk esterno collegato al tuo laptop con Arch Linux tramite terminale, segui questi passaggi:

1. **Identifica il dispositivo**: Apri il terminale e digita `lsblk` per visualizzare tutti i dispositivi di archiviazione collegati. Cerca il nome del dispositivo che corrisponde al tuo hard disk esterno, ad esempio `sdb1`.

2. **Crea un punto di mount**: Scegli una directory dove montare il disco, ad esempio `/mnt/external`. Crea la directory con:

   ```bash
   sudo mkdir -p /mnt/external
   ```


3. **Monta il dispositivo**: Monta l'hard disk esterno nella directory appena creata con:

   ```bash
   sudo mount /dev/sdb1 /mnt/external
   ```


   Assicurati di sostituire `/dev/sdb1` con il percorso corretto del tuo dispositivo.

4. **Accedi ai file**: Ora puoi accedere ai file del tuo hard disk esterno navigando nella directory di mount:

   ```bash
   cd /mnt/external
   ```


5. **Smonta il dispositivo**: Una volta terminato, smonta l'hard disk per rimuoverlo in sicurezza:

   ```bash
   cd ~
   sudo umount /mnt/external
   ```


Questi passaggi ti permetteranno di accedere e gestire il tuo hard disk esterno tramite terminale su Arch Linux. 