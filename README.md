# arch-linux-theme
A customizable Arch Linux theme created step by step.

Step 1: Setting Up GRUB with the Vimix Theme
To enhance the look of GRUB, I used the Grub-theme-vimix, a stylish blur-themed design that gives your bootloader a modern touch. This theme supports 2K and 4K displays, making it a perfect choice for high-resolution setups.

The theme is available on the following GitHub repository:
🔗 vinceliuice/grub2-themes

To install it, follow these steps:

Clone the repository or download the theme files:

bash
Copy code
git clone https://github.com/vinceliuice/grub2-themes.git
Navigate to the downloaded directory:

bash
Copy code
cd grub2-themes
Run the installation script included with the theme:

bash
Copy code
sudo ./install.sh
The script will apply the theme automatically. Once done, update GRUB to finalize the changes:

bash
Copy code
sudo grub-mkconfig -o /boot/grub/grub.cfg
This method is straightforward and ensures the theme is correctly installed and applied. Enjoy a refined GRUB experience with Vimix! 

Step 2: Customizing SDDM with a Theme
To further enhance the visual appeal of your system, I recommend customizing the SDDM display manager with a stylish theme. I sourced my SDDM theme from this page, which offers a variety of options to choose from.

Recommended Installation Method:
The easiest way to install SDDM themes on Arch Linux or an Arch-based system is by using the AUR helper paru. Here’s how to do it:

Search for SDDM themes in the AUR:

bash
Copy code
paru -Ss sddm-theme
Choose a theme and install it. For example:

bash
Copy code
paru -S sddm-theme-<theme-name>
Applying the Theme:
Once the theme is installed, you need to update the SDDM configuration to use it:

Open the default configuration file for SDDM:

bash
Copy code
sudo nano /usr/lib/sddm/sddm.conf.d/default.conf
Locate the Theme setting and change its value to the name of the theme you just installed. For example:

ini
Copy code
[Theme]
Current=<theme-name>
Save the file and exit the editor.

Restart SDDM to apply the changes:

bash
Copy code
sudo systemctl restart sddm
This approach ensures a smooth setup process and allows you to take full advantage of the AUR's rich selection of themes. Transform your login screen with ease!

Step 3: Setting Up Waybar with a Custom Theme
To complete the aesthetic of your Arch Linux setup, I recommend configuring Waybar, a highly customizable bar for Wayland compositors like Hyprland. For this, I used the Macchiato theme from the Catppuccin Waybar GitHub repository.

Installing Waybar
First, ensure Waybar is installed on your system. You can install it using your package manager:

bash
Copy code
sudo pacman -S waybar
Applying the Macchiato Theme
Clone the Catppuccin Waybar repository:

bash
Copy code
git clone https://github.com/catppuccin/waybar.git
Navigate to the repository folder and locate the Macchiato theme:

bash
Copy code
cd waybar
Copy the configuration and theme files to your Waybar directory:

The config file goes into .config/waybar:
bash
Copy code
mkdir -p ~/.config/waybar
cp configs/macchiato.jsonc ~/.config/waybar/config
The CSS theme file goes into .config/waybar/themes:
bash
Copy code
mkdir -p ~/.config/waybar/themes
cp themes/macchiato.css ~/.config/waybar/themes/style.css
Important for Hyprland Users:
If you're using Hyprland, you need to update the configuration to ensure compatibility. In the config file (now located at ~/.config/waybar/config), replace any instance of wlr with hyprland. For example:

jsonc
Copy code
"modules-left": ["hyprland/workspaces"]
Start or restart Waybar to see the changes.

