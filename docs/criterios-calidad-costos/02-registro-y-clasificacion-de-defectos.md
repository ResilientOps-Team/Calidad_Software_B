# 2. Registro y clasificación de defectos

Cada defecto se registra en [plantillas/registro-defectos.csv](plantillas/registro-defectos.csv)
indicando componente, etapa de origen y de detección, severidad, alcance y requisito afectado.

## Etapas

| E1 | E2 | E3 | E4 | E5 | E6 | E7 |
|----|----|----|----|----|----|----|
| Requisitos | Diseño | Codificación | Pruebas unitarias | Integración / CI | Despliegue | Producción |

## Impacto

| Severidad | Peso | Criterio |
|-----------|:----:|----------|
| Crítica | 10 | Brecha de seguridad, pérdida de datos o caída total |
| Alta | 5 | Función principal no funciona |
| Media | 2 | Falla parcial con alternativa |
| Baja | 1 | Cosmético |

| Alcance | Factor |
|---------|:------:|
| Chasis (afecta a todos los servicios) | ×3 |
| Plantilla | ×2 |
| Un servicio | ×1 |

`puntaje_impacto = peso_severidad × factor_alcance` → P1 si es Crítica o puntaje ≥ 15.
