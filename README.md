<img src="/docs/assets/logo.png" width="200" />

# BasketTCG-docs
> Documentación del proyecto [BasketTCG](https://github.com/Fcojavier9/BasketTCG), un TFG

Este repositorio contiene la documentación del TFG (Trabajo de Fin de Grado) de
- Francisco Javier Montiel Noguera
- Pablo Navarro Valverde
- Rafael Dominguez Alcolea

Curso 2023-2024, DAW (Desarrollo de Aplicaciones Web) 

## Instalación

Si buscas usar en local **esta documentación**

```shell
# Descarga el repositorio
git pull https://github.com/Rafa-sh/BasketTCG-docs && cd BasketTCG-docs
# Instala mkdocs-material
pip install mkdocs-material
# Instala paquetes adicionales para mkdocs
pip install pillow cairosvg mkdocs-include-dir-to-nav
# Iniciar página en local
mkdocs serve
```
Ahora la página con la documentación estará en 127.0.0.1:8000!

Cambios en los documentos se reflejarán en la página automáticamente

## Desarrollo

Para continuar con el desarrollo de la documentación, es tan simple como modificar los archivos markdown en el repositorio.

Si quieres conocer la sintaxis concreta del proyecto, [sigue este link](https://rafa-sh.github.io/BasketTCG-docs/Referencia/markdown)

```shell
git clone https://github.com/your/awesome-project.git
cd awesome-project/
packagemanager install
```

Para añadir paquetes adicionales para mkdocs, debes añadir un comando para instalarlo en `.githubs/workflows/ci.yml`

```shell
    # Por ejemplo, este es el comando que añade el propio mkdocs-material
      - run: pip install mkdocs-material
```

## Características

- Página estática profesional, con configuración simple, y escrita puramente en markdown
- Diseño responsivo y accesible
- Personalizado al estilo del proyecto
- Ligero y rápido
- Open Source
- Los autores pueden editar la documentación desde el navegador o desde su IDE
- Modo oscuro
- Un sistema de busqueda avanzado, rápido, y funciona offline
- soporte para anotar código de forma elegante


## Configuración

Toda la configuración puede ser encontrada en `/mkdocs.yml`

Puedes encontrar sobre la configuración de mkdocs base [aquí](https://www.mkdocs.org/user-guide/configuration/), y de mkdocs-material [aquí](https://squidfunk.github.io/mkdocs-material/).

## Links

- Repositorio de BasketTCG: https://github.com/Fcojavier9/BasketTCG

- Página de la documentación: https://rafa-sh.github.io/BasketTCG-docs/Referencia/api/

- Repositorio de esta documentación: https://github.com/Rafa-sh/BasketTCG-docs

## Licencia

WIP
