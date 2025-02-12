# Decrypt
## Windows
```powershell
 veracrypt /v X:\path\to\volume /l Z /p YourPassword /q /m rm
```
Explanation:

    /v X:\path\to\volume → Specifies the encrypted volume (e.g., D:\MyVolume.hc).
    /l Z → Mounts the volume as drive letter Z:.
    /p YourPassword → Specifies the password for decryption.
    /q → Quiet mode (no GUI).
    /m rm → Mounts as a removable medium.

After execution, you can access the decrypted volume as Z: in Explorer.

## Linux
```sh
veracrypt --mount /path/to/volume /mnt/veracrypt1 --password=YourPassword
```
Explanation:

    --mount /path/to/volume → Specifies the encrypted volume (e.g., /home/user/secret.hc).
    /mnt/veracrypt1 → The mount point where the decrypted volume will be accessible.
    --password=YourPassword → Specifies the password for decryption.

After execution, the decrypted volume will be available at /mnt/veracrypt1.
