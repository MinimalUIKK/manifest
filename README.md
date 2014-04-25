Crear directorio para alojar el código:

	mkdir MinimalUI
	cd MinimalUI
	mkdir .repo/local_manifests

Iniciar repositorio para descargar el código:

    repo init -u git://github.com/MinimalUI/manifest.git -b master

Después, para descargar el local_manifest, utiliza este otro comando:

    curl -L -o .repo/local_manifests/minimal.xml -O -L https://raw.github.com/MinimalUI/manifest/master/minimal.xml
 
Comenzar la descarga de código:

    repo sync -f
