# generator-core

# Instrucciones para Actualizar Submódulos de Git

Este documento explica cómo actualizar los submódulos de un proyecto al último commit disponible en su repositorio original, inicializar cualquier submódulo no inicializado y verificar su estado.

## Actualizar los Submódulos al Último Commit del Repositorio Original

Para actualizar cada submódulo a su última versión desde el repositorio original (remoto), utiliza el siguiente comando:
```bash
git submodule update --remote --merge
```

- Este comando actualiza cada submódulo al último commit del branch por defecto del repositorio original.
- La opción `--merge` intenta hacer un merge si tienes cambios locales en el submódulo que pudieran entrar en conflicto con el commit remoto.

## Verificar el Estado de los Submódulos

Puedes verificar el estado de los submódulos y confirmar que cada uno apunta al último commit de su repositorio original ejecutando:
```bash
git submodule status
```

- Esto te mostrará la referencia del commit actual de cada submódulo.

## Hacer un Commit en el Repositorio Principal

Una vez que has actualizado los submódulos, si el estado de los submódulos ha cambiado (es decir, si se han actualizado a nuevos commits en sus repositorios), necesitas hacer un commit en el repositorio principal para reflejar estos cambios:
```bash
git add .
git commit -m "Actualización de submódulos a sus últimos commits originales"
```

- Esto añadirá los cambios de los submódulos y los preparará para ser registrados en el historial de tu proyecto.

## Subir los Cambios al Repositorio Remoto

Finalmente, una vez que has hecho el commit, puedes subir tus cambios al repositorio remoto ejecutando:

```bash
git push origin <branch>
```

- Reemplaza `<branch>` con el nombre de la rama en la que estás trabajando (por ejemplo, `main` o `master`).

---

De esta forma, cada submódulo será actualizado con los últimos cambios de su proyecto original y el estado de tu proyecto principal reflejará estos cambios. Asegúrate de verificar el estado después de cada actualización para evitar conflictos.

