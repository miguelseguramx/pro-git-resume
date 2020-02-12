## CONFIGURACIÓN Y AYUDA

### Configuracion `git config`



### `git reset`

### `git rm`

### `git clean`

## RAMIFICAR Y FUSIONAR 

### `git branch`
### `git checkout`
### `git merge`
### `git mergetool`
### `git log`
### `git stash`
### `git tag`

## USANDO REPOSITORIOS REMOTOS

### `git fetch`
### `git pull`
### `git push`
### `git remote`
### `git archive`
### `git  submodule`

## INSPECCION Y COMPARACION 

### `git show`
### `git shortlog`
### `git describe`

## DEPURACION

### `git bisect`
### `git blame`
### `git grep`

## PARCHEO

### `git cherry-pick`
### `git rebase`
### `git revert`

#CONFIGURACION DE GITHUB
| | |
|-|-|
|git config core.editor         |        Configura un editor para escribir los mensajes de los commmits|
|  Comando | Descripción 
|  `git config core.editor `                 |   Configura un editor para escribir los mensajes de los commmits  |  
|  `git config --global alisas.co checkout` |  Crea un alias para el commando checkout con el nombre de co  |
|   `git config --global alias.ci commit`  | Crea un alias para el commando commit con el nombre de ci  |
|  `git config --global alias.st status`   |   Crea un alias para el commando status con el nombre de st |

>     -             git co / git ci / git st 

### Ayuda `git help`

| Comando  | Descripción  |
| ------------ | ------------ |
|  `git config --global alias.unstage 'reset HEAD --'` |    Los alias pueden servir para mejorar el uso intuitivo de git  |

    
>	    git unstage [file-name]

|  Comando |  Descripción |
| ------------ | ------------ |
|  `git config --global alias.last 'log -1 HEAD'` |    Te muestra cual fue la ultima confirmacion realizada |
|  `git config --global alias.visual '!gitk'`  | Si deseas ejecutar un commando externo usa ! antes de el

## OBTENER O CREAR REPOSITORIOS

| Comando | Descripción |
|------------|--------|
   | `git init`          |     Inicializa un nuevo repositorio
  |  `git clone url`       |    Copia un repositorio remoto 
   | `git clone path`     |     Copia un repositorio que tienes en otra carpeta

## IGNORAR LOS ARCHIVOS EN UN REPOSITORIO
### .GITIGNORE
    
| Selector | Descripción |
|-|-|
|*.a          |   Ignora todos los archivos .a |
|     !lib.a         |     Excepto el archivo lib.a |
|    /TODO       |     Ignora dentro del directorio raiz el directorio TODO |
|   build/       |       Ignora todos los archivos del directorio build |
|  doc/*.txt     |      Ignora todos los archivos txt dentro del directorio pero no los .txt de los subdirectorios|
|      doc/**/*.txt    |    Ignora todos los archivos txt del directorio doc|

## Comandos del dia a dia

### `git add`
| Comando| Descripción| 
|-| -|
 |   `git add* `       |       Añade todos los documentos nuevos o con cambios al stagin area|
 |   `git add *.jS `    |       Añade todos los documentos .js de la carpeta al stagin area|
  |  `git add LICENSE `       | Añade el documento LICENSE al stagin area|

### `git status`
| Comando| Descripción|
|-|-|
  |  `git status`                      |            Muestra los documentos preprarados|
|    `git status -s / git status --short`     |      Muestra los documentos preprados de manera compactada|
    
>     -    $git status -s                          
 
 | Banderas retornadas por  git status |Descripción |
 |-|-|
  |  -       M           |             Significa que el archivo fue modificado|
|    -       MM           |            Significa que en el archivo hay cambios preparados y otros sin preparar|
  |  -       A       |                     Significa que el archivo ya fue preprado|
 |   -       ??           |              Significa que es un archivo no rastreaso|
    
