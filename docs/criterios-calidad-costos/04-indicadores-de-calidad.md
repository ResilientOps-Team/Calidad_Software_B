# 4. Indicadores de calidad y costo de la no calidad

| Indicador | Fórmula | Meta |
|-----------|---------|:----:|
| Densidad de defectos | defectos / KLOC | ≤ 2 |
| Eficiencia de eliminación (DRE) | defectos antes de E7 / defectos totales | ≥ 90 % |
| Fuga a producción | defectos en E7 / defectos totales | ≤ 10 % |
| Críticos/altos abiertos | conteo | 0 |
| Cobertura del chasis | líneas cubiertas / líneas totales | ≥ 80 % |
| % de no calidad | costo de la no calidad / costo de calidad | ≤ 30 % |
| Razón conformidad | (prevención + evaluación) / costo de la no calidad | ≥ 2 |

Se calculan al cierre de cada iteración; un indicador fuera de meta genera una acción
correctiva que vuelve al registro de defectos.
