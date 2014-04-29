Instalar paquetes necesarios para el entorno de compilación:

    sudo apt-get install git gnupg flex bison gperf build-essential \
    zip curl libc6-dev libncurses5-dev:i386 x11proto-core-dev \
    libx11-dev:i386 libreadline6-dev:i386 libgl1-mesa-glx:i386 \
    libgl1-mesa-dev g++-multilib mingw32 tofrodos \
    python-markdown libxml2-utils xsltproc zlib1g-dev:i386
    
Hacer link de librerías para evitar errores:

    sudo ln -s /usr/lib/i386-linux-gnu/mesa/libGL.so.1 /usr/lib/i386-linux-gnu/libGL.so
    
Instalar java:

    sudo apt-get install openjdk-6-jdk openjdk-6-jre
    
Crear directorio para el repositorio binario y dar permisos:

    mkdir ~/bin
    PATH=~/bin:$PATH
    
Instalar el repositorio binario:

    curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
    chmod a+x ~/bin/repo

Crear directorio para alojar el código:

    mkdir MinimalUI
    cd MinimalUI

Iniciar repositorio para descargar el código:

    repo init -u git://github.com/MinimalUI/manifest.git -b master

Después, para descargar el manifest y el local_manifest, utiliza estos dos comandos:

    mkdir .repo/local_manifests

    curl -L -o .repo/local_manifests/minimal.xml -O -L https://raw.github.com/MinimalUI/manifest/master/minimal.xml
 
Comenzar la descarga de código:

    repo sync -f

Compilar:

    source build/envsetup.sh

    lunch

    <seleccionas tu dispositivo>

    make otapackage -jX (X = número de núcleos de tu ordenador)
