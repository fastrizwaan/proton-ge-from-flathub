# proton-ge-from-flathub
Create Proton-GE .tar.zst file from flathub installed `com.valvesoftware.Steam.CompatibilityTool.Proton-GE`
which can be used as a wine runner by lutris/playonlinux/winezgui/bottles etc. or other flatpak applications.

```
#!/bin/bash

sudo flatpak install flathub --system com.valvesoftware.Steam.CompatibilityTool.Proton-GE/x86_64/stable
SRC_DIR=$(dirname $(realpath $0))
echo "SRC_DIR = $SRC_DIR"

tar -I "zstd -19 -T4" -cvf Proton-GE-7.29.tar.zst -C "/var/lib/flatpak/runtime/com.valvesoftware.Steam.CompatibilityTool.Proton-GE/x86_64/stable/active/files" .
```
