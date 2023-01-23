# Virtosa | Remastering Linux Project
last update : 26 January 2023

## Introducing
Virtosa adalah linux yang dibuat untuk melakukan pentesting

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
      gnome-tour \
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
    # git clone https://github.com/Imamsubekti26/plymouth-linux.git /usr/share/plymouth/theme/virtosa-splash
    ```

8. Ubah Icon

    ```Console
    # mv /usr/share/icons/zafiro/Dark/ /usr/share/icons/Zafiro-icon-dark/
    # mv /usr/share/icons/zafiro/Light/ /usr/share/icons/Zafiro-icon-light/
    # rm -R /usr/share/icons/zafiro/
    ```

9. Ubah wallpaper dan logo

    ```Console
    # mv /usr/share/plymouth/theme/virtosa-splash/joker.jpg /usr/share/backgrounds/
    # mv /usr/share/plymouth/theme/virtosa-splash/virtosa.jpg /usr/share/plymouth/
    ```

10. Ubah Cursor

    ```Console
    # mv /usr/share/themes/Nordic/kde/cursors/Nordic-cursors /usr/share/icons/
    ```

11. Untuk mengatur tema dan tampilan, GNOME bekerja dengan dconf, tetapi dconf hanya bisa digunakan untuk spesifik user saja, untuk mensetting global user, bisa menggunakan glib

    ```Console
    # mv /usr/share/plymouth/theme/virtosa-splash/*.override /usr/share/glib-2.0/schemas/
    # glib-compile-schemas /usr/share/glib-2.0/schemas/
    ```

12. Ubah Splash Screen

    ```Console
    # update-alternatives --install /usr/share/plymouth/themes/default.plymouth default.plymouth /usr/share/plymouth/themes/virtosa-splash/virtosa-splash.plymouth 700
    # update-alternatives --set default.plymouth /usr/share/plymouth/themes/virtosa-splash/virtosa-splash.plymouth
    # update-initramfs -u
    ```

13. setting tampilan saat pertama kali install

```Console
    # nano /etc/lsb-release
    # nano /etc/issue
    # nano /etc/issue.net
    # nano /etc/usr/share/ubiquity-slideshow/slides/welcome.html
```

14. ubah logo ini ```/usr/shell/gnome-shell/extensions/zorin-menu@zorinos.com/zorin-icon-symbolic.svg```

## Credits

- thanks to zorin OS (check on [Website]('https://zorin.com'))
- thanks to EliverLara for Nordic Theme and Nordic Cursors (check on [Github]('https://github.com/EliverLara'))
- thanks to zayronxio for Zafiro Icons (check on [Github]('https://github.com/zayronxio'))
- thanks to lonewolf6738 for Joker Wallpaper (check on [Alphacoders]('https://alphacoders.com/users/profile/42440'))
