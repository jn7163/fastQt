#FastQt ![travis](https://api.travis-ci.org/labsquare/fastQt.svg?branch=master) ![Qt](https://img.shields.io/badge/Qt-qmake-green.svg) [![Gitter](https://badges.gitter.im/labsquare/fastQt.svg)](https://gitter.im/labsquare/fastQt?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)
FastQt is the clone of [FastQC](http://www.bioinformatics.babraham.ac.uk/projects/fastqc/) application ported 
from Java to [C++/Qt5](https://www.qt.io/) 

![Preview](https://raw.githubusercontent.com/labsquare/fastQt/master/screenshot.gif)

##Installation 
### Ubuntu
deb package has not yet ready. But An [AppImage](http://appimage.org/) has been made for Linux x86_64 and has been tested on ubuntu 16.04.  
You can download it from [here](https://github.com/labsquare/fastQt/releases/download/0.1/fastqt-0.1-linux-x86_64.AppImage) and run it as follow : 

    chmod +x fastqt-0.1-linux-x86_64.AppImage
    ./fastqt-0.1-linux-x86_64.AppImage
    
### Archlinux
There is an AUR package for Archlinux. [Just get it from the AUR](https://aur.archlinux.org/packages/fastqt/).
    
    
Other package will come soon for Windows and MacOS. You can try to compile it anyway.
    
## Compilation 
### Prerequisites - Install KArchive
You need to install karchive before compiling FastQt.    
**From ubuntu** >xenial you can install it from repositories : 
 
     sudo apt install libkf5archive-dev

**From fedoar** >= 24 you can install it from repositories :

    sudo dnf install kf5-karchive-devel

**From source** : 

    git clone git://anongit.kde.org/extra-cmake-modules
    cd extra-cmake-modules
    mkdir build && cd build    
    cmake .. -DCMAKE_INSTALL_PREFIX=/usr/
    make && sudo make install
    cd ../..
    git clone git://anongit.kde.org/karchive.git
    cd karchive
    mkdir build && cd build 
    cmake .. -DCMAKE_INSTALL_PREFIX=/usr/
    make 
    sudo make install

### Install Qt >5.7

**From website** : Download Qt > 5.7 from https://www.qt.io/.   
Don't forget to check QtChart module during installation. 

**From ubuntu** : Qt 5.7 is not yet avaible with ubuntu. But you can add PPA to your software system. 
For exemple for xenial 

    sudo add-apt-repository ppa:beineri/opt-qt57-xenial
    sudo apt-get install qt57base qt57charts-no-lgpl
    source /opt/qt57/bin/qt57-env.shf

**From fedora** : Qt 5.7 is avaible

    sudo dnf install qt5-qtbase-devel qt5-qtcharts-devel 

### Compile FastQt 
Be sure you have the correct version of Qt (>5.7) by using qmake. You will find qmake in bin folder where you installed Qt. For exemple, if you installed Qt from ppa:beineri, you will find it under /opt/qt57/bin/qmake. Then launch the compilation from FastQC folder as follow.

     /opt/qt57/bin/qmake --version
     /opt/qt57/bin/qmake 
     make 
     sudo make install 
     
