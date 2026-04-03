# Plantilla de Reporte — ITESM

Plantilla de LaTeX para reportes académicos del Tecnológico de Monterrey. Incluye portada institucional, ambientes de teoremas con color, macros matemáticas y formato profesional listo para usar.

## Vista previa

La plantilla genera un reporte con:
- Portada con logo institucional, título, autor, matrícula, curso y profesor
- Resumen (abstract) en español
- Tabla de contenidos
- Ambientes de teoremas, definiciones, ejemplos y observaciones con cajas de color
- Referencias bibliográficas

## Requisitos

- Distribución de TeX con `pdflatex` (e.g., TeX Live, MiKTeX, MacTeX)
- `latexmk` (opcional, incluido en la mayoría de distribuciones)

## Uso

### Compilar

```bash
latexmk -pdf report.tex
```

O manualmente:

```bash
pdflatex report.tex
pdflatex report.tex  # segunda pasada para referencias y TOC
```

### Personalizar

Edita la sección **DATOS DEL REPORTE** en `report.tex` (línea ~260):

```latex
\newcommand{\titulo}{TITULO DEL REPORTE}
\newcommand{\subtitulo}{Escuela de Ingenieria y Ciencias}
\newcommand{\autor}{Nombre del Autor}
\newcommand{\matricula}{A00000000}
\newcommand{\curso}{Clave y Nombre del Curso}
\newcommand{\profesor}{Nombre del Profesor}
\newcommand{\campus}{Campus}
\newcommand{\fecha}{\today}
```

## Ambientes disponibles

| Ambiente | Uso | Color |
|---|---|---|
| `teorema` | Teoremas | Teal |
| `lema` | Lemas | Teal |
| `proposicion` | Proposiciones | Teal |
| `corolario` | Corolarios | Teal |
| `definicion` | Definiciones | MidnightBlue |
| `ejemplo` | Ejemplos | DarkSlateGray |
| `observacion` | Observaciones | DimGray (barra lateral) |
| `ejercicio` | Ejercicios | DimGray (barra lateral) |

Sintaxis:

```latex
\begin{teorema}{Título del teorema}{etiqueta}
    Contenido del teorema.
\end{teorema}
```

Referencia cruzada con `\cref{thm:etiqueta}`.

## Macros matemáticas

- Conjuntos: `\N`, `\Z`, `\Q`, `\R`, `\C`
- Delimitadores: `\abs{x}`, `\norm{x}`, `\inner{x,y}`, `\ceil{x}`, `\floor{x}` (usar `\abs*{x}` para auto-escalado)
- Operadores en español: `\sen`, `\tg`
- Atajos: `\eps` (varepsilon), `\del` (delta)

## Estructura de archivos

```
report.tex   — documento principal (plantilla + contenido de ejemplo)
logo.png     — logo del ITESM para la portada
.gitignore   — ignora archivos auxiliares de LaTeX
```

## Licencia

Uso libre para estudiantes del ITESM.