### `git diff`

 |Comando | Descripción |
 |-|-|
   | `git diff `            |  ¿Que has cambiado pero aun no has preparado? ¿Que has preparado y esta listo para confirmar? Muestra de manera exacta las lineas que fueron añadidas y eliminadas  que no estan preparados, si ya tus cambios estan preparados, no devolvera ninguna salida.|
|    `git diff -status`    |   Muestra lo que has preparado y sera incluido en el siguiente commit|
    

### `git commit`
|Comando |Descripción |
|-|-|
|    `git commit`             |                             Se abrira el editor de codigo para añadir el mensaje|
  |  `git commit -m 'initial project version'` |             El mensaje de confirmacion se escribira de manera directa|
   | `git commit -am 'initial project version'`     |     Con la bandera -a, git prepara todos los archivos rastreados antes del commit, ahorrandose el paso de git add |

### `git log`

|Comando  |Descripción | 
|-|-|
|  `git log`        |            Lista las confirmaciones o commmits realizados con SHA-1, nombre, correo, fecha y mensaje|
|  `git log -p `         |       Muestra las diferencias introducidas entre commits|
|    `git log -2 `           |     Muestra unicamente los ultimos dos commits|
|   `git log -<n> `      |        Muestra unicamente los ultimos n commits|
|    `git log -stat `       |      Muestra las estadisticas del commmit, cuantos archicos se modificaron, cuantas lineas se añadieron o eliminaron |
|  `git log --pretty= `     |     Muestra cada commit en ciertos formatos |
| `git log pretty=oneline`| Muestra el SHA-1, los apuntadores y los mensajes  

>        99e8ab6 (HEAD -> master) Commit Message    
    
| | |
|-|-|
| `git log pretty=short `| Muestra el SHA-1 completo, los apuntadores, el autor y  los mensajes |
| `git log pretty=full` | Muestra el SHA-1 completo, los apuntadores, el autor  y los datos del que realizo el commit a la rama actual y  los mensajes |
| `git log pretty=fuller `| Muestra el SHA-1 completo, los apuntadores, el autor y la fecha de creacion, los datos del sujeto que realizo el commit a la rama actual y la fecha de realizacion asi como los mensajes |
| `git log pretty=' % % %'`| Te permite especificar tu propio fomato, a continuacion hay un aseccion entera dedicada a ello |

#### Especificar  tu propio formato con `git log --pretty=''`

|Comando | Descripción|
|-|-|
|  `git log --pretty=''`   | Te permite especificar tu propio formato|
|  %H     |      Hash de la confirmacion|
|    %h    |        Hash de la confirmacion abreviado|
|    %t     |       Hash del arbol |
|    %T    |        Hash del arbol abreviado|
|   %P     |       Hashes de las confirmaciones padre |
|  %p      |      Hashes de las confirmaciones padre abreviados |
|      %an     |      Nombre del autor|
|       %ae     |      Direccion de correo electronico del autor |
|       %ad      |     Fecha de autoria |
|       %ar     |      Fecha de autoria relativa|
|       %cm    |       Nombre del confirmador|
|       %ce      |     Direccion de correo electronico del confirmador|
|      %cd        |   Fecha de confirmacion|
|       %cr     |      Fecha de confirmacion, relativa|
 |       %s     |       Asunto|
| `git log -2 --pretty='%h %an %cm %ad'` | Ejemplo de multiples selectores|

| Comando  | Descripción  |
|-|-|
 |   `git log --graph `        |   Muestra un grafico de confirmaciones y uniones, se puede usar con cualquier otra opcion|
 |  `git log --shortstat  `      |  Muestra solo las estadisticas|
 |   `git log --name-only  `     |   Muestra solo los archivos afectados|
 |   `git log --relative-date `  |   Muestra la fecha en formato relativo|
 |   `git log --since=2.weeks`   |   Muestra los commits ocurridos desde hace dos semanas|
 |   `git log --autor   `        |   Filtra los commmits por autor |
 |   `git log --grep  `          |   Filtra los commmits por palabras clave en los mensajes de confirmacion|
 |   `git log --all-match  `     |   Filtra los commmits por dos o mas tipos de opciones como autor y palabras claves|
 |   `git log --S `              |   Recibe una cadena y solo muestra las confirmaciones que cambiaron el codigo añadiendo o eliminando una cadena|
    
