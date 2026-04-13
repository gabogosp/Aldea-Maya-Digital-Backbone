# 🪰 04 — Blueprint del Proyecto Piloto: Unidad de Transformación MSN (Mosca Soldado Negro)

> *"El Land estratégico. Atacar el problema más inmediato y visible."*

---

## 1. El Estándar de Oro: Por Qué Empezamos con MSN

### 1.1 Justificación Estratégica

La Mosca Soldado Negro (Hermetia illucens) es la primera unidad productiva que se activa en Aldea Maya. No es casualidad. Es la decisión más inteligente del roadmap:

| Criterio | Por qué MSN primero |
|----------|---------------------|
| **Ciclo corto** | 14-18 días de ciclo larval vs. 255 días del cerdo. Resultados rápidos. |
| **Pivote circular** | Conecta residuos municipales con proteína animal y fertilizante. Sin MSN, no hay economía circular. |
| **Bajo riesgo** | Inversión inicial moderada, tecnología probada, mercado creciente. |
| **Alta visibilidad** | Transforma un problema visible (basura municipal) en un producto de valor. |
| **Demuestra el modelo** | Si MSN funciona orquestada por el backbone, el mismo patrón se replica en las demás unidades. |
| **No tiene sistema** | Es la oportunidad perfecta para que BeInCloud demuestre SDD desde cero. |

### 1.2 MSN en el Contexto de Aldea Maya

```mermaid
graph TD
    subgraph "ENTRADA: Residuos"
        MUN[🏘️ Residuos Municipales<br/>La Presumida, San Felipe I<br/>+ otros pueblos<br/>Meta inicial: 20 ton]
        PEC[🐷 Residuos Pecuarios<br/>Estiércol, vísceras<br/>de unidades futuras]
        AGR[🌾 Residuos Agrícolas<br/>Rastrojo, merma<br/>de cosechas]
    end

    subgraph "PROCESAMIENTO"
        SEP[🏭 Planta de Separación<br/>Orgánico / No-orgánico<br/>Control de calidad]
        BIO[🪰 Bioconversión MSN<br/>Naves de cría<br/>Ciclo: 14-18 días]
        POST[⚙️ Post-procesamiento<br/>Secado, molienda,<br/>extracción de grasa]
    end

    subgraph "SALIDA: Productos"
        HARINA[🥩 Harina de Insecto<br/>40-42% proteína<br/>Sustituto de harina<br/>de pescado]
        ACEITE[🛢️ Aceite Larval<br/>Rico en ácido láurico<br/>Para dietas animales]
        FRASS[🌱 Frass / Fertilizante<br/>Rico en NPK<br/>Regenerador de suelo]
    end

    MUN --> SEP
    PEC --> SEP
    AGR --> SEP
    SEP --> BIO
    BIO --> POST
    POST --> HARINA
    POST --> ACEITE
    POST --> FRASS

    HARINA -->|Dietas| DEST1[🐷🐔🐟🦐<br/>Unidades Pecuarias]
    ACEITE -->|Dietas| DEST1
    FRASS -->|Regeneración| DEST2[🌾 Agricultura<br/>+ Frutales]

    style BIO fill:#2d5016,stroke:#1a3a0a,color:#fff
    style HARINA fill:#8b4513,stroke:#5c2d0e,color:#fff
    style FRASS fill:#4a7c2e,stroke:#2d5016,color:#fff
```

---

## 2. Flujo de Captura: Del Residuo Municipal al Fertilizante Orgánico

### 2.1 Cadena de Valor Completa

