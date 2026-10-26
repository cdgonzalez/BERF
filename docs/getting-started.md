# Guía de Inicio Rápido — BERF (Backend Engineer Resume Framework)

**BERF** es un framework modular en LaTeX diseñado específicamente para ingenieros de software backend, enfocado en legibilidad, cumplimiento con sistemas ATS (Applicant Tracking Systems) y diseño basado en tokens.

---

## 1. Requisitos Previos

Para compilar documentos que utilicen paquetes modernos como `fontspec` y fuentes OpenType/TrueType, se requiere una distribución de TeX con soporte para **XeLaTeX** o **LuaLaTeX**:

- **Windows**: [MiKTeX](https://miktex.org/) o [TeX Live para Windows](https://tug.org/texlive/).
- **Linux (Debian/Ubuntu)**:
  ```bash
  sudo apt update
  sudo apt install texlive-xetex texlive-fonts-recommended texlive-fonts-extra texlive-plain-generic
  ```
- **macOS**: [MacTeX](https://www.tug.org/mactex/).

### Fuentes recomendadas
Por defecto, el framework utiliza:
- **Texto Principal**: `TeX Gyre Heros` (alternativa libre a Helvetica/Arial, estándar en TeX Live/MiKTeX) o `Arial`.
- **Código y Badges**: `Inconsolata` (o `Consolas` / `Fira Code`).

---

## 2. Personalización de Datos del Candidato

Edita el archivo [`config/metadata.tex`](file:///c:/Users/Prueba/Documents/Dev/BERF/config/metadata.tex) con tu información:

```latex
\newcommand{\cvName}{Tu Nombre Completo}
\newcommand{\cvHeadline}{Senior Backend Engineer | Distributed Systems}
\newcommand{\cvLocation}{Ciudad, País}
\newcommand{\cvEmail}{tu.email@dominio.com}
\newcommand{\cvPhone}{+52 55 1234 5678}
\newcommand{\cvLinkedinUser}{tu-usuario}
\newcommand{\cvGithubUser}{tu-usuario}
\newcommand{\cvWebsiteDisplay}{tuweb.dev}
\newcommand{\cvWebsiteUrl}{https://tuweb.dev}
```

Estos valores alimentarán tanto el encabezado visible del currículum como los metadatos internos del archivo PDF (autor, título, keywords).

---

## 3. Estructuración del Contenido

El contenido está dividido modularmente en la carpeta [`sections/`](file:///c:/Users/Prueba/Documents/Dev/BERF/sections):

1. **`sections/summary.tex`**: Breve síntesis de perfil técnico.
2. **`sections/skills.tex`**: Categorías de tecnologías con pills/badges (`\cvTag`).
3. **`sections/experience.tex`**: Roles y empresas con viñetas orientadas a métricas (TPS, latencia, costos).
4. **`sections/projects.tex`**: Repositorios destacados y arquitecturas implementadas.
5. **`sections/education.tex`**: Títulos y certificaciones académicas.
6. **Módulos Opcionales**:
   - `sections/certifications.tex`: Credenciales cloud (AWS, CKA, Terraform).
   - `sections/languages.tex`: Nivel de idiomas.
   - `sections/awards.tex`: Hackathons, conferencias y publicaciones.

---

## 4. Compilación

### Compilación desde Terminal (PowerShell o Bash)

```powershell
# Crear directorio de salida si no existe
New-Item -ItemType Directory -Force -Path output | Out-Null

# Compilar con XeLaTeX apuntando a output/
xelatex -output-directory=output main.tex
```

> **Nota**: Se recomienda compilar dos veces consecutivas en la primera ejecución para que `hyperref` resuelva correctamente todos los enlaces y metadatos cruzados.

### Compilación en VS Code
Si utilizas la extensión **LaTeX Workshop**:
1. Configura el recipe de compilación como `xelatex`.
2. Presiona `Ctrl + Alt + B` para compilar.
3. El visor integrado mostrará el PDF generado en tiempo real.

