# Arch Linux Theme

A step-by-step guide to creating a customizable Arch Linux theme. This project enhances the visual appeal and functionality of your system with modern themes and tools.

---

## Step 1: Setting Up GRUB with the Vimix Theme

Give your bootloader a modern touch with the **Grub-theme-vimix**. This stylish theme supports 2K and 4K displays, making it perfect for high-resolution setups.

### Installation
1. Clone the theme repository:
   ```bash
   git clone https://github.com/vinceliuice/grub2-themes.git
   ```
2. Navigate to the downloaded directory:
   ```bash
   cd grub2-themes
   ```
3. Run the installation script:
   ```bash
   sudo ./install.sh
   ```
4. Update GRUB to apply the theme:
   ```bash
   sudo grub-mkconfig -o /boot/grub/grub.cfg
   ```

Enjoy a refined GRUB experience with Vimix!

---

## Step 2: Customizing SDDM with a Theme

Enhance your display manager by adding a stylish theme to SDDM.

### Installation
1. Search for SDDM themes using the AUR helper `paru`:
   ```bash
   paru -Ss sddm-theme
   ```
2. Install the desired theme:
   ```bash
   paru -S sddm-theme-<theme-name>
   ```

### Applying the Theme
1. Open the default configuration file for SDDM:
   ```bash
   sudo nano /usr/lib/sddm/sddm.conf.d/default.conf
   ```
2. Locate the [Theme] section and update it:
   ```ini
   [Theme]
   Current=<theme-name>
   ```
3. Restart SDDM to apply the changes:
   ```bash
   sudo systemctl restart sddm
   ```

---

## Step 3: Setting Up Waybar with a Custom Theme

Add a modern bar to your setup using Waybar and the Macchiato theme from the Catppuccin repository.

### Installation
1. Install Waybar:
   ```bash
   sudo pacman -S waybar
   ```
2. Clone the Catppuccin Waybar repository:
   ```bash
   git clone https://github.com/catppuccin/waybar.git
   ```
3. Copy the configuration files:
   - Config file to `~/.config/waybar`:
     ```bash
     mkdir -p ~/.config/waybar
     cp configs/macchiato.jsonc ~/.config/waybar/config
     ```
   - CSS theme file to `~/.config/waybar/themes`:
     ```bash
     mkdir -p ~/.config/waybar/themes
     cp themes/macchiato.css ~/.config/waybar/themes/style.css
     ```

### For Hyprland Users
Replace `wlr` with `hyprland` in your Waybar config file for compatibility:
```jsonc
"modules-left": ["hyprland/workspaces"]
```
Restart Waybar to apply the changes:
```bash
pkill waybar && waybar
```

---

## Step 4: Installing and Configuring Wlogout for Waybar

Add a sleek logout menu to your Waybar with Wlogout.

### Installation
1. Install wlogout using the AUR helper `yay`:
   ```bash
   yay -S wlogout
   ```

### Configuration
1. Edit the `style.css` file in `/etc/wlogout`:
   ```bash
   sudo nano /etc/wlogout/style.css
   ```
2. Update the background-color transparency (recommended: 0.7):
   ```css
   background-color: rgba(0, 0, 0, 0.7);
   ```
3. Save the file and exit.

### Adding Wlogout to Waybar
1. Add Wlogout to your Waybar configuration:
   ```jsonc
   "modules-right": [
       "wlogout"
   ]
   ```
2. Restart Waybar:
   ```bash
   pkill waybar && waybar
   ```

---

## Step 5: Locking Your Computer with Swaylock

Secure your system by adding a lock screen with Swaylock.

### Installation
1. Install swaylock-effects using `yay`:
   ```bash
   yay -S swaylock-effects
   ```

### Configuration
1. Add the following binding to your configuration file:
   ```bash
   bind=SUPER,L,exec,swaylock --clock --indicator --indicator-radius 120 --indicator-thickness 7 --effect-blur 5x3 --inside-color 00000055 --ring-color ffaaff --key-hl-color 8be9fd --line-color 00000000 --separator-color 00000000 --text-color ffffff --fade-in 0.2
   ```

This setup creates a sleek lock screen with a blur effect, clock, and customized colors.

---

## Conclusion

By following these steps, you can achieve a fully customized and visually appealing Arch Linux setup. Whether it's GRUB, SDDM, Waybar, Wlogout, or Swaylock, every detail contributes to a modern and functional desktop experience.

Happy customizing! 🎨🚀
