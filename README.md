# Biblioteca-Springboot

## Descripción del proyecto

**Biblioteca-Springboot** es un proyecto académico desarrollado para la
asignatura **Ingeniería DevOps (DOY0101)** de **Duoc UC**.

El proyecto corresponde a una aplicación basada en una arquitectura de
microservicios desarrollada principalmente con **Java y Spring Boot**.

El objetivo del proyecto es aplicar conceptos y buenas prácticas de
**Ingeniería DevOps**, especialmente en:

- Control de versiones.
- Trabajo colaborativo.
- Gestión de ramas.
- Git y GitHub.
- Pull Requests.
- Integración continua.
- Automatización mediante GitHub Actions.
- Construcción de aplicaciones mediante Maven.
- Construcción de imágenes mediante Docker.
- Trazabilidad de cambios.
- Buenas prácticas de desarrollo y versionamiento.

El repositorio permite simular un flujo de trabajo utilizado en equipos de
desarrollo de software, donde los cambios son desarrollados en ramas
independientes, revisados mediante Pull Requests y posteriormente integrados
a las ramas principales.

---

# Objetivos del proyecto

Los principales objetivos son:

- Aplicar control de versiones utilizando Git.
- Utilizar GitHub como repositorio remoto.
- Implementar una estrategia de ramificación.
- Aplicar buenas prácticas para nombres de ramas.
- Aplicar buenas prácticas para mensajes de commit.
- Utilizar Pull Requests para integrar cambios.
- Mantener la trazabilidad de los cambios realizados.
- Utilizar GitHub Actions para automatizar procesos.
- Implementar un flujo básico de Integración Continua (CI).
- Utilizar Maven para construir los proyectos Java.
- Utilizar Docker para construir las imágenes de los servicios.
- Documentar el proyecto mediante `README.md`.

---

# Tecnologías y herramientas

Las principales tecnologías y herramientas utilizadas son:

| Tecnología / Herramienta | Uso |
|---|---|
| Java 21 | Lenguaje de programación |
| Spring Boot | Desarrollo de microservicios |
| Spring Cloud | Componentes para arquitectura distribuida |
| Maven | Gestión y construcción del proyecto |
| PostgreSQL | Base de datos |
| Docker | Contenedores |
| Docker Compose | Orquestación de servicios |
| Git | Control de versiones |
| GitHub | Repositorio remoto y colaboración |
| GitHub Actions | Automatización CI/CD |
| Eureka Server | Descubrimiento de servicios |
| API Gateway | Entrada y comunicación con los microservicios |
| Postman | Pruebas de APIs |
| Visual Studio Code | Entorno de desarrollo |

---

# 🏗️ Arquitectura del proyecto

El proyecto se encuentra organizado mediante diferentes módulos y
microservicios.

```text
Biblioteca-Springboot/
│
├── .github/
│   └── workflows/
│       └── main.yml
│
├── api-gateway/
│   ├── src/
│   ├── target/
│   ├── Dockerfile
│   └── pom.xml
│
├── common/
│
├── eureka/
│   ├── src/
│   ├── target/
│   ├── Dockerfile
│   └── pom.xml
│
├── init-multi-db/
│
├── ms-catalogo/
│   ├── src/
│   ├── target/
│   ├── Dockerfile
│   └── pom.xml
│
├── ms-recursos/
│   ├── src/
│   ├── target/
│   ├── Dockerfile
│   └── pom.xml
│
├── ms-usuarios/
│   ├── src/
│   ├── target/
│   ├── Dockerfile
│   └── pom.xml
│
├── postman/
│
├── docker-compose.yml
├── pom.xml
└── README.md
```

Esta organización permite separar los distintos componentes del sistema,
facilitando su desarrollo, mantenimiento, versionamiento y posterior
automatización.

---

# 🔀 Estrategia de ramificación

Para organizar el desarrollo se utiliza una estrategia basada en ramas
principales y ramas destinadas a funcionalidades y correcciones.

La estructura general es:

```text
main
 │
 └── develop
       │
       ├── feature/<nombre>
       │
       ├── feature/<nombre>
       │
       └── hotfix/<nombre>
```

## 🌳 Rama `main`

