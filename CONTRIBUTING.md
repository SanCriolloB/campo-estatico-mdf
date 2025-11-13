# Guía de Contribución — campo-estatico-mdf

Gracias por tu interés en colaborar con el proyecto **campo-estatico-mdf**.  
Este documento define las normas de contribución, ramas, commits y flujo de trabajo.

---

## Flujo de trabajo de desarrollo

El repositorio sigue la siguiente jerarquía de ramas:

```
main ← develop ← feat/*  o  fix/*
```

- **main** → versiones estables (liberadas y publicadas).  
- **develop** → rama de integración y pruebas.  
- **feat/** → nuevas funcionalidades (feature).  
- **fix/** → correcciones de errores.

---

## Proceso de contribución

1. Crea un **Issue** describiendo la mejora o bug (usa las plantillas del repositorio).  
2. Crea una nueva rama desde `develop`:
   ```bash
   git checkout develop
   git pull origin develop
   git checkout -b feat/<descripcion-corta>
   ```
3. Realiza commits atómicos y descriptivos.  
4. Ejecuta pruebas y verifica que todo funcione:
   ```bash
   pytest
   python -m sphinx -T -E -b html docs/source docs/_build/html
   ```
5. Abre un **Pull Request** hacia `develop`:
   - Título: `[RFx/RNFy] <resumen de la contribución>`
   - Incluye: descripción, RF/RNF asociado y `Closes #<issue-id>`.
6. Espera revisión y aprobación (mínimo 1 aprobación).  
7. Una vez aprobado, se realiza *Squash & merge* hacia `develop`.

---

## Reglas de estilo de commits

- `feat:` → nueva funcionalidad.  
- `fix:` → corrección de bug.  
- `docs:` → cambios en documentación.  
- `test:` → nuevos tests o actualizaciones.  
- `build:` → cambios en empaquetado o CI/CD.  
- `chore:` → tareas de mantenimiento.

Ejemplos:
```
feat(gui): agrega visualización del campo eléctrico
fix(solver): corrige cálculo del gradiente en frontera
docs(sphinx): actualiza teoría del método de Gauss-Seidel
```

---

## Pruebas locales

Antes de subir un PR, asegúrate de que todo pase correctamente:

```bash
pytest
python -m build
python -m sphinx -T -E -b html docs/source docs/_build/html
```

Puedes ejecutar la aplicación GUI:
```bash
streamlit run app_streamlit/streamlit_app.py
```

---

## Estructura del proyecto

```
campo_estatico_mdf/
├─ campo_estatico_mdf/        # Código fuente (solver, utilidades)
├─ app_streamlit/             # Interfaz gráfica (GUI)
├─ docs/                      # Documentación (Sphinx)
├─ tests/                     # Casos de prueba (pytest)
├─ examples/                  # Ejemplos de uso
├─ pyproject.toml             # Configuración PyPI
├─ .github/workflows/ci.yml   # Pipeline CI/CD
└─ README.md, LICENSE, CHANGELOG.md
```

---

## Licencia

Este proyecto está bajo la licencia MIT.  
Consulta el archivo `LICENSE` para más detalles.

---

**Autores:** Santiago Criollo & Daniel Ramirez  
**Repositorio:** [https://github.com/SanCriolloB/campo-estatico-mdf](https://github.com/SanCriolloB/campo-estatico-mdf)
