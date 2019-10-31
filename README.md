
A Different Audio Spectrum Analyzer

![](../../wiki/plasmoid/preview.png)

[Previews](../../wiki/Previews).

### Dependencies

#### Arch Linux

```bash
sudo pacman -S python-numpy python-pillow python-pyaudio python-websockets qt5-websockets qt5-3d 
```

PKGBUILD is available

#### Ubuntu

```bash
sudo apt-get install qml-module-qt3d qml-module-qt-websockets \
    python3-numpy python3-pyaudio python3-websockets python3-pil 
```

### Installation

#### Via Command Line

```bash
git clone https://github.com/rbn42/panon.git
cd panon/kde
kpackagetool5 -t Plasma/Applet --install plasmoid
```

Drag panon widget to your panel (eg. [latte-dock](https://github.com/psifidotos/Latte-Dock)).
![](../../wiki/plasmoid/step1.png)
![](../../wiki/plasmoid/step2.png)

### Shaders

Shaders are stored in [kde/plasmoid/contents/shaders/](kde/plasmoid/contents/shaders/). 

Providing panon is installed in your home directory, you can add your own shader files to ```~/.local/share/plasma/plasmoids/panon/contents/shaders/```. Panon can detect and load new shaders in this folder during runtime. The name of a shader file must be ended with ".frag".

#### Debugging Shaders

Neither KDE Panel nor Latte-Dock shows the errors caused by the shaders. To catch the error messages, `plasma-sdk` is required. To debug your shader, you must put your shader file in [kde/plasmoid/contents/shaders/](kde/plasmoid/contents/shaders/), and then start plasmoidviewer in a console. 
```bash
cd ./kde/
#Providing `plasma-sdk` is installed
plasmoidviewer --applet ./plasmoid/
```
In plasmoidviewer, go to the configuration window and pick your own shader. 
Then plasmoidviewer will run your shader and show the errors, if exist, in the console.

### Credits

Some code parts are adapted from [PyVisualizer](https://github.com/ajalt/PyVisualizer).
