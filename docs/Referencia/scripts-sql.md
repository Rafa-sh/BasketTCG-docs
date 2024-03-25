---
title: Scripts SQL
icon: material/database-import
---
*Todos los scripts del proyecto estan preparados para PostgreSQL*

## crear-tablas.sql
El script comprueba el estado de la base de datos, y toma una acción dependiendo de lo que observa.  
  
- Si las tablas `usuarios, carta, coleccion, mercado` existen, no hace nada  
- Si algunas de las tablas `usuarios, carta, coleccion, mercado` existen, pero no todas, da un mensaje informando de que la BD esta corrupta o que el script es incompatible con la versión de la BD  
- Si no, crea las tablas `usuarios, carta, coleccion, mercado`, y genera 2-3 filas de ejemplo por tabla  

## hola