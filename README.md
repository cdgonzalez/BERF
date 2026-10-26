# BERF — Backend Engineer Resume Framework

> **BERF** es un framework moderno, modular y extensible en LaTeX para crear currículums técnicos de alto impacto para Ingenieros de Software Backend.

Diseñado con un enfoque de **Sistema de Tokens de Diseño**, separación estricta de componentes, tipografía limpia y optimización tanto para lectores humanos como para sistemas ATS (Applicant Tracking Systems).

---

## 🚀 Características Principales

* **Sistema de Tokens de Diseño**: Colores, tipografía y espaciados desacoplados en `config/`.
* **Completamente Modular**: Secciones independientes en `sections/` (`summary`, `skills`, `experience`, `projects`, `education`, etc.).
* **Optimizado para ATS**: Estructura de texto plana, semántica limpia, sin tablas complejas anidadas que confundan a los parseadores automáticos.
* **Badges y Etiquetas Técnicas**: Macro `\cvTag` para destacar tecnologías clave (*Go, Rust, Kafka, Kubernetes, PostgreSQL, AWS*).
* **Orientado a Métricas de Backend**: Diseñado para resaltar throughput (TPS), latencias p99, optimizaciones de memoria y concurrencia.
* **Metadatos PDF Dinámicos**: Inyección automática de autor, título y palabras clave en el archivo PDF generado.

---

## 📁 Estructura del Proyecto

```
BERF/
├── config/                  # Capa del Sistema de Diseño
│   ├── packages.tex         # Dependencias centralizadas
│   ├── colors.tex           # Tokens semánticos de color
│   ├── fonts.tex            # Tipografía, jerarquías y tamaños
│   ├── layout.tex           # Geometría, márgenes y espaciados
│   ├── metadata.tex         # Datos del candidato y metadatos PDF
│   └── commands.tex         # Biblioteca de componentes UI
├── sections/                # Módulos de Contenido
│   ├── header.tex           # Bloque superior del CV
│   ├── summary.tex          # Extracto profesional
│   ├── skills.tex           # Habilidades y herramientas con badges
│   ├── experience.tex       # Experiencia laboral cuantificable
│   ├── projects.tex         # Proyectos de arquitectura distribuida
│   ├── education.tex        # Educación universitaria
│   ├── certifications.tex   # Credenciales cloud (AWS, CKA, Terraform)
│   ├── languages.tex        # Idiomas y fluidez
│   └── awards.tex           # Reconocimientos y conferencias
├── docs/                    # Documentación Técnica
│   ├── getting-started.md   # Requisitos previos y guía de compilación
│   ├── architecture.md      # Topología y catálogo de componentes
│   └── customization.md     # Personalización de temas, márgenes y métricas
├── main.tex                 # Documento orquestador raíz
└── output/                  # Directorio de salida para compilados PDF
```

---

## 🛠️ Compilación Rápida

Se requiere **XeLaTeX** o **LuaLaTeX** (debido al soporte de fuentes modernas vía `fontspec`):

```powershell
# En PowerShell:
New-Item -ItemType Directory -Force -Path output | Out-Null
xelatex -output-directory=output main.tex
```

```bash
# En Linux / macOS:
mkdir -p output
xelatex -output-directory=output main.tex
```

---

## 📚 Documentación Detallada

* 📖 [Guía de Inicio Rápido](docs/getting-started.md)
* 🏗️ [Arquitectura del Sistema](docs/architecture.md)
* 🎨 [Personalización de Temas y Buenas Prácticas](docs/customization.md)