```mermaid
sequenceDiagram
    participant GOB as 🏛️ Gobierno Municipal
    participant REC as 🚛 Recolección
    participant SEP as 🏭 Planta Separación
    participant MSN as 🪰 Unidad MSN
    participant ALM as 📦 Almacén
    participant UPP as 🐷 Unidades Pecuarias
    participant AGR as 🌾 Agricultura
    participant AUD as 📊 Auditoría (Fondo)

    GOB->>REC: Alianza: acceso a residuos de 2-3 pueblos
    REC->>SEP: 20 ton residuos orgánicos (meta inicial)
    Note over SEP: Separación orgánico/no-orgánico<br/>Control de contaminantes
    SEP->>MSN: Sustrato orgánico limpio

    Note over MSN: Ciclo larval: 14-18 días<br/>Temperatura: 27-32°C<br/>Humedad: 60-70%

    MSN->>ALM: Harina de insecto (proteína)
    MSN->>ALM: Aceite larval (grasa)
    MSN->>ALM: Frass (fertilizante)

    ALM->>UPP: Proteína + grasa para dietas
    ALM->>AGR: Fertilizante para suelo

    Note over AUD: Cada paso tiene registro<br/>en el backbone:<br/>- Toneladas recibidas<br/>- Rendimiento de conversión<br/>- Destino de cada producto<br/>- Costo por tonelada

    REC-->>AUD: Registro de recolección
    SEP-->>AUD: Registro de separación
    MSN-->>AUD: Registro de producción
    ALM-->>AUD: Registro de distribución
```

### 2.2 Métricas Clave del Flujo MSN

| Métrica | Unidad | Meta Inicial | Meta Año 1 |
|---------|--------|:------------:|:----------:|
| Residuo recolectado | Toneladas/mes | 20 | 80 |
| Tasa de conversión | % peso seco | 20-25% | 25-30% |
| Proteína producida | Toneladas/mes | 4-5 | 20-24 |
| Fertilizante producido | Toneladas/mes | 10-12 | 40-48 |
| Costo por kg de proteína | USD/kg | A establecer | -30% vs. harina de pescado |
| Empleos directos | Personas | 8-12 | 25-35 |

---

## 3. Lo Que el Backbone Orquesta en el Blueprint MSN

### 3.1 Sistema MSN: Desarrollado desde Cero con SDD

La MSN no tiene sistema existente. Es la oportunidad de demostrar el modelo SDD completo:

```mermaid
flowchart TD
    subgraph "Especificación (SDD)"
        S1[📜 Spec: Registro de<br/>lotes de residuo]
        S2[📜 Spec: Control de<br/>ciclo larval]
        S3[📜 Spec: Producción<br/>y rendimiento]
        S4[📜 Spec: Distribución<br/>a unidades destino]
        S5[📜 Spec: Reporte de<br/>auditoría MSN]
    end

    subgraph "Captura (Edge AI)"
        AV[🎙️ Asistente Virtual MSN<br/>Captura por voz:<br/>'Llegaron 3 toneladas<br/>del pueblo La Presumida']
    end

    subgraph "Sistema MSN"
        REG[📋 Registro de Lotes]
        CICLO[🔄 Control de Ciclo]
        PROD[📊 Producción]
        DIST[🚛 Distribución]
    end

    subgraph "Backbone"
        BUS[🔄 Bus de Eventos]
        SYNC[📋 Sincronía con<br/>Unidades Pecuarias]
        AUDIT[🔍 Auditoría]
    end

    S1 --> REG
    S2 --> CICLO
    S3 --> PROD
    S4 --> DIST
    S5 --> AUDIT

    AV --> REG
    REG --> CICLO
    CICLO --> PROD
    PROD --> DIST

    DIST --> BUS
    BUS --> SYNC
    BUS --> AUDIT
```

### 3.2 Eventos de Dominio MSN

| Evento | Trigger | Consumidores | Acción |
|--------|---------|--------------|--------|
| `LoteResiduoRecibido` | Llegada de residuo a planta | Separación, Auditoría | Registrar origen, peso, calidad |
| `SustratoListo` | Separación completada | Unidad MSN | Asignar a nave de cría |
| `CicloLarvalIniciado` | Larvas depositadas en sustrato | Control de ciclo | Iniciar monitoreo de T° y humedad |
| `CosechaLarvalLista` | Ciclo de 14-18 días completado | Post-procesamiento | Iniciar secado y molienda |
| `ProteínaDisponible` | Harina de insecto lista | Unidades Pecuarias, Almacén | Notificar disponibilidad para dietas |
| `FertilizanteDisponible` | Frass procesado | Agricultura, Almacén | Notificar disponibilidad para suelo |
| `RendimientoCalculado` | Fin de lote completo | Auditoría, Fondo | Reportar conversión y costos |

### 3.3 Sincronía MSN ↔ Porcinos (El Primer Flujo de Orquestación)