La rama `main` corresponde a la rama principal del proyecto.

Su objetivo es mantener una versión estable del código.

Los cambios importantes deben ser integrados mediante un Pull Request.

---

## 🌱 Rama `develop`

La rama `develop` se utiliza como rama de integración del desarrollo.

Las nuevas funcionalidades pueden ser desarrolladas en ramas `feature/*` y
posteriormente integradas en `develop`.

---

## 🚀 Ramas `feature/*`

Las ramas `feature/*` se utilizan para desarrollar nuevas funcionalidades.

Ejemplos:

```text
feature/github-actions
feature/catalogo
feature/usuarios
```

El formato utilizado es:

```text
feature/<nombre-de-la-funcionalidad>
```

Esto permite identificar rápidamente el propósito de cada rama.

---

## 🛠️ Ramas `hotfix/*`

Las ramas `hotfix/*` se utilizan para solucionar errores o problemas
específicos.

Ejemplos:

```text
hotfix/error-login
hotfix/error-workflow
hotfix/error-docker
```

---

# 💡 Justificación de la estrategia de ramificación

La utilización de diferentes tipos de ramas permite separar el desarrollo de
nuevas funcionalidades de las versiones estables del proyecto.

Las ramas `feature/*` permiten trabajar en nuevas funcionalidades sin modificar
directamente las ramas principales.

Las ramas `hotfix/*` permiten realizar correcciones específicas de manera
aislada.

Finalmente, los Pull Requests permiten revisar los cambios antes de realizar
la integración.

Esta estrategia facilita el trabajo colaborativo y mejora la trazabilidad del
desarrollo.

---

# 🏷️ Convención de nombres de ramas

Para mantener una estructura organizada se utilizan nombres descriptivos.

### Funcionalidades

```text
feature/<nombre>
```

Ejemplos:

```text
feature/github-actions
feature/catalogo
feature/usuarios
```

### Correcciones

```text
hotfix/<nombre>
```

Ejemplos:

```text
hotfix/error-workflow
hotfix/error-docker
```

### Buenas prácticas

Los nombres de las ramas deben:

- Ser descriptivos.
- Ser cortos.
- Utilizar minúsculas.
- Utilizar guiones cuando sea necesario.
- Indicar claramente el objetivo de la rama.

---

# 📝 Convención de commits

Los mensajes de commit deben permitir identificar fácilmente qué cambio fue
realizado.

Se utilizan diferentes tipos según el propósito del cambio.

## `feat`

Se utiliza para nuevas funcionalidades.

```bash
git commit -m "feat: agregar endpoint de usuarios"
```

---

## `fix`

Se utiliza para solucionar errores.

```bash
git commit -m "fix: corregir configuración de Maven"
```

---

## `docs`

Se utiliza para cambios relacionados con documentación.

```bash
git commit -m "docs: agregar README del proyecto"
```

---

## `ci`

Se utiliza para cambios relacionados con integración continua.

```bash
git commit -m "ci: agregar workflow de GitHub Actions"
```

---

## `chore`

Se utiliza para tareas de mantenimiento o configuración.

```bash
git commit -m "chore: actualizar configuración del proyecto"
```

---

# 💻 Comandos utilizados en el proyecto

Durante el desarrollo del proyecto se utilizaron comandos de terminal y Git
para crear directorios, administrar archivos, controlar versiones y trabajar
colaborativamente mediante GitHub.

---

# 🖥️ Comandos básicos de terminal

## `mkdir`

El comando `mkdir` permite crear directorios o carpetas desde la terminal.

### Sintaxis

```bash
mkdir nombre-carpeta
```

### Ejemplo

```bash
mkdir proyecto
```

Este comando crea una carpeta llamada `proyecto`.

Dentro de un flujo DevOps puede utilizarse para crear y organizar la estructura
inicial de un proyecto.

Por ejemplo:

```bash
mkdir src
mkdir docs
mkdir tests
```

---

## `echo`

El comando `echo` permite mostrar texto en la terminal.

También puede utilizarse junto con `>` para crear un archivo y escribir
contenido dentro de él.

### Ejemplo

```bash
echo "# Biblioteca-Springboot" > README.md
```

