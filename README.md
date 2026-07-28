# Dotfiles Backup - Restore Instructions

## Fresh EndeavourOS Install Setup

1. Install git:
   sudo pacman -S --needed git

2. Clone this repo:
   git clone https://github.com/GlorpenSlorpen/dotfiles-backup.git ~/dotfiles-backup

3. Reinstall official packages:
   sudo pacman -S --needed - < ~/dotfiles-backup/pkglist-official.txt

4. Install yay (for AUR packages):
   sudo pacman -S --needed git base-devel
   git clone https://aur.archlinux.org/yay.git
   cd yay
   makepkg -si
   cd ..

5. Reinstall AUR packages:
   yay -S --needed - < ~/dotfiles-backup/pkglist-aur.txt

6. Restore dotfiles:
   cp ~/dotfiles-backup/.bashrc ~/dotfiles-backup/.zshrc ~/dotfiles-backup/.gitconfig ~/dotfiles-backup/.vimrc ~/ 2>/dev/null
   cp -r ~/dotfiles-backup/config/* ~/.config/

7. Reboot:
   reboot

## Notes
- Discord config/data is excluded (was too large for GitHub). Just reinstall Discord and log back in.
- Check that Hyprland, waybar, and other WM tools launch correctly after reboot.
- Wallpaper image files are NOT backed up, only configs referencing their paths.
