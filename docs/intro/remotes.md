# Repositorios remotos

Clone (descargue) un repositorio que ya existe en GitHub, incluidos todos los archivos, ramas y confirmaciones

    $ git clone [url]


## Agregando remotos

- Agregue un nuevo remoto
  
        $ git remote add origin [url]

- Restablezca la url a un remoto existente

        $ git remote set-url origin [url]


## Sincronizar cambios

- Sincronice su repositorio local con el repositorio remoto en GitHub.com

        $ git push

- Carga todas las confirmaciones de sucursales locales en GitHub

        $ git merge

- Combina la rama de seguimiento remoto en la rama local actual

        $ git fetch

- Descarga todo el historial de las ramas de seguimiento remoto

        $ git pull

Actualiza su rama de trabajo local actual con todas las nuevas confirmaciones de la rama remota correspondiente en GitHub. git pull es una combinación de git fetch y git merge


## Versiones y tags

    $ git tag 1.0.0 [commit-id]
    $ git tag -a v2.2.0 -m "Primera version estable (Jun 17, 2020)"
    $ git tag -d v1.0.0

## Claves SSH

https://github.com/settings/keys

Configura tus claves SSH para Github [aqui](https://help.github.com/es/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)

    $ ssh-keygen -t rsa -b 4096 -C "rnovelo.cruz98@gmail.com"
    $ cat ~/.ssh/id_rsa.pub

