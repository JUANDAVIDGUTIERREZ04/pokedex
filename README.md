# ⚡ PokeDex - Despliegue en Azure Static Web Apps

Aplicación web interactiva desarrollada en Angular para la exploración y consulta de la PokeAPI, desplegada en la nube de Microsoft Azure bajo estrictas políticas de seguridad web (Calificación **A+** en SecurityHeaders).

---

## 📋 Tabla de Contenido
1. [Descripción del Proyecto](#-descripción-del-proyecto)
2. [Paso 1: Creación de Cuenta y Configuración Inicial en Azure](#-paso-1-creación-de-cuenta-y-configuración-inicial-en-azure)
3. [Paso 2: Estructura del Repositorio y Configuración de Seguridad](#-paso-2-estructura-del-repositorio-y-configuración-de-seguridad)
4. [Paso 3: Proceso de Despliegue Continuo (CI/CD)](#-paso-3-proceso-de-despliegue-continuo-cicd)
5. [Enlaces de Entrega](#-enlaces-de-entrega)

---

## 🚀 Descripción del Proyecto
Este proyecto forma parte del caso de estudio de *Pueblo Paleta Inc. / PumasLab*, implementando una interfaz limpia estilo retro para la búsqueda y visualización de especies Pokémon, optimizada para un rendimiento rápido y un blindaje avanzado contra vulnerabilidades comunes (XSS, Clickjacking, etc.).

---

## ☁️ Paso 1: Creación de Cuenta y Configuración Inicial en Azure

Para desplegar la aplicación garantizando disponibilidad pública y alta velocidad de entrega de contenido estático, se utilizó **Azure Static Web Apps**:

1. **Registro en la plataforma:** 
   * Se ingresó al portal oficial de [Azure for Students](https://azure.microsoft.com/en-us/free/students/) utilizando la cuenta de correo institucional otorgada por la universidad.
   * Se completó la validación de identidad y la activación de la suscripción gratuita con los créditos educativos.
2. **Creación del recurso:**
   * En el buscador del Portal de Azure, se seleccionó el servicio **Static Web Apps**.
   * Se hizo clic en *Crear* y se configuró la suscripción, el grupo de recursos y el nombre de la aplicación (`pokedex`).
3. **Conexión con GitHub:**
   * Se autorizó a Azure para vincularse directamente con el repositorio oficial del proyecto en GitHub (`JUANDAVIDGUTIERREZ04/pokedex`).
   * Se especificó la rama principal (`main`) y los detalles de compilación del framework Angular (`dist/pokedex-angular`).

---

## 🔒 Paso 2: Configuración de Seguridad y Encabezados HTTP

Para cumplir con los estándares de la auditoría de seguridad y alcanzar la calificación máxima de **A+** en *SecurityHeaders.com*, se implementó el archivo de configuración global **`staticwebapp.config.json`** en la raíz del proyecto, incorporando:
* **Content-Security-Policy (CSP):** Restricción de scripts, estilos y orígenes permitidos para consumo de la PokeAPI y sprites de imágenes.
* **Strict-Transport-Security (HSTS):** Forzado de conexiones HTTPS con precarga.
* **X-Content-Type-Options & X-Frame-Options:** Prevención de ataques MIME-sniffing y Clickjacking.
* **NavigationFallback:** Regla de reescritura optimizada para enrutamiento SPA en Angular excluyendo los recursos estáticos de la carpeta `/assets/`.

---

## 🚀 Paso 3: Proceso de Despliegue
El despliegue se gestiona de forma automatizada mediante **GitHub Actions**. Cada vez que se realiza un `git push` a la rama `main`, Azure compila la aplicación Angular en segundo plano y publica la versión más actualizada de manera instantánea.

---

## 🔗 Enlaces de Entrega
* **URL de la Aplicación Desplegada (Azure):** [https://victorious-mushroom-0440b5010.5.azurestaticapps.net](https://victorious-mushroom-0440b5010.5.azurestaticapps.net)
* **URL del Repositorio (GitHub):** [https://github.com/JUANDAVIDGUTIERREZ04/pokedex](https://github.com/JUANDAVIDGUTIERREZ04/pokedex)
