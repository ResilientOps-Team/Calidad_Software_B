# 1. Criterios y requisitos de calidad

Modelo de referencia: **ISO/IEC 25010**. Criterios priorizados y componente del chasis que los soporta:

| Criterio | Componentes del chasis |
|----------|------------------------|
| Fiabilidad | `circuit-breaker`, `health-check`, `service-discovery` |
| Seguridad | `security`, `config` |
| Mantenibilidad | `logging`, `tracing`, `service-template/`, `build-logic/ci` |
| Eficiencia | `metrics`, `infrastructure/database` |
| Portabilidad | `build-logic/docker`, `config` |

## Requisitos

| ID | Requisito | Umbral |
|----|-----------|--------|
| RNF-FIA-01 | Cada servicio expone `GET /health` | 200 en < 200 ms |
| RNF-FIA-02 | Llamadas entre servicios con circuit breaker | Abre tras 5 fallos |
| RNF-SEG-01 | APIs no públicas exigen token | 100 % de endpoints |
| RNF-SEG-02 | Sin secretos en el código | 0 hallazgos |
| RNF-MAN-01 | Cobertura de pruebas del chasis | ≥ 80 % |
| RNF-MAN-02 | Cobertura de pruebas por servicio | ≥ 70 % |
| RNF-MAN-03 | `trace_id` propagado en cada petición | 100 % de logs |
| RNF-EFI-01 | Latencia de APIs | p95 ≤ 300 ms |

Los umbrales son propuestas iniciales y se revisan cada iteración.
