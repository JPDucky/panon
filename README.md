This project has been forked from rbn42/panon, which from what I can tell is all but abandoned at this point. I get annoyed with things on the KDE store that don't "just work" when downloaded, so I aim to fix that. Because this applet has the potential to be really cool.


An audio spectrum analyzer for KDE panel.


** Requirements
|                  | Version          |
|------------------+------------------|
| OpenGL / GLSL    | >= 3.0 / 1.30    |
| org.kde.kirigami | >= 2.3 (kf 5.42) |
| org.kde.newstuff | >= 1.1 (kf 5.63) |

~~If your KDE Framework is older than 5.63, see [[../../wiki/Troubleshooting#cannot-load-the-visual-effects-page-in-the-configuration-dialog][here]].~~

** Dependencies
   
*** openSUSE
```bash
sudo dnf install qt5-qtwebsockets \
    python3-docopt python3-numpy python3-PyAudio python3-cffi python3-websockets
```

*** Arch Linux
```bash
sudo pacman -S qt5-websockets \
    python-docopt python-numpy python-pyaudio python-cffi python-websockets 
```

*** openSUSE
```bash
sudo zypper in libQt5WebSockets5 \
    python3-docopt python3-numpy python3-PyAudio python3-cffi python3-websockets
```

*** Ubuntu
```bash
sudo apt-get install qml-module-qt-websockets \
    python3-docopt python3-numpy python3-pyaudio python3-cffi python3-websockets
```

*** Solus
```bash
sudo eopkg install qt5-websockets  \
   python-docopt PyAudio numpy python-cffi python-websockets
```

** Installation
~~*** Via KDE Store
1. Open the "Add Widgets" dialog of your desktop
2. Go to "Get New Widgets" in the bottom
3. Click "Download New Plasma Widgets"
4. Search for "panon"
5. Click "Install"~~

*** Via Command Line

```bash
git clone https://github.com/rbn42/panon.git
cd panon

# Download SoundCard and hsluv-glsl
git submodule update --init

# Build translations (optional)
mkdir build
cd build
cmake ../translations
make install DESTDIR=../plasmoid/contents/locale
cd ..

# To install
kpackagetool5 -t Plasma/Applet --install plasmoid

# To upgrade
kpackagetool5 -t Plasma/Applet --upgrade plasmoid
```

~~*** Via AUR
[[https://aur.archlinux.org/packages/plasma5-applets-panon/][plasma5-applets-panon]] is available for ArchLinux. ~~

~~** [[../../wiki/VisualEffects][Visual Effects]]
   
** [[../../wiki/Troubleshooting][Troubleshooting]]~~

** Credits
*** Main Contributors
    From old to new,
    |                                        | Contributor                                                    |
    |----------------------------------------+----------------------------------------------------------------|
    | AUR package maintained by              | [[https://aur.archlinux.org/packages/?K=mareex&SeB=m][mareex]], [[https://github.com/flying-sheep][flying-sheep (Philipp A.)]] |
    | German translation added by            | [[https://github.com/NLDev][NullDev (Chris)]]                  |
    | "Download New Effects" dialog added by | [[https://github.com/flying-sheep][flying-sheep (Philipp A.)]] |
    | Dutch translation added by            | [[https://github.com/Vistaus][Vistaus (Heimen Stoffels)]]                  |
    | "Monitor of Current Device" option  added by            | [[https://github.com/yuannan][Yuannan]]                  |
 And thanks for all the reported issues and suggestions, which I would not list here.
*** Third Party Source 
 | Files                                                                                           | Source                                                                                           | Licensed under |
 |-------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------+----------------|
 | [[file:panon/backend/source.py][source.py]] and [[file:panon/backend/spectrum.py][spectrum.py]] | adapted from [[https://github.com/ajalt/PyVisualizer][PyVisualizer]]                             |                |
 | =hsv2rgb= in [[file:plasmoid/contents/shaders/utils.fsh][utils.fsh]]                            | copied from [[https://gist.github.com/patriciogonzalezvivo/114c1653de9e3da6e1e3][GLSL-color.md]] |                |