>            git log --Sfunction_name
    
    
 | | |
 |-|-|
 |`git log --/src/js/app.js`| Debe ser la ultima opcion, recibe una ruta y muestra los commits que introdujeron cambios a un determinado archivo |
 |`git log --since, --after`| Muestra los commits hechas despues de la fecha especificada|
 |git config --global alisas.co checkout      |  Crea un alias para el commando checkout con el nombre de co |
 |git config --global alias.ci commit         |  Crea un alias para el commando commit con el nombre de ci |
 |git config --global alias.st status         |  Crea un alias para el commando status con el nombre de st |

    >             git co / git ci / git st 
    
  | | |
  |-|-|
  |git config --global alias.unstage 'reset HEAD --'  | Los alias pueden servir para mejorar el uso intuitivo de git |
    
    >             git unstage [file-name]
    
  | | |
  |-|-|
  |git config --global alias.last 'log -1 HEAD'    |    Te muestra cual fue la ultima confirmacion realizada|
  |git config --global alias.visual '!gitk'        |    Si deseas ejecutar un commando externo usa ! antes de el|

    
#INICIALIZAR UN REPOSITORIO

   | | |
   |-|-|
   |git init            |   Inicializa un nuevo repositorio    |
   |git clone url       |   Copia un repositorio remoto |
   |git clone path      |    Copia un repositorio que tienes en otra carpeta|

#AÑADIR DOCUMENTOS AL AREA DE preparacion

   | | |
    |-|-|
    |git add*               | Añade todos los documentos de la carpeta al stagin area|
    |git add *.jS           | Añade todos los documentos .js de la carpeta al stagin area|
    |git add LICENSE        | Añade el documento LICENSE al stagin area|

#IGNORAR LOS ARCHIVOS EN UN REPOSITORIO
  ##.gitignore

  | | |
  |-|-|
  | *.a            |     #Ignora todos los archivos .a |
  | !lib.a         |    #Excepto el archivo lib.a |
  | /TODO          |     #Ignora dentro del directorio raiz el directorio TODO|
  | build/         |     #Ignora todos los archivos del directorio build|
  | doc/*.txt      |     #Ignora todos los archivos txt dentro del directorio pero no los .txt de los subdirectorios|
  | doc/**/*.txt   |     #Ignora todos los archivos txt del directorio doc|
    

#MUESTRA LOS DOCUMENTOS EN EL AREA DE PREPARACION
  
  | | |
  |-|-|
  |git status                               |   Muestra los documentos preprarados |
  |git status -s / git status--short        |   Muestra los documentos preprados de manera compactada |
    
    >    $git status -s    
    
   | | |
    |-|-|
    |       M  index.html         |         M    Significa que fue modificado |
    |       MM index.css          |         MM   Significa hay cambios preparados y sin preparar, MAM |
    |-       A  README             |         A    Significa que fue preprado |
    |-       ?? LICENSE            |         ??   Significa que es un archivo no rastreaso| 
    
    
| | |
 |-|-|
  |git diff          |     ¿Que has cambiado pero aun no has preparado? ¿Que has preparado y esta listo para confirmar? Muestra de manera exacta las lineas que fueron añadidas y eliminadas que no estan preparados, si ya tus cambios estan preparados, no devolvera ninguna salida. |
  |git diff -status  |     Muestra lo que has preparado y sera incluido en el siguiente commit |
    

#REALIZA CONFIRMACIONES 
  
  | | |
  |-|-|
  |git commit                                     |     Se abrira el editor de codigo para añadir el mensaje |
  |git commit -m 'initial project version'        |     El mensaje de confirmacion se escribira de manera directa |
  |git commit -a -m 'initial project version'     |     Con la bandera -a, git prepara todos los archivos rastreados antes del commit, ahorrandose el paso de git add|
    
