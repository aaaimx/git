# Respositorios locales

## Configuración inicial

Configure la información del usuario para todos los repositorios locales

- Establece el correo electrónico que desea adjuntar a sus transacciones de confirmación

      $ git config --global user.email "[email address]"

- Establece el nombre que desea adjuntar a sus transacciones de confirmación
      
      $ git config --global user.name "[name]"

## Crear repositorios

Al comenzar con un nuevo repositorio localmente, solo necesita hacerlo una vez.

- Convierte un directorio existente en un repositorio git

      $ git init


## Hacer cambios

Examinar e inspeccionar la evolución de los archivos del proyecto.

- Muestra metadatos y cambios de contenido de la confirmación especificada

      $ git status

- Instantáneas del archivo en preparación para el versionado

      $ git add [archivo]

- Registra confirmaciones de archivos permanentemente en el historial de versiones
  
      $ git commit -m "[mensaje descriptivo]"

- Muestra el historial de versiones de la rama actual
  
      $ git log

## El archivo .gitgnore

A veces puede ser una buena idea excluir archivos de ser rastreados con Git. Esto normalmente se hace en un archivo especial llamado `.gitignore`. Puede encontrar plantillas útiles para archivos `.gitignore` en [gitignore templates](https://github.com/github/gitignore).


## Ramas

Las ramas son una parte importante de trabajar con Git. Cualquier confirmación que realice se realizará en la sucursal a la que está actualmente "desprotegido". Use `git status` para ver qué rama es esa. 

- Crea una nueva rama, sin moverse de la rama actual
  
      $ git branch [nombre-rama] 

- Cambia a la rama especificada y actualiza el directorio de trabajo
  
      $ git checkout [nombre-rama] 

- Crea una nueva rama, y cambia a la rama especificada. [Los 2 comandos anteriores en 1 solo]

      $ git checkout -b [nombre-rama]

