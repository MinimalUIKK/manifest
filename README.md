Crear directorio para alojar el código:

	mkdir MinimalUI
	cd MinimalUI

Iniciar repositorio para descargar el código:

    repo init -u git://github.com/MinimalUI/manifest.git -b master

Después, para descargar el local_manifest, utiliza estos dos comandos:

    mkdir .repo/local_manifests

    curl -L -o .repo/local_manifests/minimal.xml -O -L https://raw.github.com/MinimalUI/manifest/master/minimal.xml
 
Comenzar la descarga de código:

    repo sync -f
