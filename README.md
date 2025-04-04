# Hyprland Setup

<details>
  <style>
    /* Hyprland-inspired styles */
    body {
      background-color: #232136;
      font-family: 'JetBrains Mono', monospace;
      color: #e0def4;
    }
    h1, h2, h3, h4, h5, h6 {
      color: #b9f2ff;
    }
    a {
      color: rgb(123, 130, 255);
      text-decoration: underline;
    }
  </style>
</details>

<div align="center" style="background-color: #232136; border-left: 5px solid rgb(111, 142, 235); padding: 1em; margin-bottom: 1em; color: #e0def4;">
  <h2 style="color: rgb(185, 242, 255);">Hello Fellow Hyprland Newcomers!</h2>
  <p style="font-size: 1.2em; font-weight: bold;">Welcome to my Hyprland Setup!</p>
  <p>I hope you find it useful and enjoyable.</p>
  <p style="color: #f6c177;">
    ❗ If something does not work, please <a href="https://github.com/Firstp1ck/Hyprland_simple-minimal_Setup/issues/new" rel="noopener noreferrer" style="color: rgb(123, 130, 255); text-decoration: underline;">open an issue</a> on this repository ❗<br>
    ❗I am always open to suggestions and feedback ❗
  </p>
</div>

## Example Image

![Hyprland Minimal Setup](example_images/minimal_setup_3.png)

## Example Terminal and Musik Visualizer

![Hyprland Minimal Setup](example_images/Kitty_cava_btop_fastfetch.png)

![Hyprland Minimal Setup](example_images/cava.gif)

