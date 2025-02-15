## Dev

1. Clonar el repositorio
2. Crear un .env basado en el .env.template
3. Ejecutar el comando `git submodule update --init --recursive` para reconstruir los sub-módulos
4. Ejecutar el comando `docker compose up --build`
5. Ir al Users MS, crear un .env basado en el .env.template
6. Ejecutar el comando, dentro de la carpeta users-ms `npx prisma generate`
7. Ejecutar el comando, dentro de la carpeta users-ms `npx prisma migrate deploy`
8. Ejecutar el comando, dentro de la carpeta users-ms `npx prisma db seed`
9. Ejecutar el comando, dentro de la carpeta auth-ms `npx prisma generate`
10. Ejecutar el comando, dentro de la carpeta auth-ms `npx prisma migrate deploy`
11. Ejecutar el comando, dentro de la carpeta ai-messaging-mw `npx prisma generate`
12. Ejecutar el comando, dentro de la carpeta ai-messaging-mw `npx prisma migrate deploy`

### Pasos para crear los Git Submodules

1. Crear un nuevo repositorio en GitHub
2. Clonar el repositorio en la máquina local
3. Añadir el submodule, donde `repository_url` es la url del repositorio y `directory_name` es el nombre de la carpeta donde quieres que se guarde el sub-módulo (no debe de existir en el proyecto)

```
git submodule add <repository_url> <directory_name>
```

4. Añadir los cambios al repositorio (git add, git commit, git push)
   Ej:

```
git add .
git commit -m "Add submodule"
git push
```

5. Inicializar y actualizar Sub-módulos, cuando alguien clona el repositorio por primera vez, debe de ejecutar el siguiente comando para inicializar y actualizar los sub-módulos

```
git submodule update --init --recursive
```

6. Para actualizar las referencias de los sub-módulos

```
git submodule update --remote
```

## Importante

Si se trabaja en el repositorio que tiene los sub-módulos, **primero actualizar y hacer push** en el sub-módulo y **después** en el repositorio principal.

Si se hace al revés, se perderán las referencias de los sub-módulos en el repositorio principal y tendremos que resolver conflictos.

# Prod

1. Clonar el repositorio
2. Crear un .env basado en el .env.template
3. Ejecutar el comando

````
docker compose -f docker-compose.prod.yml build
```# chat-ai-launcher
````
