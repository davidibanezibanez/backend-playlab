# backend-playlab

## Cómo ejecutar

1) La versión del backend es java 17.
2) Revisar en pom.xml que todo este instalado sin ninguna acción requerida.
3) Crear en local base de datos "db-playlab" (si no existe).
4) Crear archivo .env (si no existe).
5) Generar clave que se usará para firmar jwt (Algoritmo HS256, base 64, 32 bytes).
6) Agregar al archivo .env la clave de la siguiente manera: JWT_PRIVATE_KEY=clave.
7) Correr la aplicación.