#REVISAR EL HISTORIAL DE CONFIRMACIONES
   
  | | |
  |-|-|
  |git log                |    Lista las confirmaciones o commmits realizados con SHA-1, nombre, correo, fecha y mensaje |
  |git log -p             |    Muestra las diferencias introducidas entre commits|
  |git log -2             |    Muestra unicamente los ultimos dos commits|
  |git log -<n>           |    Muestra unicamente los ultimos n commits|
  |git log -stat          |    Muestra las estadisticas del commmit, cuantos archicos se modificaron,  cuantas lineas se añadieron o eliminaron|
  |git log --pretty       |    Muestra cada commit en ciertos formatos|
    
   
        >        oneline    short    full    fuller    format
    
    
   | | |
    |-|-|
    | git log --pretty=format  |  Te permite especificar tu propio formato|

   | | |
    |-|-|       
    |       %H         |   Hash de la confirmacion |
    |       %h         |   Hash de la confirmacion abreviado|
    |       %t         |   Hash del arbol |
    |       %T         |   Hash del arbol abreviado|
    |       %P         |   Hashes de las confirmaciones padre |
    |       %p         |   Hashes de las confirmaciones padre abreviados|
    |       %an        |   Nombre del autor|
    |       %ae        |   Direccion de correo electronico del autor |
    |       %ad        |   Fecha de autoria |
    |       %ar        |   Fecha de autoria relativa|
    |       %cm        |   Nombre del confirmador|
    |       %ce        |   Direccion de correo electronico del confirmador|
    |       %cd        |   Fecha de confirmacion|
    |       %cr        |   Fecha de confirmacion, relativa|
    |       %s         |   Asunto|
    
   | | |
    |-|-|
    |git log --graph            |  Muestra un grafico de confirmaciones y uniones, se puede usar con cualquier otra opcion |
    |git log --shortstat        |  Muestra solo las estadisticas |
    |git log --name-only        |  Muestra solo los archivos afectados |
    |git log --relative-date    |  Muestra la fecha en formato relativo |
    |git log --since=2.weeks    |  Muestra los commits ocurridos desde hace dos semanas |
    |git log --autor            |  Filtra los commmits por autor  |
    |git log --grep             |  Filtra los commmits por palabras clave en los mensajes de confirmacion |
    |git log --all-match        |  Filtra los commmits por dos o mas tipos de opciones como autor y palabras claves |
    |git log --S                |  Recibe una cadena y solo muestra las confirmaciones que cambiaron el codigo añadiendo o eliminando una cadena |
    
     >             git log --Sfunction_name
   | | |
    |-|-|
    |git log --/src/js/app.js  |   Debe ser la ultima opcion, recibe una ruta y muestra los commits que introdujeron cambios a un determinado archivo |
    |git log --since, --after  |   Muestra los commits hechas despues de la fecha especificada |
    
     >             git log --since="2008-10-01"
    
   | | |
    |-|-|
    | git log --until, --before   |   Muestra los commits hechos antes de una fecha |
    

#DESHACER UN CAMBIO REALIZADO
    
| | |
|-|-|
| git commit --amend                 |                  Regresa la ultima confirmacion reaizada al area de preparacion para que agregues documentos o cambies el mensaje de confirmacion |
|git reset HEAD index.js             |                Quita un archivo del area de preparacion |
|git checkout --<file>               |                Devuelve un archivo al estado original de la ultima confirmacion |

#ELIMINAR ARCHIVOS
   
  | | |
  |-|-|
  |git rm 'index.html'      | Elimina el archivo de los archivos rastreados y tambien de tu directorio |
  |git rm \*.log            | Elimina todos los archivos que acaben con .log |
  |git rm log/\*.log        | Elimina todos los archivos que acaben con .log dentro de log |
  |git rm --cached node/    | Elimina el archivo de los archivos rastreados pero no de tu disco duro |

#RENOMBRAR ARCHIVOS
  
  | | |
  |-|-|
  | git mv file_from file_to  |  Renombra un archivo y lo añade al area de preparacion, es mas comodo que: 
