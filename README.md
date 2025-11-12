# campo-estatico-mdf

Backend (método de diferencias finitas) para resolver el potencial electrostático 2D (ecuación de Laplace),
con métodos Jacobi y Gauss-Seidel, y cálculo del campo eléctrico **E = -∇V**.

## Fase 1 (núcleo)
- Clase `LaplaceSolver2D`
- Discretización N×N con contornos Dirichlet
- Solvers Jacobi y Gauss-Seidel
- Cálculo de campo eléctrico (Ex, Ey)
- Ejemplo mínimo en `examples/placa_basica.py`