Este comando crea el archivo `README.md` y agrega el texto indicado.

Dentro de Ingeniería DevOps, `echo` puede utilizarse en scripts para generar
archivos, mensajes o configuraciones de forma automatizada.

---

## `cd`

El comando `cd` permite cambiar de directorio.

### Ejemplo

```bash
cd Biblioteca-Springboot
```

Permite ingresar a la carpeta del proyecto para ejecutar comandos sobre ella.

---

## `dir`

En Windows, el comando `dir` permite visualizar los archivos y carpetas
existentes en el directorio actual.

### Ejemplo

```bash
dir
```

Es útil para comprobar la estructura del proyecto y verificar que los archivos
se encuentren en la ubicación esperada.

---

## `cls`

El comando `cls` permite limpiar la pantalla de la terminal en Windows.

### Ejemplo

```bash
cls
```

Este comando solamente limpia la visualización de la terminal y no modifica
los archivos del proyecto.

---

# 🔧 Comandos básicos de Git

Git es el sistema de control de versiones utilizado para registrar y administrar
los cambios realizados en el proyecto.

Permite mantener un historial de modificaciones y facilita el trabajo
colaborativo.

---

## `git init`

Inicializa un repositorio Git en una carpeta.

```bash
git init
```

Se utiliza para comenzar a controlar las versiones de un proyecto local.

---

## `git clone`

Permite obtener una copia local de un repositorio remoto.

```bash
git clone URL_DEL_REPOSITORIO
```

Por ejemplo:

```bash
git clone https://github.com/usuario/proyecto.git
```

Se utiliza cuando un integrante necesita obtener el proyecto desde GitHub para
comenzar a trabajar.

---

## `git status`

Permite consultar el estado actual del repositorio.

```bash
git status
```

Permite identificar:

- Archivos modificados.
- Archivos nuevos.
- Archivos preparados para commit.
- Rama actual.

Es recomendable utilizarlo antes de realizar un commit.

---

## `git add`

Permite agregar cambios al área de preparación o `staging area`.

Para agregar todos los cambios:

```bash
git add .
```

Para agregar un archivo específico:

```bash
git add README.md
```

Los archivos quedan preparados para realizar posteriormente un commit.

---

## `git commit`

Registra los cambios preparados en el historial local de Git.

```bash
git commit -m "docs: agregar README del proyecto"
```

El commit permite mantener la trazabilidad de los cambios realizados.

---

## `git push`

Envía los commits locales al repositorio remoto.

```bash
git push origin develop
```

Si se está trabajando en una rama específica:

```bash
git push origin feature/github-actions
```

Permite compartir los cambios con el equipo y actualizar la rama en GitHub.

---

## `git pull`

Obtiene los cambios existentes en el repositorio remoto y los integra en la
rama local.

```bash
git pull origin develop
```

Se recomienda utilizarlo antes de comenzar a trabajar para mantener la rama
actualizada.

---

## `git fetch`

Obtiene información actualizada de las ramas remotas sin integrar
automáticamente los cambios.

```bash
git fetch origin
```

Permite revisar el estado del repositorio remoto antes de realizar operaciones
como `merge`.

---

## `git branch`

Permite visualizar y administrar ramas.

Para visualizar las ramas locales:

```bash
git branch
```

Para visualizar ramas locales y remotas:

```bash
git branch -a
```

Para crear una rama:

```bash
git branch feature/catalogo
```

---

## `git checkout`

Permite cambiar entre ramas.

```bash
git checkout develop
```

También permite crear una rama y cambiarse inmediatamente a ella:

```bash
git checkout -b feature/catalogo
```

---

## `git switch`

Es una alternativa moderna para cambiar entre ramas.

```bash
git switch develop
```

Para crear una nueva rama y cambiarse a ella:

```bash
git switch -c feature/catalogo
```

---

## `git merge`

Permite integrar los cambios de una rama dentro de otra.

Ejemplo:

```bash
git switch develop
git merge feature/catalogo
```

En este caso, los cambios de `feature/catalogo` son integrados en `develop`.

En un flujo colaborativo, esta integración también puede realizarse mediante
un Pull Request en GitHub.

---

## `git log`

Permite visualizar el historial de commits.

```bash
git log
```

