# OviOS | Remastering Linux Project
last update : 26 January 2023

## Introducing
ovios adalah linux yang dibuat untuk melakukan pentesting

## Download and Video Review

Download : GDrive

Video review : Youtube

## Thanks for Team
| Name | NIM |
|-|-|
| Imam Subekti | 22.01.4813 |
| Imam Subekti | 22.01.4813 |
| Imam Subekti | 22.01.4813 |
| Imam Subekti | 22.01.4813 |
| Imam Subekti | 22.01.4813 |
| Imam Subekti | 22.01.4813 |
| Imam Subekti | 22.01.4813 |
| Imam Subekti | 22.01.4813 |

## Base Information

|||
--|--|
| Name  | OviOS |
| Based on  | Zorin OS 16.2 Core |
| Desktop Interface | GNOME |
|Architecture|x86_64|
|Package management|DEB|
| Color Scheme | Nordic |
| Special for | Pentesting |
|||

## Software

|||
|-|-|
|Nmap|libreOffice|
|Metasploit|FireFox|
|Netcat|Burpsuite|
|SqlMap|Dirbuster|
|Fiddler|w3af|
|Sublist3r|Wireshark|


## Step by Step


1. Tahap Persiapan

    untuk melakukan remastering, anda diwajibkan untuk menginstall atau memiliki :

    - Komputer dengan OS linux, disini kami menggunakan ubuntu desktop 22.04
    - File ISO yang akan di remastering, disini kami menggunakan zorin OS 16.2 Core
    - Tools untuk melakukan remastering, disini kami menggunakan software Cubic

2. Buka Software Cubic

3. dasda

4. update repository

    ```Console
    # apt update
    ```

5. Install Berbagai software yang dibutuhkan

    ```Console
    # apt install git \
      curl 
    ```

6. Hapus semua bloodware bawaan zorin OS

    ```Console
    # apt purge gimp \
      aisleriot \
      gnome-mahjongg \
      gnome-maps \
      gnome-mines \
      gnome-contacts \
      gnome-sudoku \
      gnome-weather \
      quadrapassel \
      brasero \
      zorin-connect \
      zorin-appearance
    # apt autoremove
    ```

7. Download semua hal yang dibutuhkan seperti tema, icon, wallpaper, dan lain-lain

    ```Console
    # git clone https://github.com/EliverLara/Nordic.git /usr/share/themes/Nordic
    # git clone https://github.com/zayronxio/Zafiro-icons.git /usr/share/icons/zafiro
    #git clone https://github.com/Imamsubekti26/plymouth-linux.git /usr/share/plymouth/theme/virtosa-splash
    # curl 'https://images7.alphacoders.com/407/407469.jpg' --output /usr/share/backgrounds/joker.jpg
    ```

8. Ubah Splash Screen

    ```Console
    # update-alternatives --install /usr/share/plymouth/themes/default.plymouth default.plymouth /usr/share/plymouth/themes/virtosa-splash/virtosa-splash.plymouth 700
    # update-alternatives --set default.plymouth /usr/share/plymouth/themes/virtosa-splash/virtosa-splash.plymouth
    # update-initramfs -u
    ```

9. Ubah Wallpaper

    ```Console
    $ gsettings set org.gnome.desktop.background picture-uri 'file:///usr/share/backgrounds/joker.jpg'
    ```

10. Ubah Tema

    ```Console
    $ gsettings set org.gnome.desktop.interface gtk-theme 'Nordic'
    $ gsettings set org.gnome.desktop.wm.preferences theme 'Nordic'
    ```

11. Ubah Icon

    ```Console
    # mv /usr/share/icons/zafiro/Dark/ /usr/share/icons/Zafiro-icon-dark/
    # mv /usr/share/icons/zafiro/Light/ /usr/share/icons/Zafiro-icon-light/
    # rm -R /usr/share/icons/zafiro/

    $ gsettings set org.gnome.desktop.interface icon-theme 'Zafiro-icon-dark'
    ```

12. Ubah Cursor

    ```Console
    # mv /usr/share/themes/Nordic/kde/cursors/Nordic-cursors /usr/share/icons/

    $ gsettings set org.gnome.desktop.interface cursor-theme 'Nordic-cursors'
    ```