> 1. mv file_from file_to 
> 2.  rm file_from 
> 3.  git add file_to |

  | | |
  |-|-|
  |git remote              |   Muestra los nombres de cada uno de los remotos que tienes especificados|
  |git remote -v           |   Muestra las URLs que git ha asociado a los nombres, un repositorio con multiples colaboradores, se veria asi|

# ETIQUETADO 

###     Se usa tipicamente para marcar puntos importantes en el historial como versiones de lanzamiento
    
   | | |
   |-|-|
   | git tag                |   Lista las etiquetas en orden alfabetico |
   | git tag -l             |   Lista las etiquetas con un patron  articular como una serie particular |
 | git tag -l 'v1.8.5*'  |    Muestra las etiquetas de la serie 1.8.5 |
    
    
###     Hay dos tipos de etiquetas, las ligeras y las anotadas, las ligeras son solo un puntero en un commit especifico, las anotadas son objetos enteros, tiene un checksum, un etiquetador, correo y fecha
    
   | | |
   |-|-|
   |git tag -a [tag-name] -m '[tag-message]'   |    Crea una etiqueta anotada y un mensaje asociado a esta |    
   |git show [tag-name]                  |   Muestra la informacion de la etiqueta anotada y del commit marcado dependiendo de que tipo de etiqueta sea|
   |git tag [tag-name]                   |   Crea una etiqueta ligeras|
   |git tag -a [tag-name] checksum       |   Crea una etiqueta con un commit anterior|    
   |git push [server-name] [tag-name]    |   Manda un etiqueta especifica a un repositorio remoto|
  |git push [server-name] --tags        |   Manda todas las etiquetas a un servidor remoto|    
  |git checkout -b [branch-name] [tag-name]   | Una etiqueta no es algo que se pueda mover, si deseas modificarla es necesario que creeas una nueva rama|
  |git describe master                     |  Te mostara el numero de la ultima etiqueta y el numero de  confirmaciones despues de esta, le da preferencia a la etiquetas anotadas|

#     Firmar etiquetas:

#TRABAJAR CON REPOSITORIOS REMOTOS
    
  | | |
  |-|-|
  |       backdoor  | https://github.com/bakkdoor/grit (fetch) |
  |       bakkdoor  | https://github.com/bakkdoor/grit (push) |
  |     cho45     | https://github.com/cho45/grit (fetch)|
  |       cho45     | https://github.com/cho45/grit (push)|
  |       koke      | https://github.com/koke/grit (fetch)|
  |      koke      | https://github.com/koke/grit (push)|
  |      origin    | https://github.com/origin/grit (fetch)|
  |      origin    | https://github.com/origin/grit (push)|
    
   | | |
   |-|-|
   |git remote add [nombre] [url]               |  Sirve añadir un repositorio remoto y asociarlo a un nombre ::que se pueda referenciar |
  |git fetch [nombre]                          |  Sirve para traer toda la informacion que tiene [nombre] pero que yo no tengo en mi repositorio |
  |git fetch origin                            |  Se trae todo el trabajo nuevo que ha sido enviado al servidor desde que lo clonaste |
  |git pull                                    |  Trae una rama remota y automaticamente trata de combianrla con la rama en la que estas |
  |git push [nombre-remoto] [nombre-rama]      |  Sirve para enviar tu rama a un servidor |
  |git push origin master           |     Manda tu rama master al servidor origin, solo sirver si tiene permisos de escritura y si nadie clono el mismo repositorio y envio informacion, en ese caso sera necesario traer su rama, combinarla y luego hacer el envio
|git push origin [nombre-X]:[nombre-Y]  | Manda tu rama local x a la rama y del servidor |
    |git remote show origin                      |  Te permite ver mas informacion de un remoto en particular |
    |git remote rename old_name new_name         |  Renombra un reporitorio remoto| 
    |git remote rm                               |  Elimina un repositorio remoto|

