# Gitflow

![](https://wac-cdn.atlassian.com/dam/jcr:61ccc620-5249-4338-be66-94d563f2843c/05%20(2).svg?cdnVersion=1109)

## Semantic Versioning [(SemVer)](https://semver.org/)

### ELI5: ¿Cómo funcionan las versiones?

> _Al igual que con una nueva actualización de un videojuego o algo así. siempre veo, por ejemplo, v1.2.3. ¿Cómo funciona esto? ¿Qué significan los puntos y los decimales?_

## Github flow

[Guia interactiva](https://guides.github.com/introduction/flow/)

## Caso de Uso

> La división de Software del Capitulo AAAIMX esta desarrollando una API REST para su nueva aplicación móvil, por lo que asignó los siguientes roles en su equipo de **Backend** para desarrollar el proyecto:

- Lider del proyecto (Project Manager )
- Desarrollador 1 (Dev1)
- Desarrollador 2 (Dev2)

## Flujo de trabajo

1. 🚩Crear proyecto
2. ⬆️ Iniciar repositorio y subir a **Github**
3. 🔒 Crear y proteger rutas (`master`, `develop` y/o `staging`)
4. ⬇️ Devs clonan y crean ramas
5. 📅 Crear _Board_ automatizado
6. 📅 Crear **Issues**
7. 👨‍💻 **Dev1** toma la primera **issue** (Mover tarjeta y/o comentar)
8. ⛕ Crea una **rama** y realiza los cambios (`feature`, `hotfix` y/o `bugfix`)
9.  🔰 Envia **pull request**
10. 💬 **Project manager** hace _Code Review_
11. ✔️ Correcciones y merge a `develop`
12. 🗑️ Cerrar **issue**
13. ⬇️ **Dev2** baja cambios desde la rama `develop`
14. 👨‍💻 **Dev2** toma otra **issue** (Mover tarjeta y/o comentar)
15. 🔁 _Repetir pasos [8]() al [13]() por cada **issue** existente_
16. 📦 Crear _tags_ y publicar version

## Material adicional

- [Scrum](<https://es.wikipedia.org/wiki/Scrum_(desarrollo_de_software)>)
- [ELI5 Scrum, Kanban, Cascada](https://www.reddit.com/r/agile/comments/2d3sa4/can_someone_eli5_scrum_agile_kanban_and_waterfall/)