13. Ubah tampilan Taskbar
    ```Console
    $ gsettings set org.gnome.settings-daemon.plugins.xsettings overrides "{'Gtk/ShellShowsAppMenu': <0>}" && \
      gsettings set org.gnome.desktop.interface enable-hot-corners false && \
      gsettings set org.gnome.desktop.wm.preferences button-layout 'appmenu:minimize,maximize,close' && \
      gsettings set org.gnome.nautilus.preferences click-policy 'double' && \
      gsettings set org.gnome.shell disable-user-extensions false && \
      gsettings set org.gnome.shell disabled-extensions "['zorin-dash@zorinos.com', 'zorin-menu@zorinos.com', 'zorin-hide-activities-move-clock@zorinos.com']" && \
      gsettings set org.gnome.shell enabled-extensions "['drive-menu@gnome-shell-extensions.gcampax.github.com', 'remove-dropdown-arrows@mpdeimos.com', 'user-theme@gnome-shell-extensions.gcampax.github.com', 'x11gestures@joseexposito.github.io', 'zorin-appindicator@zorinos.com', 'zorin-desktop-icons@zorinos.com', 'zorin-printers@zorinos.com', 'zorin-taskbar@zorinos.com']" && \
      gsettings set org.gnome.shell.extensions.zorin-taskbar activate-single-window true && \
      gsettings set org.gnome.shell.extensions.zorin-taskbar animate-show-apps true && \
      gsettings set org.gnome.shell.extensions.zorin-taskbar click-action 'TOGGLE-SHOWPREVIEW' && \
      gsettings set org.gnome.shell.extensions.zorin-taskbar dot-style-focused 'CILIORA' && \
      gsettings set org.gnome.shell.extensions.zorin-taskbar dot-style-unfocused 'DOTS' && \
      gsettings set org.gnome.shell.extensions.zorin-taskbar group-apps true && \
      gsettings set org.gnome.shell.extensions.zorin-taskbar group-apps-use-launchers false && \
      gsettings set org.gnome.shell.extensions.zorin-taskbar intellihide false && \
      gsettings set org.gnome.shell.extensions.zorin-taskbar multi-monitors false && \
      gsettings set org.gnome.shell.extensions.zorin-taskbar panel-element-positions '{"0":[{"element":"showAppsButton","visible":true,"position":"stackedTL"},{"element":"activitiesButton","visible":false,"position":"stackedTL"},{"element":"leftBox","visible":true,"position":"stackedTL"},{"element":"taskbar","visible":true,"position":"centerMonitor"},{"element":"centerBox","visible":true,"position":"stackedBR"},{"element":"rightBox","visible":true,"position":"stackedBR"},{"element":"systemMenu","visible":true,"position":"stackedBR"},{"element":"dateMenu","visible":true,"position":"stackedBR"},{"element":"desktopButton","visible":false,"position":"stackedBR"}],"1":[{"element":"showAppsButton","visible":true,"position":"stackedTL"},{"element":"activitiesButton","visible":true,"position":"stackedTL"},{"element":"leftBox","visible":true,"position":"stackedTL"},{"element":"taskbar","visible":true,"position":"centerMonitor"},{"element":"centerBox","visible":true,"position":"stackedBR"},{"element":"rightBox","visible":true,"position":"stackedBR"},{"element":"systemMenu","visible":true,"position":"stackedBR"},{"element":"dateMenu","visible":true,"position":"stackedBR"},{"element":"desktopButton","visible":false,"position":"stackedBR"}]}' && \
      gsettings set org.gnome.shell.extensions.zorin-taskbar panel-element-positions-monitors-sync true && \
      gsettings set org.gnome.shell.extensions.zorin-taskbar panel-positions '{"0":"BOTTOM"}' && \
      gsettings set org.gnome.shell.extensions.zorin-taskbar panel-size 42 && \
      gsettings set org.gnome.shell.extensions.zorin-taskbar peek-mode true && \
      gsettings set org.gnome.shell.extensions.zorin-taskbar show-favorites true && \
      gsettings set org.gnome.shell.extensions.zorin-taskbar show-favorites-all-monitors true && \
      gsettings set org.gnome.shell.extensions.zorin-taskbar show-running-apps true && \
      gsettings set org.gnome.shell.extensions.zorin-taskbar show-tooltip true && \
      gsettings set org.gnome.shell.extensions.zorin-taskbar show-window-previews true && \
      gsettings set org.gnome.shell.extensions.zorin-taskbar window-preview-size 150 && \
      gsettings set com.zorin.desktop.auto-theme night-theme 'ZorinGrey-Dark' && \
      gsettings set org.gnome.shell.extensions.user-theme name 'Nordic' && \
      gsettings set org.gnome.shell favorite-apps "['firefox.desktop', 'org.gnome.Nautilus.desktop', 'org.gnome.Terminal.desktop']"

    ```

14. setting firefox supaya homepagenya ganti
    ```Console
    $ sed -i '44i user_pref("browser.startup.homepage", "about:home");\n' ~/.mozilla/firefox/*.default-release/prefs.js
    ```

    ## Credits

    - thanks to zorin OS (check on [Website]('https://zorin.com'))
    - thanks to EliverLara for Nordic Theme and Nordic Cursors (check on [Github]('https://github.com/EliverLara'))
    - thanks to zayronxio for Zafiro Icons (check on [Github]('https://github.com/zayronxio'))
    - thanks to lonewolf6738 for Joker Wallpaper (check on [Alphacoders]('https://alphacoders.com/users/profile/42440'))