Una versión resumida:

```bash
git log --oneline
```

También permite visualizar el historial de las ramas:

```bash
git log --oneline --graph --all
```

Este comando es útil para comprobar la trazabilidad de los cambios.

---

## `git diff`

Permite visualizar las diferencias entre los cambios realizados.

```bash
git diff
```

Es útil para revisar las modificaciones antes de ejecutar `git add`.

---

## `git remote`

Permite consultar los repositorios remotos asociados al proyecto.

```bash
git remote -v
```

Normalmente el repositorio principal de GitHub se identifica como:

```text
origin
```

---

## `git remote add`

Permite asociar un repositorio remoto al repositorio local.

```bash
git remote add origin URL_DEL_REPOSITORIO
```

---

## `git restore`

Permite descartar cambios locales que todavía no han sido confirmados.

```bash
git restore archivo.txt
```

Debe utilizarse con precaución, ya que puede eliminar modificaciones locales.

---

# 📋 Resumen de comandos

| Comando | ¿Para qué sirve? |
|---|---|
| `mkdir` | Crear carpetas |
| `echo` | Mostrar o generar texto |
| `cd` | Cambiar de directorio |
| `dir` | Mostrar archivos y carpetas en Windows |
| `cls` | Limpiar la terminal |
| `git init` | Inicializar un repositorio Git |
| `git clone` | Clonar un repositorio remoto |
| `git status` | Consultar el estado del repositorio |
| `git add` | Preparar cambios |
| `git commit` | Registrar cambios |
| `git push` | Enviar cambios al repositorio remoto |
| `git pull` | Obtener e integrar cambios remotos |
| `git fetch` | Obtener información del repositorio remoto |
| `git branch` | Crear y administrar ramas |
| `git checkout` | Cambiar o crear ramas |
| `git switch` | Cambiar o crear ramas |
| `git merge` | Integrar ramas |
| `git log` | Consultar historial |
| `git diff` | Visualizar diferencias |
| `git remote` | Consultar repositorios remotos |
| `git restore` | Descartar cambios locales |

---

# 🌐 GitHub y trabajo colaborativo

GitHub permite almacenar el repositorio Git de manera remota y proporciona
herramientas para trabajar colaborativamente.

Entre las principales herramientas utilizadas se encuentran:

- Repositorios.
- Ramas.
- Pull Requests.
- Fork.
- Historial de commits.
- GitHub Actions.

---

# 🍴 Fork

Un **Fork** permite crear una copia de un repositorio de GitHub dentro de otra
cuenta.

El flujo general es:

```text
Repositorio original
        │
        ▼
      Fork
        │
        ▼
Copia del repositorio
        │
        ▼
Crear rama
        │
        ▼
Realizar cambios
        │
        ▼
Commit
        │
        ▼
Push
        │
        ▼
Pull Request
        │
        ▼
Repositorio original
```

El Fork resulta útil cuando una persona necesita trabajar sobre una copia de
un proyecto sin modificar directamente el repositorio original.

---

# 🔄 Pull Request

Un **Pull Request (PR)** permite solicitar la integración de los cambios
realizados en una rama hacia otra.

Por ejemplo:

```text
feature/catalogo
       │
       │ Pull Request
       ▼
    develop
```

También puede utilizarse para integrar cambios desde `develop` hacia `main`:

```text
develop
   │
   │ Pull Request
   ▼
  main
```

El Pull Request permite revisar los cambios antes de realizar la integración.

---

# 🔁 Flujo colaborativo con Git

El flujo utilizado para desarrollar una funcionalidad puede representarse de
la siguiente manera:

```text
             develop
                │
                ▼
        Crear rama feature
                │
                ▼
     feature/nueva-funcionalidad
                │
                ▼
          Modificar código
                │
                ▼
           git status
                │
                ▼
             git add
                │
                ▼
           git commit
                │
                ▼
             git push
                │
                ▼
             GitHub
                │
                ▼
        Pull Request
                │
                ▼
             Revisión
                │
                ▼
              Merge
                │
                ▼
             develop
```

Este flujo permite mantener un historial de cambios y facilita la colaboración
entre los integrantes del equipo.

---

# 🧪 Maven

