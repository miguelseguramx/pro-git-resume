## CONFIGURACIÓN Y AYUDA

### Configuracion `git config`

|  Comando | Descripción 
| ------------ | ------------ |
|  `git config core.editor `                 |   Configura un editor para escribir los mensajes de los commmits  |  
|  `git config --global alisas.co checkout` |  Crea un alias para el commando checkout con el nombre de co  |
|   `git config --global alias.ci commit`  | Crea un alias para el commando commit con el nombre de ci  |
|  `git config --global alias.st status`   |   Crea un alias para el commando status con el nombre de st |

>     -             git co / git ci / git st 

### Ayuda `git help`

| Comando  | Descripción  |
| ------------ | ------------ |
|  `git config --global alias.unstage 'reset HEAD --'` |    Los alias pueden servir para mejorar el uso intuitivo de git  |

    
>     -             git unstage [file-name]

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

