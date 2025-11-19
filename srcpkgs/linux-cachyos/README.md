# Installation

```bash
sudo xbps-install -R hostdir/binpkgs linux-cachyos
```

The kernel hooks will automatically:
- Generate initramfs with dracut
- Update GRUB configuration

Then reboot to use the new kernel.

## Manual steps (if hooks fail)

```bash
# Re-run kernel hooks
sudo xbps-reconfigure -f linux-cachyos

# Or manually generate initramfs and update bootloader
sudo dracut --force --hostonly /boot/initramfs-6.17.8-cachyos_1.img 6.17.8-cachyos_1
sudo grub-mkconfig -o /boot/grub/grub.cfg
```

Note: Kernel version format is `VERSION-cachyos_REVISION` (e.g., `6.17.8-cachyos_1`).
