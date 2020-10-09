# Pick a Linux Distro
* I tried [Phoenix OS](http://www.phoenixos.com/), which is actually Android and worked *really* nicely, but my OS randomly broke and got stuck in a boot loop
* [Ubuntu](https://ubuntu.com/) might be a reasonable choice, but I imagine that its desktop environment will be too resource-intensive for the weak T100TA
* I'm trying [Xubuntu](https://xubuntu.org/) to see if it works well

# Create a Bootable USB of your Linux Install Image
1. Download [Rufus](https://rufus.ie/) (I like the portable version)
2. Run Rufus (these instructions are using version 3.11.1678)
3. Click the "SELECT" button and select your Linux installation image
4. Make sure the correct device is selected in the "Device" dropdown (it should be your USB flash drive)
    * Remember that this will wipe out your USB flash drive
5. For "Persistent partition size", use the default of "0 (No persistence)
6. For "Partition scheme", use the default of "GPT"
7. For "Target system", use the default of "BIOS or UEFI" (the T100TA is UEFI)
8. For "Volume label", use whatever you want (I just keep it as the default)
9. For "File system", use the default of "FAT32 (Default)"
10. For "Cluster size", use the default (for Xubuntu, my default seems to be "8192 bytes (Default)")
11. Click "START"
12. If you're given any prompts where Rufus asks for permission, click "Yes" to give permission
13. If you're asked to write the image in "ISO Image mode" or in "DD Image mode", use the recommended of "ISO Image mode"
14. If Rufus warns you about all data being destroyed on the device, click "OK"
15. Rufus will do its thing for a while (you can track its progress in "Status")
16. Once Rufus is done, click "CLOSE" to exit Rufus
17. Download [`bootia32.efi`](bootia32.efi) and move it to the `EFI/BOOT` directory in your USB flash drive
    * This folder should probably already contain `BOOTx64.EFI`, `grubx64.efi`, and `mmx64.efi`
18. Eject your USB flash drive and then remove it

# Boot Into the Installer
## Disable Secure Boot
1. Power on your ASUS T100TA while repeatedly pressing the `F2` key to boot into the UEFI menu (called "Aptio Setup Utility")
2. Go to the "Security" tab
3. Enter the "Secure Boot menu"
4. Make sure "Secure Boot Support" is "\[Disabled\]"

# Acknowledgements
[This repo](https://github.com/5bentz/linux-asus-t100) was extremely helpful as I was figuring things out.
