# Seteando el entorno de trabajo #

----------
## Laravel ##
Necesita tener instalado composer

Instalar Laravel

`composer create-project laravel/laravel my_dir --prefer-dist`

## Bootstrap ##
Necesita bower, aunque podria instalarse con composer,o bien copiarse los archivos bajados desde el sitio. La ventaja de bower o composer es que se pueden actualizar las dependencias con solo correr un comando desde la consola.

Primero setear el directorio de trabajo para bower, en la carpeta public de la instalacion de Laravel, crear el directorio de trabajo para bower.

En la raiz de la instalación, al nivel del `composer.json`, crear un archivo y llamarlo `.bowerrc`

`
{
  "directory": "public/my_components"
}
`

Luego instalar bootstrap con bower

`bower install bootstrap`

## Repositorio Git ##

Luego iniciar el repo Git. Situarse en la raiz del proyecto creado y ejecutar en consola.

` git init ` inicia el repositorio

` git add . ` agrega todos los archivos al stage area

` git commit -m "Commit inicial."` primer commit

Configurar un repositorio remoto

` git remote add origin uri_al_repo_remoto `


`uri_al_repo_remoto` puede ser usando cualquiera de los protocolos https o git.

Ahora crear la rama `develop`

`git checkout -b develop` automáticamente git nos pone en esa rama.

Enviar todo al remoto `--all` le indica que lleve todas las ramas al remoto.

`git push -u --all origin`
