# Changelog

## [1.0.2] - 2025-11-17
### Fixed
- Corrección completa del método **Gauss–Seidel**, que en la versión 1.0.0
  ejecutaba solo una iteración sin actualizar el potencial.  
  Ahora:
  - Itera in-place correctamente.
  - Calcula `err_max` y aplica criterio de convergencia `max|ΔV| < epsilon`.
  - Produce soluciones equivalentes a Jacobi.
- Se añadieron **tests de regresión** (`test_solver.py`).
- Validación adicional: casos triviales y campo lineal.

### Improved
- Ampliación de documentación para Jacobi y Gauss–Seidel.
- Normalización del parámetro: se acepta `"gauss-seidel"` y `"gauss_seidel"`.
- Actualización de `README.md`, `pyproject.toml` y documentación para v1.0.2.

---

## [1.0.0] - 2025-11-12
### Added
- Backend MDF con Jacobi y Gauss-Seidel.
- Cálculo de campo eléctrico E = -∇V.
- GUI Streamlit.
- Docs Sphinx en GitHub Pages.
- Pruebas unitarias.
- Empaquetado en PyPI.

### CI/CD
- Workflow de GitHub Actions para pruebas, documentación y verificación del paquete.