```mermaid
sequenceDiagram
    participant PORC as 🐷 Sistema Porcino
    participant BB as 🔄 Backbone
    participant MSN as 🪰 Sistema MSN
    participant AGRO as 🌾 Sistema Agrícola

    PORC->>BB: GestacionRegistrada(cerdas: 10, lechones_est: 120)
    BB->>BB: Calcular demanda de proteína<br/>120 lechones × dieta por etapa
    BB->>MSN: IncrementarProduccion(proteina_kg: X, fecha_limite: Y)
    MSN->>BB: ProduccionConfirmada(capacidad: OK/INSUFICIENTE)

    alt Capacidad insuficiente
        BB->>BB: Calcular residuo adicional necesario
        BB->>MSN: SolicitarIncrementoRecoleccion(ton_adicionales: Z)
        MSN->>BB: RecoleccionAjustada
    end

    BB->>AGRO: AjustarSiembra(ingredientes_complementarios: [...])
    AGRO->>BB: SiembraConfirmada

    Note over BB: Todo registrado para auditoría:<br/>- Demanda proyectada<br/>- Capacidad confirmada<br/>- Ajustes realizados<br/>- Fechas comprometidas
```

---

## 4. Plan de Ejecución: 8 Semanas con Dependencias Reales

### 4.1 Gantt del Blueprint MSN (Mosca Soldado Negro)

```mermaid
gantt
    title Blueprint MSN — Plan de 6 Semanas
    dateFormat  YYYY-MM-DD
    axisFormat  %d %b

    section 🔐 Fase 0: Acceso y Formalización
    Grupo de trabajo + NDA              :f0a, 2026-04-13, 5d
    Acceso a Drive y documentación      :f0b, after f0a, 2d
    Sesión de inmersión con aliado MSN  :milestone, f0m, after f0b, 0d

    section 📜 Fase 1: Especificación (SDD)
    Spec flujo de recolección           :f1a, after f0b, 4d
    Spec ciclo larval y bioconversión   :f1b, after f0b, 4d
    Spec producción y rendimiento       :f1c, after f1a, 3d
    Spec integración con backbone       :f1d, after f1b, 3d
    Modelo de datos audit-ready         :f1e, after f1c, 2d

    section ✅ Fase 2: Validación
    Revisión con aliado MSN             :f2a, after f1e, 3d
    Revisión con Dirección Estratégica  :f2b, after f2a, 2d
    Incorporación de feedback           :f2c, after f2b, 3d

    section 🏗️ Fase 3: Blueprint Técnico
    Arquitectura sistema MSN + stack    :f3a, after f2c, 3d
    Contratos de interfaz (APIs)        :f3b, after f3a, 3d
    Precotización detallada             :f3c, after f3b, 2d
    Presentación final a Aldea Maya     :milestone, f3m, after f3c, 0d
```

### 4.2 Dependencias Críticas y Riesgos del Timeline

| Dependencia | De quién depende | Riesgo si se retrasa | Mitigación |
|-------------|:----------------:|:--------------------:|------------|
| Firma de NDA | Legal de ambas partes | Bloquea acceso a información confidencial | Iniciar proceso legal en paralelo con grupo de trabajo |
| Acceso al Drive | Aldea Maya | Sin documentación no se puede especificar | Solicitar acceso parcial mientras se formaliza NDA |
| Sesión con aliado MSN (Mosca Soldado Negro) | Disponibilidad del líder especialista | Specs sin validación de campo | Agendar desde Semana 1 para asegurar slot |
| Revisión de Dirección Estratégica | Disponibilidad de la dirección | Blueprint sin aprobación estratégica | Enviar specs para revisión asíncrona, sesión solo para dudas |

> **Nota sobre el timeline**: Las 6 semanas contemplan 4 semanas de trabajo efectivo de BeInCloud + 2 semanas de buffer por dependencias de Aldea Maya (firmas, accesos, agendas). Si Aldea Maya se mueve rápido en la formalización, el blueprint puede estar listo antes.

### 4.3 Gates de Aprobación

El plan tiene tres gates donde se requiere aprobación explícita antes de avanzar:

```mermaid
flowchart LR
    G0[🔐 Gate 0<br/>NDA firmado +<br/>Acceso a docs<br/>Sem 1] --> G1[📜 Gate 1<br/>Specs aprobadas<br/>por aliado MSN +<br/>Dirección<br/>Sem 4] --> G2[🏗️ Gate 2<br/>Blueprint +<br/>Precotización<br/>presentados<br/>Sem 6]

    style G0 fill:#e74c3c,stroke:#c0392b,color:#fff
    style G1 fill:#f39c12,stroke:#d68910,color:#fff
    style G2 fill:#27ae60,stroke:#1e8449,color:#fff
```

---

## 5. Stack Tecnológico Propuesto

Esta sección detalla las tecnologías recomendadas para el sistema MSN (Mosca Soldado Negro). Cada elección se justifica por su impacto en el negocio, no por preferencia técnica.

### 5.1 Supuesto de Conectividad

Se asume que Aldea Maya contará con conectividad a internet como parte de su infraestructura de ciudadela (energías limpias, agua tratada, vivienda — la conectividad es un servicio más). El stack se diseña **cloud-first**.

> **Nota**: En caso de que la conectividad sea limitada o intermitente en fases tempranas de construcción, existen opciones de tolerancia a desconexión (cache local en dispositivos de captura, sincronización diferida) que se pueden incorporar sin cambiar la arquitectura base. Esto se evaluará durante el acompañamiento con Aldea Maya en las primeras semanas.

### 5.2 Arquitectura del Sistema MSN — Cloud-First

```mermaid
graph TD
    subgraph "Campo"
        AV[🎙️ Asistente Virtual MSN<br/>App móvil / tablet<br/>Captura por voz<br/>Cache local para sync]
        SENS[📡 Sensores<br/>Temperatura, humedad<br/>en naves de cría]
    end

    subgraph "Cloud — AWS (o GCP equivalente)"
        APIGW[🔌 API Gateway<br/>AWS API Gateway]
        LAMBDA[⚡ Funciones<br/>AWS Lambda / Go]
        DB[🗄️ Base de Datos<br/>Amazon RDS PostgreSQL]
        EVENTS[🔄 Bus de Eventos<br/>Amazon EventBridge]
        STEPS[📋 Orquestación<br/>AWS Step Functions]
        S3[📦 Almacenamiento<br/>Amazon S3]
        ANALYTICS[📊 Analítica<br/>Amazon Athena + QuickSight]
        IOT[📡 IoT Core<br/>AWS IoT Core]
    end

    subgraph "Observabilidad y FinOps"
        OBS[📊 CloudWatch +<br/>AWS X-Ray]
        FINOPS[💰 AWS Cost Explorer +<br/>Alertas de presupuesto]
    end

    AV --> APIGW
    SENS --> IOT
    IOT --> EVENTS
    APIGW --> LAMBDA
    LAMBDA --> DB
    LAMBDA --> EVENTS
    EVENTS --> STEPS
    STEPS --> DB
    STEPS --> S3
    DB --> ANALYTICS
    S3 --> ANALYTICS

    LAMBDA --> OBS
    STEPS --> OBS
    ANALYTICS --> FINOPS

    style EVENTS fill:#1a5276,stroke:#0e2f44,color:#fff
    style STEPS fill:#1a5276,stroke:#0e2f44,color:#fff
```

### 5.3 Justificación de Cada Componente

| Componente | Servicio AWS | Equivalente GCP | Por qué |
|------------|-------------|-----------------|---------|
| **API Gateway** | API Gateway | Cloud Endpoints | Punto de entrada único, autenticación, throttling — managed, sin servidores |
| **Lógica de negocio** | Lambda (Go) | Cloud Functions | Serverless, paga solo por uso, Go es el foco de BeInCloud |
| **Base de datos** | RDS PostgreSQL | Cloud SQL | Relacional managed, sin DBA, backups automáticos, escalable |
| **Bus de eventos** | EventBridge | Pub/Sub | Desacopla servicios, enruta eventos entre dominios, managed |
| **Orquestación** | Step Functions | Workflows | Sagas multi-paso (recolección → bioconversión → distribución), compensación automática |
| **Almacenamiento** | S3 | Cloud Storage | Documentos, specs, respaldos, datos históricos — costo mínimo |
| **Analítica / Reportes** | Athena + QuickSight | BigQuery + Looker | Consultas SQL sobre datos en S3, dashboards de auditoría — sin infraestructura |
| **IoT (sensores)** | IoT Core | IoT Core | Ingesta de datos de sensores de naves de cría — managed, escalable |
| **Observabilidad** | CloudWatch + X-Ray | Cloud Monitoring | Logs, métricas, traces — visibilidad total sin herramientas externas |
| **FinOps** | Cost Explorer + Budgets | Billing + Budgets | Control de costos en tiempo real, alertas automáticas |