Maven es utilizado para administrar la construcción de los proyectos Java.

Permite administrar dependencias y generar los artefactos necesarios para
ejecutar o empaquetar las aplicaciones.

Algunos comandos utilizados son:

```bash
mvn clean
```

Limpia los archivos generados anteriormente.

```bash
mvn package
```

Construye y empaqueta la aplicación.

```bash
mvn clean package
```

Limpia el proyecto y posteriormente lo empaqueta.

En el flujo de automatización se puede utilizar:

```bash
mvn -B clean package -DskipTests
```

La opción:

```text
-DskipTests
```

permite omitir la ejecución de pruebas durante el proceso de empaquetado.

---

# 🐳 Docker

Docker permite empaquetar las aplicaciones dentro de imágenes y ejecutarlas
como contenedores.

Cada servicio principal del proyecto posee un `Dockerfile`.

Docker Compose permite administrar varios servicios de manera conjunta.

---

## Construir las imágenes

```bash
docker compose build
```

Construye las imágenes definidas en `docker-compose.yml`.

---

## Iniciar los servicios

```bash
docker compose up -d
```

Inicia los servicios definidos en Docker Compose en segundo plano.

---

## Ver el estado de los servicios

```bash
docker compose ps
```

Permite comprobar qué contenedores están ejecutándose.

---

## Detener los servicios

```bash
docker compose down
```

Detiene y elimina los contenedores creados por Docker Compose.

---

# ⚙️ GitHub Actions

GitHub Actions permite automatizar procesos dentro del repositorio.

En este proyecto se utiliza para implementar un flujo básico de integración
continua.

El workflow se encuentra en:

```text
.github/workflows/main.yml
```

La configuración permite ejecutar el workflow cuando:

- Se realiza un `push` a `develop`.
- Se genera un Pull Request hacia `main`.

Configuración:

```yaml
on:
  push:
    branches:
      - develop

  pull_request:
    branches:
      - main
```

---

# 🔄 Flujo de Integración Continua

El workflow implementado sigue una estructura similar a:

```text
Desarrollador
      │
      ▼
     Git
      │
      ├── branch
      ├── add
      ├── commit
      └── push
             │
             ▼
           GitHub
             │
             ▼
      GitHub Actions
             │
             ├── Checkout
             │
             ├── Java 21
             │
             ├── Maven
             │
             └── Docker Build
             │
             ▼
          Resultado
```

De esta manera, determinadas tareas pueden ejecutarse automáticamente cada
vez que se producen cambios en el repositorio.

---

# 📄 Workflow de GitHub Actions

El archivo:

```text
.github/workflows/main.yml
```

contiene la configuración de automatización.

El workflow utilizado tiene la siguiente estructura:

```yaml
name: Biblioteca-Springboot CI/CD

on:
  push:
    branches:
      - develop

  pull_request:
    branches:
      - main

jobs:

  build:
    name: Build
    runs-on: ubuntu-latest

    steps:

      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Set up Java 21
        uses: actions/setup-java@v4
        with:
          distribution: temurin
          java-version: '21'
          cache: maven

      - name: Package applications
        run: mvn -B clean package -DskipTests

  docker:
    name: Build Docker Images
    runs-on: ubuntu-latest
    needs: build

    steps:

      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Set up Java 21
        uses: actions/setup-java@v4
        with:
          distribution: temurin
          java-version: '21'
          cache: maven

      - name: Package applications
        run: mvn -B clean package -DskipTests

      - name: Build Docker images
        run: docker compose build
```

El flujo se divide en dos trabajos principales:

### Build

Se encarga de:

1. Descargar el código del repositorio.
2. Configurar Java 21.
3. Ejecutar Maven.
4. Empaquetar las aplicaciones.

### Docker

Se ejecuta después del trabajo `Build`.

Se encarga de:

1. Descargar el código.
2. Configurar Java.
3. Empaquetar las aplicaciones.
4. Construir las imágenes Docker.

La relación entre ambos trabajos se establece mediante:

```yaml
needs: build
```

Esto indica que el trabajo de Docker depende de que el trabajo `Build` termine
correctamente.

---

# 🔗 Relación entre Git, GitHub y GitHub Actions

