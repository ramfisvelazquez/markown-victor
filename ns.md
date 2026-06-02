# Guía Completa de Markdown y Herramientas de Documentación

---

## PARTE 1 — Sintaxis Básica de Markdown

---

## 1. Títulos y Subtítulos

Los títulos se crean usando el símbolo `#`. La cantidad de `#` determina el nivel del título (del H1 al H6).

**Sintaxis:**

```
# Título Principal (H1)
## Subtítulo (H2)
### Subtítulo de nivel 3 (H3)
#### Subtítulo de nivel 4 (H4)
##### Subtítulo de nivel 5 (H5)
###### Subtítulo de nivel 6 (H6)
```

**Ejemplo práctico:**

# Mi Proyecto de Software
## Introducción
### Objetivos del proyecto
#### Objetivo específico 1
##### Meta 1.1
###### Detalle 1.1.a

> **Nota:** Los encabezados H1 y H2 también pueden crearse con líneas de `=` o `-` debajo del texto:
> ```
> Título H1
> =========
> Título H2
> ---------
> ```

---

## 2. Texto en Negrita y Cursiva

**Sintaxis:**

| Formato | Sintaxis | Resultado |
|---------|----------|-----------|
| Negrita | `**texto**` o `__texto__` | **texto** |
| Cursiva | `*texto*` o `_texto_` | *texto* |
| Negrita + Cursiva | `***texto***` | ***texto*** |
| Tachado | `~~texto~~` | ~~texto~~ |

**Ejemplos prácticos:**

markdown
Este es un **término importante** dentro del texto.
La función devuelve un valor *booleano* por defecto.
El archivo ***README.md*** es ***obligatorio*** en todo repositorio.
Esta función está ~~obsoleta~~ y no debe usarse.


Este es un **término importante** dentro del texto.
La función devuelve un valor *booleano* por defecto.
El archivo ***README.md*** es ***obligatorio*** en todo repositorio.
Esta función está ~~obsoleta~~ y no debe usarse.

---

## 3. Listas Ordenadas y Desordenadas

### Listas Desordenadas

Se usan `-`, `*` o `+` seguidos de un espacio.

**Sintaxis:**
```markdown
- Elemento uno
- Elemento dos
  - Sub-elemento 2.1
  - Sub-elemento 2.2
- Elemento tres
```

**Ejemplo práctico — Tecnologías frontend:**

- HTML5
- CSS3
  - Flexbox
  - Grid Layout
  - Animaciones
- JavaScript
  - React
  - Vue.js

---

### Listas Ordenadas

Se usan números seguidos de un punto.

**Sintaxis:**
```markdown
1. Primer paso
2. Segundo paso
   1. Paso secundario
   2. Paso secundario
3. Tercer paso
```

**Ejemplo práctico — Proceso de instalación:**

1. Instalar Node.js desde nodejs.org
2. Clonar el repositorio
   1. Abrir la terminal
   2. Ejecutar `git clone <url>`
3. Instalar dependencias con `npm install`
4. Iniciar el servidor con `npm start`

---

## 4. Enlaces

**Sintaxis:**

```markdown
[Texto del enlace](URL "Título opcional")

<!-- Enlace de referencia -->
[Texto][id]
[id]: https://www.ejemplo.com "Título"

<!-- Enlace rápido (URL directa) -->
<https://www.ejemplo.com>
```

**Ejemplos prácticos:**

```markdown
Visita la [documentación oficial de Markdown](https://www.markdownguide.org "Guía completa")

Repositorio en [GitHub](https://github.com)

Aprende más en <https://www.markdownguide.org>

<!-- Usando referencias -->
El proyecto usa [React][react] y [Node.js][node].

[react]: https://reactjs.org "Librería de UI"
[node]: https://nodejs.org "Entorno de ejecución"
```

**Resultado:**

