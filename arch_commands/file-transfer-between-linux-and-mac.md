Yes! Since both computers are on the same WiFi network, you have several ways to transfer data between your macOS and Arch Linux systems:

### **1. SCP (Secure Copy) via SSH**  
If SSH is enabled on your Arch machine, you can use SCP from macOS:
- Enable SSH on Arch:
  ```bash
  sudo systemctl enable --now sshd
  ```
- Find your Arch machine's IP:
  ```bash
  ip a
  ```
- Transfer a file **from macOS to Arch**:
  ```bash
  scp /path/to/file username@arch-ip:/destination/path
  ```
- Transfer a file **from Arch to macOS**:
  ```bash
  scp username@arch-ip:/path/to/file /destination/path
  ```

### **2. rsync (Efficient File Syncing)**
For larger file transfers:
```bash
rsync -avz /local/path username@arch-ip:/remote/path
```

### **3. SMB or AFP (Network File Sharing)**
- **Mac to Arch:** Enable `samba` on Arch and access it from Finder (`smb://arch-ip/`).
- **Arch to Mac:** Use macOS's built-in **File Sharing** (enable SMB) and mount it on Arch.

### **4. Python HTTP Server**
For quick sharing:
```bash
cd /path/to/files && python3 -m http.server 8080
```
Then, access `http://arch-ip:8080` in macOS's browser.

### **5. Syncthing (Continuous File Sync)**
For frequent transfers, install [Syncthing](https://syncthing.net/) on both machines.

Let me know if you need details on any method! 🚀

