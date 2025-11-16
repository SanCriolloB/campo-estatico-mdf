# Changelog

## [1.0.2] - 2025-11-15
### Fixed
- Corrección completa del método **Gauss–Seidel** en `campo_estatico_mdf/solver.py`,
  que en la versión 1.0.0 podía ejecutar solo una iteración sin actualizar
  correctamente el potencial.  
  Ahora:
  - Itera in-place correctamente.
  - Calcula `err_max` y aplica el criterio de convergencia `max|ΔV| < epsilon`.
  - Produce soluciones numéricas equivalentes a Jacobi (dentro de una tolerancia razonable).
- Se añadieron **tests de regresión** en `tests/test_solver.py` para:
  - Verificar que Gauss–Seidel no converge en 1 sola iteración para casos no triviales.
  - Comparar la solución Gauss–Seidel con Jacobi en problemas sencillos.

### Improved
- Ampliación y aclaración de la documentación (Sphinx) sobre:
  - Diferencias entre **Jacobi** y **Gauss–Seidel**.
  - Criterio de convergencia basado en `max|ΔV|`.
- Normalización del parámetro `method` en `LaplaceSolver2D`:
  - Se aceptan tanto `"gauss_seidel"` como `"gauss-seidel"` (se normaliza internamente).
- Actualización de la **GUI de Streamlit**:
  - Parámetros controlados desde la barra lateral (N, ε, `max_iter`, método, contornos).
  - Visualización del potencial `V(x, y)` como heatmap.
  - Visualización del campo eléctrico `E(x, y)` con quiver y submuestreo configurable.
  - Página específica de **Documentación** (`app_streamlit/pages/1_Documentacion.py`)
    con enlace a GitHub Pages y soporte de `DOCS_URL` para despliegues en la nube.

### Changed
- Actualización de versión en:
  - `pyproject.toml`
  - `README.md`
  - Documentación Sphinx (`conf.py`, `index.rst`, `tutorial.rst`, `api_reference.rst`).

---

## [1.0.0] - 2025-11-12
### Added
- Backend MDF con métodos iterativos **Jacobi** y **Gauss–Seidel** para la ecuación de Laplace en 2D.
- Cálculo de campo eléctrico `E = -∇V`.
- GUI Streamlit (Simulación + Documentación básica).
- Documentación inicial con Sphinx, publicada en GitHub Pages.
- Pruebas unitarias para:
  - Caso trivial.
  - Convergencia.
  - Campo eléctrico lineal.
- Empaquetado y publicación inicial en PyPI.

### CI/CD
- Workflow de GitHub Actions para:
  - Ejecutar tests.
  - Construir documentación.
  - Verificar la distribución antes de publicar.
