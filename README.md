# Calidad_Software_B

Estructura basada en el patrón **Microservice Chassis**
(https://microservices.io/patterns/microservice-chassis.html).

Un *chassis* es un framework base reutilizable por todos los microservicios. Contiene
la lógica de construcción y la solución a los aspectos transversales (*cross-cutting
concerns*), de modo que cada servicio se centra solo en su lógica de negocio.

```
.
├── chassis/                       # Framework base compartido por todos los servicios
│   ├── build-logic/               # Lógica reutilizable de build, test y empaquetado
│   │   ├── docker/                # Imágenes Docker base / empaquetado para producción
│   │   └── ci/                    # Pipelines de integración continua
│   ├── cross-cutting/             # Aspectos transversales
│   │   ├── security/              # Seguridad (p. ej. tokens de acceso en APIs REST)
│   │   ├── config/                # Configuración externalizada (credenciales, URLs de BD/brokers)
│   │   ├── logging/               # Configuración de logs
│   │   ├── health-check/          # Endpoint de salud para monitoreo
│   │   ├── metrics/               # Métricas
│   │   ├── tracing/               # Trazabilidad distribuida (ID único por petición)
│   │   ├── service-discovery/     # Registro y descubrimiento de servicios
│   │   └── circuit-breaker/       # Tolerancia a fallos parciales
│   ├── infrastructure/            # Código repetitivo específico de tecnología
│   │   ├── database/              # Pools de conexión, acceso a BD
│   │   ├── messaging/             # Integración con brokers de mensajería
│   │   └── http/                  # Procesamiento de peticiones HTTP
│   └── tests/
├── service-template/              # Plantilla para crear nuevos servicios usando el chassis
│   ├── src/{api,application,domain}
│   ├── config/
│   └── tests/
├── services/                      # Microservicios concretos (dependen del chassis)
│   └── service-a/
│       ├── src/{api,application,domain}
│       ├── config/
│       └── tests/
└── docs/                          # Documentación del proyecto
    └── criterios-calidad-costos/    # Criterios de calidad, defectos, costos e indicadores
```

> Los archivos `.gitkeep` solo existen para que Git versione las carpetas vacías.
