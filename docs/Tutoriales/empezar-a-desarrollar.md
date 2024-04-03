---
title: Empezar a desarrollar
---

Para empezar a desarrollar el proyecto, no es suficiente con un `git clone`. Aquí se explica como poner el proyecto en marcha para trabajar con este.

Este documento asume que tienes una instalación limpia de Windows 11

## Descargar programas

### IDE (VSCode)
Mientras que cualquier IDE es válido, los desarrolladores usamos VSCode, [Link](https://code.visualstudio.com/Download)

### Docker Desktop
Es necesario tener Docker, para windows se usa Docker Desktop, [Link](https://www.docker.com/products/docker-desktop/)

### Suite de herramientas git (GitKraken)
No es estrictamente necesario, pero facilia el uso de Gitflow, que usamos para el desarrollo del proyecto, [Link](https://www.gitkraken.com/)

### Herramienta de Bases de datos (DBeaver)
Una herramienta para manejar la base de datos es necesaria, usamos Dbeaver, [Link](https://dbeaver.io/)

### Cliente HTTP / API (Postman)
Un cliente para testear la API, usamos Postman [Link](https://www.postman.com/downloads/)

### Node.js
Software que usamos para el frontend, [Link](https://nodejs.org/en)

### PHP
PHP es el lenguaje usado para el backend, [Link](https://windows.php.net/download/)

### Composer
Composer se encarga de las dependencias de nuestro backend, [Link](https://getcomposer.org/download/)

### Python
Python NO es usado para el proyecto, pero si es usado para la documentación, [Link](https://www.python.org/downloads/)  
Este codígo instala las dependencias necesarias, **ejecutalo como administrador**
```python
pip install mkdocs-material pillow cairosvg mkdocs-include-dir-to-nav
```
## Preparar proyecto para trabajar

### Clonar repositorio
Puedes usar Gitkraken, o `git clone https://github.com/FcoJavier9/BasketTCG`

### Contruir contenedores
Este paso es bastante largo, ejecuta `docker-compose build` en el repositorio local.  
*Necesitas tener Docker Desktop abierto para usar los contenedores.*

### Crear .env del backend
Copia el archivo `/backend/.env.example`, y ponlo en `/backend/.env`

### Levantar contenedores
Usa `docker-compose up` para levantar los contendores
*Los contenedores aun no funcionan, necesitamos preparar la base de datos aún*

### Crear bases de datos
en `/scripts/script.sql` se encuentra un script SQL, una vez se encuentre en pie el contenedor de la base de datos, puedes conectarte usando la información de `/.env`.  
  
Una vez conectado a la base de datos, ejecuta el script SQL dado, y se creará la base de datos.

### Reiniciar contenedores
Puedes usar `Ctrl-C` para detener los contenedores, al volver a poner los contenedores en pie con `docker-compose up`. Estará el proyecto listo para trabajar.

## Poner debuggers

### Backend (Laravel)
El Dockerfile del backend viene preparado con XDebug. Debes decirle a tu IDE que use el puerto 9003, y configurar las rutas relativas que hay dentro del contenedor.  
En `/scripts/launch-backend.json.example` Se envuentra un json de ejemplo para ejecutar XDebug con vscode.  
  
Sigue estos pasos para usar el debugger en VSCode:  
1. Instala `xdebug.php-debug` en VSCode  
2. Pon una copia de `/scripts/launch-backend.json.example` en `/.vscode/launch.json`. O adapta el código de tu `/.vscode/launch.json` como veas conveniente.  
3. Una vez se encuentre el contenedor `baskettcg-backend-1` en pie, en VSCode usa "Run and debug", esuchando a XDebug  
4. Pon breakpoints donde veas conveniente, cuando se ejecute el código, funcionará el debugger como esperas.  