### 5.4 Principios de Selección

| Principio | Aplicación |
|-----------|------------|
| **Managed-first** | Cero servidores que mantener. Todo serverless o managed. Menos ops, más negocio. |
| **Cloud-first** | Se asume conectividad. El cloud es el centro, no el edge. |
| **FinOps nativo** | Cada servicio tiene costo predecible y medible. Alertas desde el día 0. |
| **Serverless donde sea posible** | Lambda + Step Functions + EventBridge = paga solo lo que usas |
| **Sin vendor lock-in en la lógica** | La lógica de negocio está en las specs (SDD), no en servicios propietarios. Migrar de AWS a GCP es cambiar infraestructura, no reescribir negocio. |

> **Regla de negocio**: Ninguna tecnología se selecciona por tendencia o preferencia. Cada componente tiene una justificación de negocio. Si no la tiene, no entra.

→ Ver detalle de capacidades técnicas de BeInCloud: [`assets/beincloud-profile.md`](./assets/beincloud-profile.md)

---

## 6. Gobernanza y Transparencia del Piloto

### 6.1 Reporte al Fondo — Piloto MSN (Mosca Soldado Negro)

El piloto MSN genera el primer reporte de auditoría real del backbone:

```mermaid
pie title "Distribución de Inversión — Piloto MSN"
    "Especificación SDD" : 25
    "Infraestructura física" : 35
    "Sistema digital (desarrollo)" : 20
    "Asistente virtual (Edge AI)" : 10
    "Capacitación de aldeanos" : 10
```

### 6.2 KPIs del Piloto

| KPI | Definición | Frecuencia |
|-----|------------|:----------:|
| Toneladas procesadas | Residuo convertido en producto | Semanal |
| Costo por kg de proteína | Competitividad vs. mercado | Mensual |
| Tasa de conversión | Eficiencia del proceso biológico | Por lote |
| Empleos generados | Impacto social directo | Mensual |
| Trazabilidad | % de flujos con registro completo | Mensual |
| Tiempo de reporte | Días entre cierre de mes y reporte listo | Mensual |

> El piloto MSN (Mosca Soldado Negro) es la prueba de concepto del modelo completo. Si funciona aquí — con trazabilidad, auditoría y orquestación — el mismo patrón se aplica a las 20+ unidades restantes.

---

## 7. Criterios de Éxito del Blueprint

- [ ] El aliado MSN puede leer la spec y confirmar que refleja su operación real
- [ ] El blueprint permite entender el flujo de inversión sin conocimiento técnico
- [ ] Cualquier despacho de TI puede tomar el blueprint e implementar sin depender de BeInCloud
- [ ] Los contratos de interfaz (APIs) permiten integración futura con porcinos, agricultura, etc.
- [ ] Las métricas de auditoría están definidas y son medibles desde el día 1
- [ ] El stack tecnológico está justificado por negocio, no por preferencia técnica

---

## Navegación

| Anterior | Siguiente |
|:--------:|:---------:|
| [← 03 — SDD + IA](./03-sdd-methodology.md) | [05 — Propuesta de Socio →](./05-roadmap-economics.md) |

→ Para entender la sincronía biológica que MSN habilita: [`01-business-alignment.md`](./01-business-alignment.md)
→ Para ver la arquitectura de datos donde MSN se integra: [`02-architecture-ecosystem.md`](./02-architecture-ecosystem.md)
→ Para conocer a BeInCloud: [`assets/beincloud-profile.md`](./assets/beincloud-profile.md)

---

*Documento vivo. Versión 0.2 — Sprint 0, Abril 2026*
*Be In Cloud Group LLC — Ingeniería Cloud con Visión Financiera*
