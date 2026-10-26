# Guía de Personalización y Buenas Prácticas — BERF

Esta guía detalla cómo personalizar el aspecto visual de tu currículum y cómo redactar viñetas técnicas de alto impacto para roles de ingeniería backend.

---

## 1. Personalización de Tokens de Diseño

### Tokens de Color (`config/colors.tex`)
El sistema utiliza una paleta base y tokens semánticos. Para cambiar el color de acento principal (por ejemplo, cambiar de azul a esmeralda o púrpura), modifica el mapeo semántico:

```latex
% Cambiar el acento por defecto:
\colorlet{cvAccent}{green600}  % o definecolor{customColor}{HTML}{7C3AED}
\colorlet{cvLink}{green600}
```

Tokens principales:
* **`cvPrimary`**: Color del nombre, títulos de experiencia y nombres de proyectos (por defecto: `slate900` / `#0F172A`).
* **`cvSecondary`**: Color del texto base, empresas y roles (por defecto: `slate700` / `#334155`).
* **`cvAccent`**: Color de líneas divisorias, viñetas, iconos y enlaces (por defecto: `blue600` / `#2563EB`).
* **`cvMuted`**: Fechas, ubicaciones y separadores sutiles (por defecto: `slate500` / `#64748B`).
* **`cvBackground`**: Fondo de los badges técnicos `\cvTag` (por defecto: `gray100` / `#F8FAFC`).

---

## 2. Ajuste de Tipografía (`config/fonts.tex`)

Si deseas cambiar las familias tipográficas, puedes configurar cualquier fuente de tu sistema operativo mediante `fontspec`:

```latex
% Ejemplo con fuentes comunes de Windows/Linux:
\setmainfont{Inter}         % o "Roboto", "Liberation Sans", "Helvetica Neue"
\setmonofont{Fira Code}     % o "JetBrains Mono", "Consolas"
```

Los tamaños de fuente están desacoplados mediante tokens:
* `\cvNameSize`: Tamaño del nombre (por defecto: `24pt`).
* `\cvTitleSize`: Tamaño del headline profesional (por defecto: `13pt`).
* `\cvSectionSize`: Tamaño de títulos de sección (por defecto: `11pt`).
* `\cvBodySize`: Tamaño del texto general (por defecto: `10pt`).

---

## 3. Ajuste de Márgenes y Estrategia de 1 Página

Si necesitas ajustar el contenido para que encaje estrictamente en **1 página** (o en **2 páginas exactas**), puedes ajustar los tokens de separación en [`config/layout.tex`](file:///c:/Users/Prueba/Documents/Dev/BERF/config/layout.tex):

### Reducir márgenes de página
```latex
\geometry{
    top=1.2cm,
    bottom=1.2cm,
    left=1.4cm,
    right=1.4cm
}
```

### Compactar espaciados verticales
```latex
\setlength{\cvSpacingXS}{1.5mm}
\setlength{\cvSpacingSM}{2.5mm}
\setlength{\cvSpacingMD}{4mm}
\setlength{\cvSpacingLG}{5mm}
\setlength{\cvSpacingXL}{8mm}
```

---

## 4. Redacción de Viñetas de Ingeniería Backend (Fórmula Google XYZ)

Para maximizar el impacto ante reclutadores técnicos y hiring managers, cada viñeta en `sections/experience.tex` y `sections/projects.tex` debe seguir la estructura:

$$\text{"Logré } [X] \text{ medido por } [Y] \text{ mediante } [Z]\text{"}$$

### Comparativa de Redacción:

| ❌ Redacción Pasiva / Débil | ✅ Redacción Orientada a Métricas de Backend (BERF) |
|---|---|
| *"Trabajé en el desarrollo de APIs para procesamiento de pagos con Go."* | *"Diseñé y desplegué una arquitectura orientada a eventos con **Go** y **Kafka**, procesando más de **15,000 TPS** con latencias p99 inferiores a **45 ms**."* |
| *"Mejoré la base de datos de la empresa y arreglé consultas lentas."* | *"Optimicé índices y planes de ejecución en **PostgreSQL** y capa de cache en **Redis**, reduciendo el consumo de CPU en base de datos en un **38\%**."* |
| *"Ayudé a migrar servidores a la nube con Docker."* | *"Migré servicios monolíticos a clústeres en **Kubernetes (EKS)** con Terraform, reduciendo el tiempo de despliegue de 45 a **4 minutos** en pipelines de CI/CD."* |