El flujo completo puede representarse de la siguiente manera:

```text
             DESARROLLO
                 │
                 ▼
             Git Branch
                 │
                 ▼
              Cambios
                 │
                 ▼
              git add
                 │
                 ▼
             git commit
                 │
                 ▼
              git push
                 │
                 ▼
              GitHub
                 │
          ┌──────┴──────┐
          │             │
          ▼             ▼
    Pull Request    GitHub Actions
          │             │
          ▼             ├── Maven
        Revisión        │
          │             └── Docker
          ▼
        Merge
          │
          ▼
       develop/main
```

Git se encarga principalmente del control de versiones.

GitHub permite almacenar el repositorio y colaborar.

GitHub Actions permite automatizar procesos sobre los cambios realizados.

---

# 🚀 Flujo DevOps del proyecto

El flujo general utilizado puede representarse como:

```text
┌──────────────────────────────┐
│         DESARROLLO           │
└──────────────┬───────────────┘
               │
               ▼
        Crear feature
               │
               ▼
        Modificar código
               │
               ▼
          git status
               │
               ▼
            git add
               │
               ▼
          git commit
               │
               ▼
           git push
               │
               ▼
            GitHub
               │
               ▼
        Pull Request
               │
               ▼
           Revisión
               │
               ▼
             Merge
               │
               ▼
            develop
               │
               ▼
       GitHub Actions
               │
        ┌──────┴──────┐
        ▼             ▼
      Maven         Docker
        │             │
        └──────┬──────┘
               ▼
          CI/CD
               │
               ▼
             main
```

Este flujo permite integrar control de versiones, colaboración y
automatización dentro de un mismo proceso.

---

# 📌 Buenas prácticas aplicadas

Durante el desarrollo se consideran las siguientes buenas prácticas:

- Mantener una estructura organizada de ramas.
- Evitar trabajar directamente sobre `main`.
- Utilizar ramas `feature/*` para nuevas funcionalidades.
- Utilizar ramas `hotfix/*` para correcciones.
- Utilizar nombres descriptivos para las ramas.
- Utilizar mensajes de commit claros.
- Realizar commits relacionados con cambios específicos.
- Mantener la trazabilidad de los cambios.
- Utilizar Pull Requests para integrar cambios.
- Mantener actualizado el repositorio local.
- Documentar el proyecto mediante `README.md`.
- Utilizar GitHub Actions para automatizar tareas.
- Utilizar Docker para facilitar la construcción y ejecución de servicios.

---

# 📊 Relación de herramientas con DevOps

| Herramienta | Aplicación dentro del proyecto |
|---|---|
| Git | Control de versiones |
| GitHub | Repositorio remoto y colaboración |
| GitHub Actions | Automatización e integración continua |
| Maven | Construcción y empaquetado |
| Docker | Contenerización |
| Docker Compose | Administración de múltiples servicios |
| Postman | Pruebas de servicios |
| Visual Studio Code | Desarrollo y administración del código |

---

# 📚 Flujo resumido de comandos

Un flujo básico de trabajo puede realizarse de la siguiente manera:

```bash
# Clonar el repositorio
git clone URL_DEL_REPOSITORIO

# Entrar al proyecto
cd Biblioteca-Springboot

# Revisar el estado
git status

# Crear una nueva rama
git switch -c feature/nueva-funcionalidad

# Realizar modificaciones...

# Revisar los cambios
git status

# Agregar los cambios
git add .

# Crear commit
git commit -m "feat: agregar nueva funcionalidad"

# Enviar la rama a GitHub
git push -u origin feature/nueva-funcionalidad
```

Después del `push`, se puede crear un Pull Request desde GitHub para solicitar
la integración de la rama.

---

# 🔀 Flujo para integrar cambios

Ejemplo de integración de una funcionalidad:

```text
feature/nueva-funcionalidad
             │
             │ Pull Request
             ▼
          develop
             │
             │ Pull Request
             ▼
            main
```

De esta manera se mantiene separada la etapa de desarrollo de la versión
principal del proyecto.

---

# 👨‍💻 Integrante

**Nombre:** Pablo Reyes

**Institución:** Duoc UC

**Asignatura:** Ingeniería DevOps