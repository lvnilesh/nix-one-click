```
# Assuming
# - your system is x86_64-linux
# - your harddrive device is /dev/sda
FLAKE="github:lvnilesh/nix-one-click#nixoneclick"
DISK_DEVICE=/dev/sda
sudo nix \
    --extra-experimental-features 'flakes nix-command' \
    run github:nix-community/disko#disko-install -- \
    --flake "$FLAKE" \
    --write-efi-boot-entries \
    --disk main "$DISK_DEVICE"
```