#UTILZANDO LAS RAMAS

   | | |
   |-|-|
   |git branch                    |   Muestra todas las ramas existentes en el proyecto *Es HEAD |
   |git branch -v                 |   Muestra la ultima confirmacion de cambios en cada rama |
   |git branch --merged           |   Muestra las ramas que han sido fusionadas |
   |git branch --no-merged        |   Muestra las ramas que no han sido fusionadas |
   |git branch testing            |   Crea una rama nueva denominada testing |
   |git checkout testing          |   Salta a la rama denominada testing  |
   |git checkout -b testing       |   Crea y salta a la rama denominada testing  |
   |git checkout master           |   Incorpora hotfix a la rama donde actualmente esta el apuntador HEAD  |
   |git log --decorate            |   Nos muestra los apuntadores existentes |
   |git branch -d hotfix          |   Elimina la rama hotfix si esta ya ha sido unida a otra |
   |git branch -D hotfix          |   Elimina la rama hotfix aun si esta no ha sido unida a otra |
   |git mergetool                 |   Abre la  herramienta de visualizacion que se usara para resolver conflictos |
   | git diff master...[branch-name] | Muestra el codigo introducido en tu rama puntual desde su ancestro comun con la rama master |
   | git cherry-pick [SHA-1]       |   Toma un commit de otra rama y trata de integrarlo al codigo actual |

#UTILIZAR RAMAS REMOTAS
| | |
|-|-|
|git checkout -b [branch-name] [server-name/branch-name]  | Este comando trae una rama remota y crea una version  propia de ella si tu te traes un repositorio remoto  con git pull o git fetch, solo traeras   los apuntadores pero no ramas editabales |
|git checkout --track [server-name/branch-name]     |       Trae una rama remota y le hace un seguimiento a esta con git clone o git pull, se le hace un seguimiento a origin/master |
|git branch -u [server-name]              |                 Sirven si ya tienes una rama local y quieres asignarla |
|git branch -set-upstream [server-name]   |                 a una rama remota que acabas de traer con git pull o quieres cambiar la rama a la que le haces seguimiento |
|git merge @{u}  /  git merge @{upstream} |                 @{upstream} o @{u} hace referencia a la rama de  seguimiento, sea origin/master o cualquier otra |
|git branch -vv                          |                  Te muestra las ramas que tienes y las ramas de  seguimiento asignadas asi como si estar por delante o por detras, respecto a la ultima vez que trajiste datos|
|git fetch --all         | Es necesario ejecutarlo si deseas tener los cambios por delante y por detras 
 |ahead                  |  Son cuantas confirmaciones tenemos que no han sido mandadas al servidor
 |behind                |   Son cuantas confirmaciones no has traido del servidor
    
   | | |
   |-|-|
   |git push [server-name] --delete [branch-name]           |  Sirve para eliminar una rama remota|


#REORGANIZAR EL TRABAJO (rebase)

### Nunca reorganices confirmaciones de cambio que ya hayas enviado a un repositorio publico
####     Se recomienda reorganizar el trabajo en local siempre que no lo hayas compartido

   | | |
   |-|-|
   | git rebase master              |     Este comando reorganiza las confirmaciones de la rama [x] |
   | (git checkout [branch-name])   | a la rama master, se usa cuando se sabe que no habra conflictos es necesario estar en la rama x.  Despues solo debes hacer un merge y avanzaras rapidamente |
   |git rebase --onto master [branch-name-1][branch-name-2]  | Este commando lo que dice es activa la rama 2, averigua  los cambios desde el ancestro comun entre las ramas uno y dos, desoues aplicalos a la rama master |
   |git rebase master server                         |        Reorganiza lo echo en server al final de master|

#POSIBLE FLUJOS DE TRABAJO CON GIT

| | |
|-|-|
    |Centralizado | Todos tienen permisos de escritura a un servidor central, si uno manda antes que tu tendran que unir primero  sus ramas |
   | Administrador - Integracion |    -   Los desarrolladores tienen una copia del proyecto sobre la cual trabajan y que despues un administrador -   fusiona con su rama master que a su vez fusiona con el proyecto|
   | Dictador-Tenientes |    -   Los desarrolladores tienen sus copias de proyecto que le envian a los tenientes, estos unen las colaboraciones    -   con su rama master que a su vez le envian al dictador benevolo que las unifica y las une al proyecto completo|

     