## Table of Contents
- [Introduction](#introduction)
- [Environment Setup](#environment-setup)
- [Prerequisites](#prerequisites)
- [Setup Script Execution](#setup-script-execution)
- [Dependencies](#dependencies)
  - [Pacman Packages](#pacman-packages)
  - [AUR Extras](#aur-extras)
- [Installation & Configuration](#installation--configuration)
- [Running the Wallpaper Script](#running-the-wallpaper-script)
- [Customization](#customization)
  - [Wallpaper Management](#wallpaper-management)
  - [Window Rules](#window-rules)
  - [Keybindings](#keybindings)
  - [Appearance](#appearance)
  - [Autostart Applications](#autostart-applications)
  - [Monitor Configuration](#monitor-configuration)
- [Troubleshooting](#troubleshooting)
  - [Display and Monitor Issues](#display-and-monitor-issues)
  - [Wallpaper Management](#wallpaper-management-1)
  - [Authentication Issues](#authentication-issues)
  - [Performance Problems](#performance-problems)
  - [Application Integration](#application-integration)
  - [Configuration Debugging](#configuration-debugging)
  - [Keybinding Issues](#keybinding-issues)
  - [Recovery Options](#recovery-options)
- [Features](#features)
  - [Terminal Experience](#terminal-experience)
  - [Window Management](#window-management)
  - [Notification System](#notification-system)
  - [Visual Customization](#visual-customization)
  - [Security Features](#security-features)
- [Additional Resources](#additional-resources)
- [Dotfiles Overview](#dotfiles-overview)

## Introduction

This repository provides a comprehensive yet minimalistic Hyprland setup designed for users who want a modern, efficient, and customizable desktop environment.

### Quick Start

1. **Clones the repository into your home directory.**
   ```bash
   git clone https://github.com/yourusername/Hyprland_Simple_Setup.git ~/Hyprland_Simple_Setup
   ```
2. Navigate into the project directory and copy the dotfiles directory to your home directory:
   ```bash
   cd Hyprland_Simple_Setup
   cp -r dotfiles ~/.
   ```
3. Update the configuration files in the `dotfiles` folder to match your system (e.g. displays, wallpapers, and environment variables, see section: [Installation & Configuration](#installation--configuration)).
4. Run the setup script to install dependencies and configure your environment:
   ```bash
   cd ~/Hyprland_Simple_Setup/Setup
   ./Start_hyprland_setup.sh
   ```
5. Launch Hyprland. Enjoy your new desktop setup!

## Environment Setup

- The Setup is designed to run from EndeavourOS with KDE preinstalled. 
- You may need to modify the script for other distros or environments.
- Uses stow to manage dotfiles. The stow setupscript makes backups from the original dotfiles in the home directory.

## Prerequisites
- [Hyprland](https://hyprland.org/) installed.
- Utilities like `hyprctl`, `hyprpaper`, and a shell environment (like fish).
- `networkmanager` with`network-manager-applet` and `nm-connection-editor` installed.
- A directory containing your wallpapers.
- Vivaldi is used for browser in hyprland.conf, change it if you want to use another browser.
- Check Monitors in hyprland.conf at the start. Adapt it to your setup.

## Setup Script Execution

To install and configure Hyprland along with its dependencies, run:
```bash
cd ~/Hyprland_Simple_Setup/Setup
./Start_hyprland_setup.sh
```
This script automatically updates Pacman, installs the necessary packages, and configures Hyprland tools.

## Dependencies

### Pacman Packages
- hyprland (Main Hyprland Package)
- dolphin (File Manager)
- vivaldi (Browser)
- kitty (Terminal)
- waybar (Status Bar)
- hyprpaper (Dynamic Wallpaper Manager)
- wofi (App Launcher with)
- hyprlock (Lock Screen)
- hypridle (Idle Manager)
- hyprpolkitagent (Authentication Agent)
- polkit-kde-agent (Authentication Agent)
- gnome-keyring (Authentication Agent)
- xdg-desktop-portal-hyprland (Desktop Integration)
- xdg-desktop-portal-gtk (Desktop Integration)
- dunst (Notification Daemon)
- ttf-jetbrains-mono-nerd (Fonts)
- fish (Shell)
- stow (Utility for managing dotfiles)
- bat (cat replacement - used as alias in fish config)
- lsd (ls replacement - used as alias in fish config)
- btop (System Monitor - used as alias in fish config)

`sudo pacman -S hyprland dolphin kitty vivaldi waybar hyprpaper hyprcursor wofi hyprlock hypridle hyprpolkitagent xdg-desktop-portal-hyprland xdg-desktop-portal-gtk dunst gnome-keyring ttf-jetbrains-mono-nerd cava polkit-kde-agent fish stow bat lsd btop`

### AUR Extras
- xwaylandvideobridge-git (XWayland Video Bridge)
- hyprshot (Screenshot Tool)
- Visual Studio Code (Text Editor)

`yay -S xwaylandvideobridge-git hyprshot visual-studio-code-bin`

## Installation & Configuration

1. Clone or copy this repository to your machine.
2. Update the following files with your system-specific details:
   - **Wallpaper Configuration:**  
     Create or edit `~/.config/hypr/sources/change_wallpaper.conf` with:
     ```bash
     # Your wallpaper directory path
     WALLPAPER_DIR="$HOME/Pictures/Wallpapers"
     
     # Your monitor names (check with hyprctl monitors)
     MONITORS=(
         "DP-1"
         "HDMI-A-1"
         # Add more monitors as needed
     )
     ```
   - **Hyprlock Wallpaper Path:**  
     Update the `background` path in `~/.config/hypr/hyprlock.conf` to match your wallpaper directory.
     
   - **Display Configuration:**  
     Create or edit `~/.config/hypr/sources/displays.conf` to match your monitor setup:
     ```bash
     monitor=DP-1,2560x1440@144,0x0,1
     monitor=HDMI-A-1,1920x1080@60,2560x0,1
     # Add more monitor configurations as needed
     ```

   - **Environment Variables:**  
     Check `~/.config/fish/config.fish` for correct language settings:
     ```fish
     set -gx LC_ALL de_CH.UTF-8  # Change to your locale
     set -gx LANG de_CH.UTF-8    # Change to your locale
     set -gx LANGUAGE de_CH:en_US # Change to your language preferences
     ```

## Running the Wallpaper Script

The `change_wallpaper.sh` script:
- Checks if hyprpaper is running and starts it if necessary.
- Picks a random wallpaper from your specified directory (excluding the current one).
- Applies the new wallpaper to the specified monitors.

To run the script (Default Key Shortcut: Super(mainMod) + W):
```bash
./.config/hypr/change_wallpaper.sh
```

## Customization

### Wallpaper Management
- Modify supported file extensions in `change_wallpaper.sh`:
  ```bash
  # Add or remove file extensions
  WALLPAPER=$(find "$WALLPAPER_DIR" -type f \( -iname "*.jpg" -o -iname "*.png" -o -iname "*.webp" \))
  ```

### Window Rules
- Add custom window rules in `hyprland.conf`:
  ```ini
  # Example window rules
  windowrulev2 = float,class:^(org\.pulseaudio\.pavucontrol)$
  windowrulev2 = center,class:^(org\.pulseaudio\.pavucontrol)$
  windowrule = workspace 2, ^(vivaldi-stable)$
  windowrule = opacity 0.95, ^(Code)$
  ```

### Keybindings
- Customize shortcuts in `~/.config/hypr/sources/keybindings.conf`:
  ```ini
  # Media controls
  bind = , XF86AudioPlay, exec, playerctl play-pause
  bind = , XF86AudioNext, exec, playerctl next
  
  # Screenshot bindings
  bind = , Print, exec, hyprshot -m output
  bind = SHIFT, Print, exec, hyprshot -m region
  ```

### Appearance
- Modify Waybar styling in `style.css`:
  ```css
  /* Adjust transparency and colors */
  window#waybar {
    background: rgba(21, 18, 27, 0.8);
    color: #ffffff;
  }
  ```
- Configure Wofi menu appearance:
  ```css
  /* Customize menu size and colors */
  window {
    margin: 5px;
    background-color: #1e1e2e;
    border-radius: 15px;
  }
  ```

### Autostart Applications
- Add or modify autostart programs in `~/.config/hypr/sources/exec_once.conf`:
  ```bash  
  # User applications
  exec-once = vivaldi-stable
  exec-once = [workspace 3] code
  ```

### Monitor Configuration
- Advanced monitor setup examples:
  ```bash
  # High refresh rate gaming monitor
  monitor = DP-1,2560x1440@165,0x0,1
  
  # Vertical secondary monitor
  monitor = HDMI-A-1,1920x1080@60,2560x0,1,transform,1
  
  # Scale for HiDPI
  monitor = DP-2,3840x2160@60,5440x0,1.5
  ```

### Remove Default Tweaks
  ```
- Configure misc options to remove default settings:
  ```ini
  misc {
      vfr = true # Enable VFR (Variable Frame Rate) for Hyprland
      force_default_wallpaper = 0 # Set to 0 or 1 to disable the anime mascot wallpapers
      disable_hyprland_logo = true # If true disables the random hyprland logo / anime girl background. :(
  }
  ```

For more customization options, refer to:
- [Hyprland Configuration Reference](https://wiki.hyprland.org/Configuring/Variables/)
- [Waybar Configuration Guide](https://github.com/Alexays/Waybar/wiki/Configuration)
- [Wofi Documentation](https://hg.sr.ht/~scoopta/wofi)

## Troubleshooting

### Display and Monitor Issues
- Verify monitor names and configurations:
  ```bash
  # List all monitors and their current status
  hyprctl monitors
  
  # Check for any monitor hotplug events
  tail -f ~/.local/share/hyprland/hyprland.log | grep -i "monitor"
  ```
- If monitors are not detected properly:
  1. Ensure your GPU drivers are properly installed
  2. Try adding manual monitor configuration to `hyprland.conf`
  3. Check if your display cable is properly connected

### Wallpaper Management
- Wallpaper not changing:
  ```bash
  # Check if wallpaper directory exists and has correct permissions
  ls -la $WALLPAPER_DIR
  
  # Verify hyprpaper is running
  ps aux | grep hyprpaper
  
  # Check hyprpaper socket status
  ls -l /tmp/hypr
  ```
- Invalid wallpaper formats:
  1. Ensure images are in supported formats (jpg, png, webp)
  2. Check image file permissions
  3. Run `file` command on images to verify format

### Authentication Issues
- If polkit authentication fails:
  ```bash
  # Check if polkit agent is running
  ps aux | grep polkit
  
  # Restart polkit service
  systemctl restart polkit
  ```
- For keyring issues:
  1. Verify gnome-keyring is installed and running
  2. Check if PAM is properly configured

### Performance Problems
- For slow startup or lag:
  ```bash
  # Check startup time
  hyprctl version
  
  # Monitor resource usage
  htop
  
  # Check for GPU issues
  nvidia-smi  # For NVIDIA GPUs
  radeontop   # For AMD GPUs
  ```
- Reduce animation complexity in `hyprland.conf` if needed

### Application Integration
- XWayland applications not working:
  ```bash
  # Check if XWayland is running
  ps aux | grep Xwayland
  
  # Verify application compatibility
  echo $XDG_SESSION_TYPE
  ```
- Screen sharing issues:
  1. Ensure xdg-desktop-portal-hyprland is installed
  2. Check if necessary protocols are supported
  3. Verify xwaylandvideobridge is running for screen sharing

### Configuration Debugging
- Parse configuration errors:
  ```bash
  # Check Hyprland logs
  less ~/.local/share/hyprland/hyprland.log
  
  # Validate config syntax
  hyprctl reload
  ```
- Common configuration fixes:
  1. Check file permissions of config files
  2. Verify paths in configuration files are absolute
  3. Ensure no syntax errors in configuration files

### Keybinding Issues
- Test if keybindings are registered:
  ```bash
  # List all active bindings
  hyprctl binds
  
  # Monitor key events
  wev  # Install wev package if needed
  ```
- For non-working shortcuts:
  1. Check for conflicts with system shortcuts
  2. Verify correct syntax in keybindings configuration
  3. Ensure required programs are installed

### Recovery Options
- If Hyprland fails to start:
  1. Switch to another TTY (Ctrl+Alt+F2)
  2. Check logs: `less ~/.local/share/hyprland/hyprland.log`
  3. Try with minimal config: `mv ~/.config/hypr/hyprland.conf ~/.config/hypr/hyprland.conf.bak`

For persistent issues:
- Check [Hyprland GitHub Issues](https://github.com/hyprwm/Hyprland/issues)
- Join the [Hyprland Discord](https://discord.gg/hQ6M6xbvEM)
- Review system logs: `journalctl -b -p err`

## Features

### Terminal Experience
- **Kitty Terminal Integration**
  - Multiple layouts (splits, tabs, windows)
  - Session management and restoration
  - Custom key mappings:
    ```bash
    # Quick terminal splits
    ctrl+shift+enter -> new window
    alt+h/j/k/l -> window navigation
    ctrl+shift+t -> new tab
    ```

- **Fish Shell Enhancements**
  - Smart command history with search
  - Built-in completions and suggestions
  - Custom aliases for improved workflow:
    ```fish
    alias ls='lsd -lh --group-directories-first'
    alias top='btop'
    alias cat='bat'
    ```

- **Modern CLI Tools**
  - `bat`: Syntax highlighting for file viewing
  - `lsd`: Enhanced file listing with icons
  - `btop`: Resource monitoring with graphs
  - `fzf`: Fuzzy finding with preview
  - `fd`: Fast file search alternative

### Window Management
- **Dynamic Workspace Organization**
  - Per-monitor workspaces
  - Automatic workspace assignment rules

- **Advanced Window Controls**
  - Edge snap and resize
  - Window grouping and tabbing
  - Floating window management

- **Multi-Monitor Support**
  - Independent workspace per monitor

### Notification System
- **Dunst Configuration**
  - Critical notification persistence
  - Action button support

### Visual Customization
- **Waybar Integration**
  - Custom modules support
  - System tray integration
  - Workspace overview
  - Network management
  - Volume control
  - Battery monitoring

- **Theme Management**
  - Font configuration:
    - JetBrains Mono Nerd Font

### Security Features
- **Screen Locking**
  - Automatic screen locking
  - Custom lock screen styling
  - Multi-monitor support

- **Authentication**
  - Polkit integration
  - Keyring management
  - Secure screen sharing

## Additional Resources
- [Hyprland Wiki](https://wiki.hyprland.org/)
- [Hyprland GitHub Repository](https://github.com/vaxerski/Hyprland)
- [Waybar GitHub Repository (Wiki)](https://github.com/Alexays/Waybar/wiki)
- [Kitty Homepage (Wiki)](https://sw.kovidgoyal.net/kitty/)
- [Fish Shell (Wiki)](https://fishshell.com/docs/current/index.html)

## Dotfiles Overview

The repository’s dotfiles are organized as follows:

- **.config/waybar/**  
  Contains Waybar configuration files (e.g. config.jsonc, style.css) and scripts (e.g. toggle_waybar.sh) for managing your status bar.
  
- **.config/wofi/**  
  Includes Wofi configuration such as menu.css for customizing the launcher appearance.
  
- **.config/hypr/**  
  Holds Hyprland-related configurations and scripts like change_wallpaper.sh and fix-dolphin.sh.
  
- **.local/scripts/**  
  Provides helper scripts such as Start_stow_solve.sh which deploys the dotfiles using GNU stow.

To apply these dotfiles to your system, run the following:
  
```bash
cd ~/Hyprland_Simple_Setup/dotfiles
bash .local/scripts/Start_stow_solve.sh
```