Visita la [documentación oficial de Markdown](https://www.markdownguide.org "Guía completa")

El proyecto usa [React][react] y [Node.js][node].

[react]: https://reactjs.org "Librería de UI"
[node]: https://nodejs.org "Entorno de ejecución"

---

## 5. Imágenes

La sintaxis es similar a la de los enlaces, pero con un `!` al inicio.

**Sintaxis:**

```markdown
![Texto alternativo](ruta/imagen.png "Título opcional")

<!-- Con referencia -->
![Logo][logo]
[logo]: /assets/logo.png "Logo del proyecto"
```

**Ejemplos prácticos:**

```markdown
<!-- Imagen local -->
![Diagrama de arquitectura](./docs/arquitectura.png "Arquitectura del sistema")

<!-- Imagen desde URL -->
![Logo de Markdown](https://markdown-here.com/img/icon256.png "Markdown Logo")

<!-- Imagen con enlace clickeable -->
[![GitHub](https://img.shields.io/badge/GitHub-black?logo=github)](https://github.com)
```

**Resultado visual:**

![Logo de Markdown](https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Markdown-mark.svg/120px-Markdown-mark.svg.png "Markdown Logo")

> **Consejo:** Si la imagen no carga, el texto alternativo (`alt text`) se muestra en su lugar, lo que mejora la accesibilidad.

---

## 6. Bloques de Código

### Código en línea

Se usa una comilla invertida `` ` `` para código dentro de una oración.

```markdown
Usa el comando `npm install` para instalar dependencias.
La variable `const PI = 3.14159` es inmutable.
```

**Resultado:** Usa el comando `npm install` para instalar dependencias.

---

### Bloques de código multilínea

Se usan tres comillas invertidas ` ``` ` y se puede especificar el lenguaje para resaltado de sintaxis.

**Ejemplo en JavaScript:**

```javascript
// Función para calcular el factorial
function factorial(n) {
  if (n === 0 || n === 1) return 1;
  return n * factorial(n - 1);
}

console.log(factorial(5)); // Output: 120
```

**Ejemplo en Python:**

```python
# Función Fibonacci con recursión
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n - 1) + fibonacci(n - 2)

for i in range(10):
    print(fibonacci(i), end=" ")
# Output: 0 1 1 2 3 5 8 13 21 34
```

**Ejemplo en Bash:**

```bash
#!/bin/bash
# Script de despliegue
echo "Iniciando despliegue..."
git pull origin main
npm install --production
pm2 restart app
echo "¡Despliegue completado!"
```

---

## 7. Tablas

Las tablas se crean con `|` para columnas y `-` para separar encabezados del contenido. Se puede alinear el texto con `:`.

**Sintaxis:**

```markdown
| Encabezado 1 | Encabezado 2 | Encabezado 3 |
|:------------|:------------:|-------------:|
| Izquierda   |   Centro     |    Derecha   |
| dato 1      |   dato 2     |    dato 3    |
```

**Ejemplos prácticos:**

### Tabla de comparación de lenguajes:

| Lenguaje   | Tipo        | Velocidad | Popularidad |
|:-----------|:------------|:---------:|------------:|
| Python     | Interpretado| Media     | ⭐⭐⭐⭐⭐ |
| C++        | Compilado   | Alta      | ⭐⭐⭐⭐   |
| JavaScript | Interpretado| Media     | ⭐⭐⭐⭐⭐ |
| Rust       | Compilado   | Muy alta  | ⭐⭐⭐     |
| Go         | Compilado   | Alta      | ⭐⭐⭐⭐   |

### Tabla de comandos Git:

| Comando              | Descripción                          |
|----------------------|--------------------------------------|
| `git init`           | Inicializa un repositorio            |
| `git clone <url>`    | Clona un repositorio remoto          |
| `git add .`          | Agrega todos los cambios al staging  |
| `git commit -m "msg"`| Guarda los cambios con un mensaje    |
| `git push`           | Sube los cambios al repositorio      |

---

## 8. Citas

Las citas se crean con el símbolo `>` al inicio de la línea. Se pueden anidar con `>>`.

**Sintaxis:**
```markdown
> Esto es una cita simple.

> Cita de primer nivel
>> Cita anidada de segundo nivel
>>> Cita de tercer nivel
```

**Ejemplos prácticos:**

> "La simplicidad es la máxima sofisticación."
> — Leonardo da Vinci

> **Importante:** Recuerda siempre hacer commit de tus cambios antes de cambiar de rama.
>
> Si no lo haces, podrías perder trabajo no guardado.

> **Ejemplo de cita anidada en documentación técnica:**
>
> La especificación indica:
>> "Todos los parámetros deben ser validados antes de procesarse."
>>
>> En caso de error:
>>> Retornar código HTTP 400 con mensaje descriptivo.

---

## 9. Checklists (Listas de verificación)

Las checklists se crean con `- [ ]` para tareas pendientes y `- [x]` para tareas completadas.

**Sintaxis:**

```markdown
- [x] Tarea completada
- [ ] Tarea pendiente
- [ ] Otra tarea pendiente
```

**Ejemplos prácticos:**

### Lista de verificación para lanzar un proyecto:

- [x] Definir los requisitos del proyecto
- [x] Crear el repositorio en GitHub
- [x] Configurar el entorno de desarrollo
- [x] Escribir el README.md inicial
- [ ] Implementar autenticación de usuarios
- [ ] Conectar la base de datos
- [ ] Escribir pruebas unitarias
- [ ] Configurar CI/CD con GitHub Actions
- [ ] Realizar revisión de seguridad
- [ ] Desplegar en producción

### Checklist de revisión de código (Code Review):

- [x] El código sigue las convenciones del proyecto
- [x] No hay variables sin usar
- [x] Las funciones tienen nombres descriptivos
- [ ] Todas las funciones tienen documentación JSDoc
- [ ] Los casos límite están cubiertos con tests
- [ ] No hay credenciales hardcodeadas

---
---

## PARTE 2 — Comparación de Herramientas de Documentación

---

## Herramientas Analizadas

Se analizaron **Markdown puro**, **Notion**, **Obsidian**, **Confluence** y **Google Docs**, considerando su uso en contextos personales, académicos y empresariales.

---

## Tabla Comparativa Principal

| Característica         | Markdown               | Notion                  | Obsidian               | Confluence              | Google Docs             |
|:-----------------------|:-----------------------|:------------------------|:-----------------------|:------------------------|:------------------------|
| **Facilidad de uso**   | Media — requiere aprender sintaxis | Alta — interfaz intuitiva con bloques | Media — curva inicial moderada | Media-Baja — complejo para nuevos usuarios | Alta — similar a Word, muy familiar |
| **Trabajo colaborativo** | Básico (depende de Git/GitHub) | Excelente — colaboración en tiempo real con comentarios | Limitado — orientado al uso individual | Excelente — diseñado para equipos empresariales | Excelente — colaboración en tiempo real con historial |
| **Organización**       | Manual — carpetas y archivos del sistema | Alta — bases de datos, vistas, jerarquías | Alta — grafo de conocimiento, backlinks, tags | Alta — espacios, páginas y subpáginas anidadas | Media — carpetas en Drive, sin estructura interna avanzada |
| **Compatibilidad**     | Muy alta — universal, funciona en cualquier editor o plataforma | Media — propietario, exportación limitada | Alta — archivos `.md` nativos en disco | Media — integrado con Jira/Atlassian, limitado fuera de él | Alta — integrado con todo el ecosistema Google |
| **Exportación de documentos** | Excelente — convierte a HTML, PDF, Word, etc. con Pandoc | Limitada — PDF y Markdown básico, con pérdida de formato | Buena — exporta a PDF y Markdown, pero sin estilo | Buena — Word, PDF, aunque pierde algo de formato | Excelente — Word, PDF, ODT, EPUB, HTML |
| **Uso profesional**    | Muy alto en desarrollo de software, DevOps, documentación técnica | Alto en startups, gestión de proyectos, wikis personales y de equipo | Alto para investigadores, escritores y gestión del conocimiento personal | Muy alto en empresas medianas y grandes (especialmente con Jira) | Muy alto en educación, negocios generales, trabajo en equipo |
| **Curva de aprendizaje** | Media — sintaxis fácil de aprender, pero el ecosistema puede ser complejo | Baja — intuitivo desde el primer día | Media — conceptos de PKM y backlinks nuevos para muchos | Alta — interfaz densa, muchas opciones, administración compleja | Muy baja — casi todo el mundo ya lo conoce |
| **Dependencia de internet** | Ninguna — 100% offline con cualquier editor de texto | Alta — funcionalidad completa solo online (app desktop limitada) | Ninguna — 100% offline por diseño (sincronización opcional) | Total — completamente basado en la nube | Alta — funcionalidad completa solo online, offline muy limitado |

---

## Análisis Detallado por Herramienta

---

### 🔷 Markdown

**¿Qué es?** Un lenguaje de marcado ligero creado por John Gruber en 2004. No es una aplicación, sino un estándar de formato de texto plano.

**Fortalezas:**
- Portabilidad total: los archivos `.md` abren en cualquier sistema operativo
- Control de versiones con Git (ideal para equipos de desarrollo)
- Compatible con GitHub, GitLab, Jupyter, VS Code, Jekyll, Hugo y cientos de herramientas
- Texto plano = sin bloqueo por proveedor (vendor lock-in)
- Ideal para documentación técnica, READMEs, wikis de código

**Debilidades:**
- Sin interfaz gráfica nativa — necesita un editor o visor
- Colaboración limitada sin herramientas adicionales (Git, GitHub)
- Variaciones entre sabores (GitHub Flavored Markdown, CommonMark, MultiMarkdown)
- No apto para usuarios no técnicos

**Mejor para:** Desarrolladores, ingenieros de software, escritores técnicos, proyectos open source.

---

### 🟠 Notion

**¿Qué es?** Una plataforma todo-en-uno para notas, gestión de proyectos, bases de datos y wikis colaborativos.

**Fortalezas:**
- Interfaz tipo bloques muy intuitiva (arrastrar y soltar)
- Bases de datos relacionales con múltiples vistas (tabla, kanban, calendario, galería)
- Excelente para wikis de equipo y documentación viva
- Plantillas profesionales listas para usar
- Integración con Slack, GitHub, Figma, entre otros
- Soporte nativo de Markdown en el editor

**Debilidades:**
- Requiere conexión a internet para funcionalidad completa
- La exportación puede perder formato complejo (bases de datos → CSV/Markdown simple)
- Puede ser lento con documentos muy grandes
- El plan gratuito tiene limitaciones de páginas para equipos

**Mejor para:** Startups, equipos pequeños y medianos, gestión de proyectos, wikis empresariales, freelancers.

---

### 🟣 Obsidian

**¿Qué es?** Una aplicación de toma de notas y gestión del conocimiento personal (PKM) basada en archivos Markdown locales.

**Fortalezas:**
- 100% offline — todos los datos son archivos `.md` en tu disco
- Sistema de backlinks bidireccionales y grafo de conocimiento visual
- Altamente personalizable con plugins de la comunidad (más de 1,000)
- Compatible con cualquier servicio de sincronización (iCloud, Dropbox, Git)
- Sin vendor lock-in: tus notas son tuyas para siempre
- Ideal para gestión del conocimiento personal (Zettelkasten, Second Brain)

**Debilidades:**
- Colaboración en tiempo real muy limitada (plugin de Obsidian Sync es de pago)
- La curva de aprendizaje puede ser alta para quienes no conocen PKM
- El ecosistema de plugins puede ser abrumador al inicio
- No tiene funcionalidades de gestión de proyectos integradas

**Mejor para:** Investigadores, estudiantes, escritores, desarrolladores que quieren un sistema de conocimiento personal robusto.

---

### 🔵 Confluence (Atlassian)

**¿Qué es?** Una wiki empresarial colaborativa de Atlassian, diseñada para integrarse con Jira y el ecosistema de herramientas de desarrollo de software.

**Fortalezas:**
- Integración nativa con Jira, Trello, Bitbucket y otras herramientas Atlassian
- Espacios de trabajo organizados para grandes equipos y departamentos
- Plantillas empresariales predefinidas
- Gestión de permisos granular
- Historial de versiones completo
- Comentarios en línea y menciones

**Debilidades:**
- Curva de aprendizaje elevada para nuevos usuarios
- Interfaz densa y a veces poco intuitiva
- Costo elevado para equipos grandes
- Completamente dependiente de internet
- Puede volverse desorganizado sin una buena estrategia de gobernanza

**Mejor para:** Empresas medianas y grandes, equipos de desarrollo de software, organizaciones que ya usan Jira.

---

### 🟢 Google Docs

**¿Qué es?** Procesador de texto en la nube de Google, parte del ecosistema Google Workspace.

**Fortalezas:**
- Colaboración en tiempo real con comentarios, sugerencias y control de versiones
- Extremadamente familiar — similar a Microsoft Word
- Integración total con Google Drive, Sheets, Slides, Meet y Gmail
- Excelente para exportar a múltiples formatos (DOCX, PDF, ODT, HTML)
- Accesible desde cualquier dispositivo con navegador
- Plan gratuito muy completo

**Debilidades:**
- Funcionalidad offline muy limitada (modo offline básico)
- No es ideal para documentación técnica o código
- Sin sistema de backlinks ni organización de conocimiento avanzada
- Depende completamente de la cuenta de Google
- No soporta Markdown nativamente (aunque hay extensiones)

**Mejor para:** Educación, trabajo en oficina, documentos colaborativos generales, cualquier usuario no técnico.