###    Se recomienda usar git diff check para evitar los espacios en blanco

    Deberia haber una confirmacion por cada cuestion, si se sobreescribe el mismo archivo se recomienda usar
    git add --path  <<_interactive-stagin>> <<_rewriting_history>> 

    Se recomienda que cada confirmacion tenga un mensaje de 50 caracteres o menos, en vez de usar 'Agregue pruebas'
    o 'Añadir pruebas' use 'Agregar pruebas para'



##   EJEMPLO DE FLUJO DE TRABAJO:

    -   John y Jessica estan trabajando en un mismo proyecto, ambos clonan el repositorio del servidor e inician
    -   a trabajar en el de manera local, Jessica avanza muy rapidamente en su asunto, hace un par de commits
    -   y manda sus cambios al servidor.
    -   John continua en local trabajando en local haciendo sus propios commits despues se trae los cambios
    -   que Jessica habia realizado y los mezcla con los propios, finalmente los manda todos al servidor.
    -   Por lo mientras Jessica decidio hacer una nueva confirmacion asi que trae el trabajo de John del
    -   del servidor, lo mezcla con lo propio y luego lo manda de nuevo 
    -  
    -         Jessica          Server           John
    -                  ----------|------------>Git Clone
    -       Git clone <----------|------------
    -       Git commit           |
    -       Git commit           |             Git commit
    -       Git push  ---------->|
    -                            |             Git commit
    -                            |------------>Git fetch
    -       Git commit           |             Git merge
    -                            |<------------Git push
    -       Git fetch <----------|
    -       Git merge            |
    -       Git push  ---------->|
    
    
#  RESOLVER CONFLICTOS

##### Significa reutilizar resolucion grabada

   | | |
   |-|-|
   |git config --global rerere.enabled true     |   Git mantendra un conjunto de imagenes de integraciones anteriores y posteriores, asi si detecta un conflicto similar en el futuro podra resolverlo facilmente |
    

# HERRAMIENTAS DE GIT
#####  Mandar instantaneas sin git
    
      Sirve para mandar una instantanea de master a una persona que no usagit, si deseas un .tar es necesaria la 2°
    
       -   git archive master --prefix='project/' --format=zip >  'git describe master'.zip  
       -   git aechive master --prefix='project/' | gzip > 'git describe master'.tar.gz
    
#####     Obtener registros de cambios
    
       git shortlong --no-merges master --not v1.0.1       Te muestra todos los cambios realizados desde la ultima
       -                                                   confirmacion

##### Consultar un commit de una rama
       
       git show [branch-name] / git show[SHA-1]            Te muestra el ultimo commit de una ram

####     Consultar SHA-1 de una rama

       git rev-parse [branch-name]

####     Conocer los ultimos apuntadores de HEAD

| | |
 |-|-|     
  | git reflog / git log -g      |       Muestra los ultimos apuntadores de HEAD |
  | git show HEAD^               |       Muestra al ancestro del HEAD |
  | git show HEAD^2              |       Muestra al abuelo del HEAD |

####    Rangos de commits
   | | |
   |-|-|
   |  git log master..experiment     |     Trae todos los commits alcanzables por experiment que no son alcanzables por master        |
   |   git log experiment..master    |      Trae todos los commits alcanzables por master que no son alcanzables por experiment |
   |   git log origin/master..HEAD    |     Trae todos los commits alcanzables en HEAD que no son alcanzables por origin/master      |   
   |   git log log refA --not refB     |    No deseo ver los commits alcanzables de refB|
   |   git log refA refB ^refC        |     Deseo ver todos los commmits alcanzables desde refA  o refB pero no refC|
   |   git log master...experiment            |       Muestra los commmits que estan en master o en experiment |
    |   git log --left-right master...experiment   |   Muestra los commmits que estan en master o en experiment  y de que lado del rango se encuentra cada uno|

