# Mi primer repositorio en GitHub

Hola! Este es mi primer repositorio. Aqui aprendo a usar GitHub con Claude Code.

---

## Que es GitHub?

GitHub es una plataforma donde puedes guardar tu codigo en la nube y:
- Tener un historial de todos tus cambios
- Colaborar con otras personas
- Recuperar versiones anteriores de tu codigo

---

## Conceptos basicos de Git y GitHub

| Concepto     | Que significa                                              |
|--------------|------------------------------------------------------------|
| `repository` | Tu proyecto (carpeta con archivos + historial de cambios)  |
| `commit`     | Una foto de tu codigo en un momento dado                   |
| `push`       | Subir tus cambios locales a GitHub                         |
| `pull`       | Bajar los cambios de GitHub a tu computadora               |
| `branch`     | Una copia del proyecto para trabajar sin afectar el resto  |
| `merge`      | Unir los cambios de una branch al proyecto principal       |
| `clone`      | Descargar un repositorio de GitHub a tu computadora        |

---

## Comandos mas usados

```bash
# Ver el estado de tus archivos
git status

# Agregar un archivo para el proximo commit
git add nombre-del-archivo.txt
git add .   # agrega todos los archivos

# Guardar los cambios con un mensaje
git commit -m "mi mensaje describiendo que hice"

# Subir los cambios a GitHub
git push

# Bajar los cambios de GitHub
git pull

# Ver el historial de commits
git log --oneline
```

---

## El flujo tipico de trabajo

1. Editas un archivo en tu computadora
2. Haces `git add` para preparar los cambios
3. Haces `git commit` para guardarlos con un mensaje
4. Haces `git push` para subirlos a GitHub

---

*Creado con Claude Code - Anthropic*
