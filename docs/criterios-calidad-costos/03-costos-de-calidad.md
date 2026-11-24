# 3. Costos de prevención, evaluación y fallos

```
Costo de Calidad = Prevención + Evaluación + Fallos internos + Fallos externos
Costo de la No Calidad = Fallos internos + Fallos externos
```

| Categoría | Ejemplos en el proyecto |
|-----------|-------------------------|
| Prevención | Requisitos, diseño del chasis, estándares en CI |
| Evaluación | Revisiones de código, pruebas, pipeline de CI |
| Fallos internos | Retrabajo y re-pruebas antes de producción (E1–E6) |
| Fallos externos | Incidentes, hotfix, redespliegue de servicios, inactividad (E7) |

`costo = horas × costo_hora` (registrar en [plantillas/costos-calidad.csv](plantillas/costos-calidad.csv)).

Un defecto cuesta más cuanto más tarde se detecta (referencia orientativa: 1× en requisitos,
10× en pruebas, 50–100× en producción). En el chasis, además, se multiplica por los
servicios que hay que redesplegar.
