# Guía Completa de Git

## Tutorial Técnico para Desarrolladores

**Autor:** Ramfis Velazquez
**Fecha:** Junio 2026

---

# Índice

1. Introducción a Git
2. Instalación de Git
3. Configuración inicial
4. Comandos básicos
5. Trabajo con ramas (Branches)
6. Repositorios remotos
7. Tabla de referencia rápida
8. Conclusiones

---

# 1. Introducción a Git

Git es un sistema de control de versiones distribuido, creado por Linus Torvalds en 2005. Permite registrar los cambios realizados en archivos a lo largo del tiempo, facilitando la colaboración entre múltiples desarrolladores.

## ¿Por qué usar Git?

* Guarda el historial completo de cambios en tu proyecto.
* Permite trabajar en equipo sin conflictos.
* Puedes revertir errores fácilmente.
* Es el estándar de la industria del software.
* Compatible con plataformas como GitHub, GitLab y Bitbucket.

## Conceptos clave

* **Repositorio (repo):** Carpeta donde Git guarda el historial del proyecto.
* **Commit:** Fotografía del estado del proyecto en un momento dado.
* **Branch (rama):** Línea de desarrollo independiente.
* **Merge:** Unión de dos ramas en una sola.

---

# 2. Instalación de Git

## En Windows

1. Descarga el instalador desde `git-scm.com`.
2. Ejecuta el archivo `.exe` descargado.
3. Sigue el asistente de instalación (opciones predeterminadas recomendadas).
4. Verifica la instalación abriendo Git Bash.

## En macOS

```bash
# Usando Homebrew (recomendado)
brew install git

# O instalar las Xcode Command Line Tools
xcode-select --install
```

## En Linux (Ubuntu/Debian)

```bash
# Actualizar repositorios
sudo apt update

# Instalar Git
sudo apt install git -y

# Verificar instalación
git --version
```

> Nota: Deberías ver algo como `git version 2.x.x` al ejecutar `git --version`.

---

# 3. Configuración inicial

Antes de usar Git por primera vez, configura tu identidad. Esta información aparecerá en cada commit que realices.

```bash
# Configurar nombre de usuario
git config --global user.name "Tu Nombre"

# Configurar correo electrónico
git config --global user.email "tu@correo.com"

# Configurar editor de texto predeterminado (Visual Studio Code)
git config --global core.editor "code --wait"

# Ver toda la configuración actual
git config --list
```

---

# 4. Comandos básicos

## Iniciar un repositorio

```bash
# Crear un nuevo repositorio en la carpeta actual
git init

# Clonar un repositorio existente desde internet
git clone https://github.com/ramfisvelazquez/markown-victor
```

## Ciclo de vida de un archivo

Los archivos en Git pasan por diferentes estados:

1. **Untracked** → archivo nuevo, Git no lo conoce.
2. **Staged** → listo para ser confirmado (commit).
3. **Committed** → guardado en el historial.

```bash
# Ver el estado actual del repositorio
git status

# Agregar un archivo al área de staging
git add nombre-del-archivo.txt

# Agregar TODOS los archivos modificados
git add .

# Crear un commit con un mensaje descriptivo
git commit -m "Agrega funcionalidad de login"

# Ver el historial de commits
git log

# Ver historial resumido (una línea por commit)
git log --oneline
```

## Deshacer cambios

```bash
# Descartar cambios en un archivo (antes del staging)
git restore nombre-del-archivo.txt

# Quitar un archivo del staging sin borrar cambios
git restore --staged nombre-del-archivo.txt

# Ver diferencias entre el archivo actual y el último commit
git diff nombre-del-archivo.txt
```

---

# 5. Trabajo con ramas (Branches)

Las ramas permiten desarrollar funcionalidades de forma aislada sin afectar el código principal.

```bash
# Ver todas las ramas del proyecto
git branch

# Crear una nueva rama
git branch nueva-funcionalidad

# Cambiar a otra rama
git checkout nueva-funcionalidad

# Crear una rama y cambiar a ella en un solo paso
git checkout -b nueva-funcionalidad

# Fusionar una rama con la rama actual
git merge nueva-funcionalidad

# Eliminar una rama
git branch -d nueva-funcionalidad
```

## Flujo de trabajo típico con ramas

```bash
# 1. Asegúrate de estar en main
git checkout main

# 2. Crea tu rama para la nueva tarea
git checkout -b feature/formulario-contacto

# 3. Trabaja y haz commits
git add .
git commit -m "Agrega formulario de contacto"

# 4. Vuelve a main y fusiona
git checkout main
git merge feature/formulario-contacto

# 5. Borra la rama ya innecesaria
git branch -d feature/formulario-contacto
```

---

# 6. Repositorios remotos

Un repositorio remoto (como GitHub) permite compartir el código con otras personas o tener una copia de seguridad en la nube.

```bash
# Ver repositorios remotos configurados
git remote -v

# Conectar tu repositorio local con uno remoto
git remote add origin https://github.com/usuario/mi-proyecto.git

# Subir cambios al repositorio remoto
git push origin main

# Descargar y aplicar cambios del repositorio remoto
git pull origin main

# Solo descargar cambios sin aplicarlos
git fetch origin
```

---

# 7. Tabla de referencia rápida

| Comando             | Descripción                         | Uso frecuente |
| ------------------- | ----------------------------------- | ------------- |
| `git init`          | Inicializa un repositorio nuevo     | ⭐⭐⭐           |
| `git clone <url>`   | Clona un repositorio remoto         | ⭐⭐⭐           |
| `git status`        | Muestra el estado del repositorio   | ⭐⭐⭐           |
| `git add .`         | Agrega todos los cambios al staging | ⭐⭐⭐           |
| `git commit -m ""`  | Guarda los cambios con un mensaje   | ⭐⭐⭐           |
| `git log --oneline` | Historial resumido de commits       | ⭐⭐⭐           |
| `git branch`        | Lista todas las ramas               | ⭐⭐⭐           |
| `git checkout -b`   | Crea y cambia a una nueva rama      | ⭐⭐⭐           |
| `git merge <rama>`  | Fusiona una rama con la actual      | ⭐⭐⭐           |
| `git push`          | Sube cambios al repositorio remoto  | ⭐⭐⭐           |
| `git pull`          | Descarga y aplica cambios remotos   | ⭐⭐⭐           |
| `git diff`          | Muestra diferencias en los archivos | ⭐⭐            |
| `git restore`       | Descarta cambios en un archivo      | ⭐⭐            |
| `git stash`         | Guarda cambios temporalmente        | ⭐⭐            |

---

# 8. Conclusiones

A lo largo de esta guía hemos recorrido los fundamentos esenciales de Git, desde su instalación hasta el trabajo con ramas y repositorios remotos.

## Lo más importante a recordar

* Git es una habilidad esencial para cualquier desarrollador de software moderno.
* El flujo básico de trabajo es siempre: **add → commit → push**.
* Las ramas son tu herramienta más poderosa: úsalas para cada nueva funcionalidad o corrección.
* Los commits frecuentes con mensajes descriptivos hacen el historial más útil.
* Practica todos los días, incluso en proyectos personales pequeños.

## Próximos pasos sugeridos

1. Crea una cuenta gratuita en GitHub.
2. Crea tu primer repositorio público.
3. Practica el ciclo **add → commit → push** diariamente.
4. Aprende sobre `git rebase` y resolución de conflictos.

> "El control de versiones no es opcional en el desarrollo de software profesional — es la base sobre la que se construye todo lo demás."

---

© 2026 — Documentación creada como práctica académica de Markdown
