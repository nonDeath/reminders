# Seteando el entorno de trabajo #

----------
## Laravel ##
Necesita tener instalado composer

Instalar Laravel

`composer create-project laravel/laravel my_dir --prefer-dist`

## Bootstrap ##
Necesita bower, aunque podria instalarse con composer

Primero setear el directorio de trabajo para bower, en la carpeta public de la instalacion de Laravel, crear el directorio de trabajo para bower.

En la raiz de la instalación, al nivel del `composer.json`, crear un archivo y llamarlo `.bowerrc`

`
{
  "directory": "public/my_components"
}
`

Luego instalar bootstrap con bower

`bower install bootstrap`
