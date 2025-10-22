# what included:
This is based on Fedora-sway Spin, for default packages installed, please visit Fedora42 Sway-Spin Docs : <url>https://fedoraproject.org/spins/sway</url>

     tmux plugins  --> needs to install tpm and run the install_plugins.sh script if failed just remove the folders inside plugins and relaunch the script
    .tmux.conf
    .bashrc
    .config/kitty
    .config/waybar
    .config/sway
    .config/wofi
    .config/rofi
    .local/bin/  --> I use wofi for application launching also the fedora logo at mid top bar works the same, for custom scripts like fzfind or fzps including my fzbmark.py I use rofi, you can Add any scripts there
for live background we need to download and compile mpvpaper: https://github.com/GhostNaN/mpvpaper


keybindings are based on my Own preferals, Most Commons:

     Super+D --> rofi (as custom Script launcher)
     Super+r --> wofi (as application launcher)
     Super+l --> swaylock
     Super+E --> nautilus
     Super+q --> exit apps
     Super+shift+s --> ScreenShot
     Super+Shit+number --> move to Desktop
     Super+number --> go to Desktop
     Super+f --> FullScreen/exit FullScreen
     Ctrl+Alt+Delete --> Logout
     Super+Shift+r --> reload sway (be careful about mpvpaper not eat your RAM)

for laptops with nvidia integrated Cards, do not use sway-nvidia it's old and will break:

    switch to a different TTY (Ctrl+Alt+F3).

    Log in and run:

    sudo systemctl stop display-manager  # Stops GDM/GNOME
    sudo modprobe -r nvidia_drm nvidia_modeset nvidia_uvm nvidia
    sway

    After exiting Sway:

    sudo modprobe nvidia_drm nvidia_modeset nvidia_uvm nvidia
    sudo systemctl start display-manager  # Restarts GNOME

Need to install GitHub repos:

    git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm

    git clone --single-branch https://github.com/GhostNaN/mpvpaper
    # Build
    cd mpvpaper
    meson setup build --prefix=/usr/local
    ninja -C build
    # Install
    ninja -C build install

    https://github.com/ryanoasis/nerd-fonts/releases/download/v3.4.0/3270.zip
    https://github.com/subframe7536/maple-font/releases
    gsettings set org.gnome.desktop.interface gtk-theme "Adwaita-dark"
     
packages I installed via DNF are listed here:
    
    sudo dnf install qt5ct sway waybar meson git cmake gcc-c++ power-profiles-daemon mpv-devel wayland-devel wlroots-devel nautilus sway-wallpapers swayidle swaybg swayimg swaylock swappy slurp grim grimpicker fontawesome-fonts-all xclip fuzzel highlight wofi rofi fzf 
    pip install pygments
    
<img width="1920" height="1080" alt="swappy-20251022_121154" src="https://github.com/user-attachments/assets/8734a6e3-3a7b-40f9-a50d-cab52c93458f" />

<img width="1920" height="1080" alt="swappy-20251022_121135" src="https://github.com/user-attachments/assets/8a58d512-c4d8-4d18-9269-ba99136ce2f2" />

I didn't add dual monitor settings because it will change from system to system, Also I don't like tweaking gtk themes so much, "Adwaita-dark" is the only tweak I do, If you like you can also get it done via dconf-editor and other tools.<br>

Terminal also has few tricks:

     Ctrl+t --> fuzyfind 
     Ctrl+r --> fuzy history search
     Alt+c --> cd into folder of fuzy search results 
     cats --> bat implementation via python and highlight 

Peace :)<br>
My initial design was not as smooth as this rice, I got inspiration of <a href=https://github.com/diinki>diinki's</a> rice to give some soul to this rice :), if you want to go deep with customization I strongly advise to check her github page :)
