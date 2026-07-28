# Dotfiles Backup - Restore Instructions

## Fresh EndeavourOS Install Setup

1. Install git:
2. 
   sudo pacman -S --needed git

3. Clone this repo:
4. 
   git clone https://github.com/GlorpenSlorpen/dotfiles-backup.git ~/dotfiles-backup

5. Reinstall official packages:
6. 
   sudo pacman -S --needed - < ~/dotfiles-backup/pkglist-official.txt

7. Install yay (for AUR packages):
8. 
   sudo pacman -S --needed git base-devel
   git clone https://aur.archlinux.org/yay.git
   cd yay
   makepkg -si
   cd ..

9. Reinstall AUR packages:
10. 
   yay -S --needed - < ~/dotfiles-backup/pkglist-aur.txt

11. Restore dotfiles:
12. 
   cp ~/dotfiles-backup/.bashrc ~/dotfiles-backup/.zshrc ~/dotfiles-backup/.gitconfig ~/dotfiles-backup/.vimrc ~/ 2>/dev/null
   cp -r ~/dotfiles-backup/config/* ~/.config/

13. Reboot:
   reboot

## Notes
- Discord config/data is excluded (was too large for GitHub). Just reinstall Discord and log back in.
- Check that Hyprland, waybar, and other WM tools launch correctly after reboot.
- Wallpaper image files are NOT backed up, only configs referencing their paths.
