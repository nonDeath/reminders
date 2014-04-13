# Seteando el entorno de trabajo #

## Laravel ##
Necesita tener instalado composer

Instalar Laravel
    
    composer create-project laravel/laravel my_dir --prefer-dist
    
### Remover el segmento `public` de la url ###

**Solución 1**

Personalmente recomiendo esta solución, aunque en shared hostings puede no ser viable.

Para esto necesitamos crear un alias para nuestro web site.

Primero crear un archivo .conf, en entorno de desarrollo se puede crear en la raiz del sitio. O bien, usando wampserver colocarlo en el directorio alias.

    
    Alias /mi-web "/path/a/mi/directorio/public"
    <Directory "/path/a/mi/directorio/public">
    	Options Indexes FollowSymLinks ExecCGI
    	AllowOverride all
    	Order Deny,Allow
    	Deny from all
    	Allow from 127.0.0.1
    	Allow from ::1
    	Allow from localhost
    </Directory>
    

En caso de haber colocado este archivo en la raiz del sitio, debe abrirse el archivo httpd.conf y agregar la linea
    
    Include "path/a/mi/archivo/*.conf"
    
Para que esto funcione debe reiniciarse el servicio apache.

### Way generators ###

Para ayudarse en el desarrollo es recomendable instalar los generadores de Jeffrey Way.

Abrir el archivo `composer.json` y agregar lo siguiente.

    "require-dev": { 
    	"way-generators": "2.*"
    }


Luego actualizar las dependencias.
    
    composer update --dev
    
Una vez completada la operación, Abrir `app/config/app.php`, y agregar un item más en el array de Service Providers.
    
    'Way\Generators\GeneratorsServiceProvider'
    
Referencia de comandos disponibles [https://github.com/JeffreyWay/Laravel-4-Generators](https://github.com/JeffreyWay/Laravel-4-Generators)

## Bootstrap ##
Necesita bower, aunque podria instalarse con composer,o bien copiarse los archivos bajados desde el sitio. La ventaja de bower o composer es que se pueden actualizar las dependencias con solo correr un comando desde la consola.

Primero setear el directorio de trabajo para bower, en la carpeta public de la instalacion de Laravel, crear el directorio de trabajo para bower.

En la raiz de la instalación, al nivel del `composer.json`, crear un archivo y llamarlo `.bowerrc`

    
    {
      "directory": "public/my_components"
    }
    

Luego instalar bootstrap con bower
    
    bower install bootstrap
    
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