#ORGANIZACION INTERACTIVA
  | | |
  |-|-|
   | git add -i    /    git add --Interactive   |   Sirve si modificas varios archivos y decides que cada cambio este en una confirmacion diferente |
   | What now> 2 / u        |                       Solicitara que archivos deseas organizar|
   | Update>> 1, 2          |                       Selecciona el archivo 1 y 2 |
   | What now> 3 / r        |                       Revierte la accion realizada|
   | What now> 6 / d        |                       Muestra una lista de los archivos organizados y puedes selccionar  aquellos de los que quiseieras ver la diferencia|
   |What now> 5 / p          |                     Te muestra todos los cambios realizados para que puedas organizar los cambios que deseas en el commit y los que no deseas tener aun|

   | | |
    |-|-|        
    |y | Prepara este pedazo|
    |n | Ignora este pedazo|
    |a | Prepara este y todos los cambios restantes del archivo|
    |d | No prepares este archivo ni ninguno de los restantes|
    |g | Selecciona un pedazo para ir |
    |/ | Busca determinado cambio con esta expresion regular|
    |j |Deja este cambio como "sin decidir", muestrane el siguiente cambio "sin decidir"|
    |J | Deja este cambio como "sin decidir", muestrane el siguiente cambio|
    |k | Deja este cambio como "sin decidir", muestrane el anterior cambio "sin decidir"|
    |K | Deja este cambio como "sin decidir", muestrane el anterior cambio|
    |s | Divide el cambio actual en cambios mas pequeños|
    |e | Dejame editar manualmente el cambio actual|
    |? | Imprime la ayuda|

#GUARDADO RAPIDO
  | | |
    |-|-|
    |git stash                   |  Crea un guardado de archivos
    |git stash save              |  Crea un guardado de archivos
    |git stash list              |  Revisa que cambios rapidos tienes guardados
    |git stash apply             |  Entra a el ultimo estado en guardado rapido
    |git stash apply stash@{2}   |  Entra a el antepenultimo estado de guardado rapido
    |git stash apply --index     |  Intenta reaplicar los cambios almacenados despues de usar un archivo
    |gut stash drop              |  Sirve para eliminar un guardado
    |git stash save --keep-index |          Solo guarda los cambios que agregaste con git add
    |git stash save --include-untracked |   |
    |git stash save -u                  |   Estas dos ultimas opciones guarda tambien los archivos que no  estan siendo vigilados por git |
    |git stash save --patch            |    Te muestra los cambios realizados igual que el organizado de parches para que decidas que cambios mantener y que cambios no mantener |


   | | |
    |-|-|
    |y -| Prepara este pedazo |
    |n -| Ignora este pedazo|
    |a -| Prepara este y todos los cambios restantes del archivo|
    |d -| No prepares este archivo ni ninguno de los restantes|
    |g -| Selecciona un pedazo para ir |
    |/ -| Busca determinado cambio con esta expresion regular|
    |s -| Divide el cambio actual en cambios mas pequeños|
    |e -| Dejame editar manualmente el cambio actual|
    |? -| Imprime la ayuda|

   | | |
    |-|-|
    |git stash branch           |           Crea una nueva rama a partir de lo que ha sido guardado |
	|git clean -f -d -n          |          Remueve cualquier archivo y subdirectorio y muestrame que habras eliminando|
	|git clean -f -d -x          |          Remueve cualquier archivo y subdirectorio existente incluso si no es   rastreado por git|
	|git clean -x -i             |          Limpiemos el directorio de manera interactiva incluyendo los archivos no rastreados|

#FIRMANDO EL TRABAJO
   | | |
    |-|-|
    |gpg --list-keys                    |   Te muestra las llaves que tienes instaladas|
    |gpg --gen-key                      |   Sirve para generar una llave |
    |git config --global user.signingkey | [key--list-keys]     |
    |git tag -s [version] -m [signed]   |   Se utiliza para firmar un tag   |
    |git tag |  
