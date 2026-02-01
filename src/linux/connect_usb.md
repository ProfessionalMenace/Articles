## How do you connect a USB to your linux computer?
Let me preface this by saying that yes, your desktop environment probably handles connecting and disconnecting USBs in a more convenient way.

1. First plug in your USB with pictures of cool cat
2. Print a list all the storage devices by using `lsblk` command (list storage block devices) <https://man7.org/linux/man-pages/man8/lsblk.8.html>
    * all connected devices should appear in the `/dev` directory
    * find which device corresponds to your USB
3. Create an empty directory let's call it `coolcats/` where you will be mounting your device to (usually in the `/mnt` directory but could be anywhere) using the `mkdir` command <https://man7.org/linux/man-pages/man2/mkdir.2.html>
4. Use the `mount` command with elevated privileges `sudo mount /dev/??? /mnt/coolcats` to mount the device onto a directory <https://man7.org/linux/man-pages/man8/mount.8.html>
5. Now that the device is mounted it behaves **almost** like a regular folder
6. Once you are done unmount coolcats using `sudo umount /mnt/coolcats` <https://man7.org/linux/man-pages/man8/umount.8.html>
7. unplug your USB
8. delete `coolcats/` directory (or not)

### BONUS:
you can mount your NTFS (windows) partition if you install `ntfs-3g` <https://en.wikipedia.org/wiki/NTFS-3G>, list your storage devices, find the correct one and mount it
```sh
lsblk --fs # list storage block devices and print their file systems
sudo mount --type ntfs /dev/??? /mnt/coolcats # mount specifying the --type argument
```