# 🏗️ 02 — Arquitectura de Datos y Transparencia

> *"Dar seguridad técnica al fondo de inversión estadounidense — sin hablar de tecnología."*

---

## 1. Digital Backbone: Motor de Orquestación

### 1.1 El Problema Real

Aldea Maya arranca con 20+ unidades productivas, 22 aliados especializados, múltiples despachos de TI y un fondo de inversión que exige auditorías mensuales. Sin un backbone:

- Cada unidad productiva opera en su propio silo
- La información viaja por WhatsApp y se pierde
- Los reportes al fondo se construyen manualmente y llegan tarde
- Escalar a franquicia es imposible porque no hay estándares
- La coordinación entre despachos de TI representa el reto operativo más complejo del proyecto

### 1.2 Arquitectura de Orquestación

```mermaid
graph TB
    subgraph "CAPA 1: PERCEPCIÓN — El Territorio Habla"
        AV1[🎙️ Asistente Virtual<br/>Gestación Porcina]
        AV2[🎙️ Asistente Virtual<br/>MSN]
        AV3[🎙️ Asistente Virtual<br/>Agricultura]
        AV4[🎙️ Asistente Virtual<br/>Acuacultura]
        AVN[🎙️ ... 15+ Asistentes<br/>Virtuales en Piso]
        SENS[📡 Sensores IoT<br/>Suelo, Agua, Clima]
    end

    subgraph "CAPA 2: SISTEMAS DE UNIDAD — Cada Sector Tiene el Suyo"
        S1[💻 Sistema Porcino<br/>Específico del sector]
        S2[💻 Sistema MSN<br/>Desarrollado a medida]
        S3[💻 Sistema Agrícola<br/>Específico del sector]
        S4[💻 Sistema Acuícola<br/>Específico del sector]
        SN[💻 ... Sistemas por<br/>Unidad Productiva]
    end

    subgraph "CAPA 3: BACKBONE — Orquestación Central"
        BUS[🔄 Bus de Eventos Territorial]
        SAGA[📋 Motor de Sagas<br/>Sincronía entre unidades]
        CONT[📜 Contratos de Interfaz<br/>Versionados]
    end

    subgraph "CAPA 4: INTELIGENCIA Y REPORTE"
        DASH[📊 Dashboard Territorial]
        AUDIT[🔍 Motor de Auditoría<br/>Audit-Ready]
        PRED[🧠 Modelos Predictivos<br/>Demanda, Clima, Producción]
    end

    subgraph "CAPA 5: STAKEHOLDERS"
        FONDO[💰 Fondo de Inversión<br/>Reportes mensuales]
        JC[👤 Dirección Estratégica<br/>Aldea Maya]
        ALIADOS[🤝 22 Aliados<br/>Líderes de Unidad]
    end

    AV1 --> S1
    AV2 --> S2
    AV3 --> S3
    AV4 --> S4
    AVN --> SN
    SENS --> BUS

    S1 --> BUS
    S2 --> BUS
    S3 --> BUS
    S4 --> BUS
    SN --> BUS

    BUS --> SAGA
    SAGA --> CONT
    CONT --> DASH
    CONT --> AUDIT
    CONT --> PRED

    DASH --> FONDO
    DASH --> JC
    DASH --> ALIADOS
    AUDIT --> FONDO

    style BUS fill:#1a5276,stroke:#0e2f44,color:#fff
    style SAGA fill:#1a5276,stroke:#0e2f44,color:#fff
    style CONT fill:#1a5276,stroke:#0e2f44,color:#fff
```

### 1.3 Principio de Interfaz, No de Reemplazo

El backbone **no reemplaza** los sistemas de cada unidad productiva. Los **conecta**.

| Escenario | Acción del Backbone |
|-----------|---------------------|
| La unidad ya tiene sistema (ej: porcinos) | Crear interfaz con el sistema existente |
| La unidad no tiene sistema (ej: MSN) | Especificar y desarrollar el sistema |
| El sistema es Excel o papel | Asistente virtual captura y alimenta un sistema nuevo |
| Múltiples despachos de TI trabajan en paralelo | El backbone define los contratos de interfaz entre ellos |

> **Regla de negocio**: El asistente virtual alimenta automáticamente el sistema de la unidad productiva. El aldeano no captura datos dos veces. Nunca.

---

## 2. Patrimonio de Datos: Audit-Ready desde el Día 0

### 2.1 El Fondo Exige Auditorías Mensuales

Aldea Maya opera bajo un régimen de auditorías mensuales exigido por el fondo de inversión. El backbone está diseñado para que cada dato sea auditable desde su origen.

### 2.2 Estructura de Datos Territorial

```mermaid
erDiagram
    UNIDAD_PRODUCTIVA ||--o{ CICLO_PRODUCCION : ejecuta
    UNIDAD_PRODUCTIVA ||--o{ ALIADO : "liderada por"
    UNIDAD_PRODUCTIVA ||--o{ ALDEANO : emplea

    CICLO_PRODUCCION ||--o{ EVENTO_OPERATIVO : genera
    CICLO_PRODUCCION ||--o{ CONSUMO_INSUMO : requiere
    CICLO_PRODUCCION ||--o{ PRODUCCION_OUTPUT : produce

    EVENTO_OPERATIVO ||--|| REGISTRO_AUDITORIA : "trazable en"

    CONSUMO_INSUMO }o--|| FLUJO_FINANCIERO : "tiene costo"
    PRODUCCION_OUTPUT }o--|| FLUJO_FINANCIERO : "genera ingreso"

    FLUJO_FINANCIERO ||--|| REGISTRO_AUDITORIA : "trazable en"
    FLUJO_FINANCIERO }o--|| REPORTE_FONDO : "agregado en"

    ALDEANO ||--o{ INDICADOR_SOCIAL : "medido por"
    INDICADOR_SOCIAL ||--|| REPORTE_FONDO : "reportado en"

    UNIDAD_PRODUCTIVA {
        string id
        string nombre
        string tipo
        string aliado_lider
        string fase_implementacion
    }

    CICLO_PRODUCCION {
        string id
        date fecha_inicio
        date fecha_fin_estimada
        string estado
        float rendimiento_esperado
    }

    REGISTRO_AUDITORIA {
        string id
        datetime timestamp
        string origen
        string tipo_evento
        string usuario
        string hash_integridad
    }

    REPORTE_FONDO {
        string id
        string periodo
        date fecha_generacion
        string estado_aprobacion
    }
```

### 2.3 Cadena de Custodia del Dato

Cada dato que entra al backbone tiene una cadena de custodia inmutable:

```mermaid
flowchart LR
    subgraph "1. ORIGEN"
        O1[👷 Aldeano]
        O2[📡 Sensor IoT]
        O3[💻 Sistema de Unidad]
    end

    subgraph "2. CAPTURA"
        CAP[🎙️ Asistente Virtual<br/>o ingesta directa]
    end

    subgraph "3. VALIDACIÓN"
        VAL[⚙️ Reglas de negocio<br/>del dominio]
    end

    subgraph "4. ALMACENAMIENTO"
        ALM[🔒 Timestamp +<br/>Hash de integridad]
    end

    subgraph "5. AGREGACIÓN"
        AGR[📊 Dashboard<br/>Territorial]
    end

    subgraph "6. REPORTE"
        REP[📋 Formato exigido<br/>por el fondo]
    end

    O1 --> CAP
    O2 --> CAP
    O3 --> CAP
    CAP --> VAL
    VAL --> ALM
    ALM --> AGR
    AGR --> REP

    style ALM fill:#1a5276,stroke:#0e2f44,color:#fff
    style REP fill:#1a5276,stroke:#0e2f44,color:#fff
```

Cada eslabón de esta cadena es inmutable y auditable. Si un dato llega al reporte del fondo, se puede rastrear hasta el aldeano o sensor que lo originó.

### 2.4 Clasificación de Datos para Auditoría

| Categoría | Ejemplos | Retención | Acceso |
|-----------|----------|-----------|--------|
| **Operativos** | Gestación registrada, cosecha completada, residuo procesado | 7 años | Aliado + Dirección |
| **Financieros** | Costo de insumo, ingreso por venta, flujo de inversión | 10 años | Dirección + Fondo |
| **Sociales** | Empleo generado, asistencia escolar, capacitación | 7 años | Dirección + Fondo |
| **Ambientales** | Calidad de suelo, emisiones evitadas, agua reutilizada | Permanente | Público (anonimizado) |

> **Regla de gobernanza**: Todo dato financiero tiene trazabilidad completa desde el evento operativo que lo originó hasta el reporte al fondo. Sin excepciones. Sin atajos.

---

## 3. FinOps desde el Día 0

### 3.1 El Problema de Costos en Proyectos de Esta Escala

Un proyecto de 5-6 años con 20+ unidades productivas puede generar costos de infraestructura digital descontrolados si no se gobiernan desde el inicio.

### 3.2 Estrategia de Control de Costos

```mermaid
graph TD
    subgraph "Principio: Compute donde tiene sentido"
        EDGE[🏭 Edge Computing<br/>En cada zona productiva<br/>Procesamiento local<br/>Funciona sin internet]
        CENTRAL[🖥️ Edge Central<br/>On-premise en Aldea Maya<br/>Orquestación, dashboards<br/>Bus de eventos]
        NUBE[☁️ Nube Soberana<br/>Región México<br/>Solo lo que requiere<br/>escala elástica]
    end

    EDGE -->|Datos agregados| CENTRAL
    CENTRAL -->|Respaldos + ML| NUBE

    subgraph "Reglas FinOps"
        R1[📏 Costo por hectárea<br/>instrumentada: decreciente]
        R2[📏 Costo de nube < 15%<br/>del costo total de TI]
        R3[📏 ROI de cada sensor<br/>justificado por caso de uso]
        R4[📏 Revisión mensual<br/>de consumo cloud]
    end
```

### 3.3 Modelo de Costos por Capa

| Capa | Tipo de Costo | Estrategia |
|------|---------------|------------|
| **Edge Zonal** | CapEx (hardware) + OpEx mínimo | Dispositivos robustos, bajo consumo, larga vida útil |
| **Edge Central** | CapEx (servidor on-premise) | Amortizable, sin costos recurrentes de nube |
| **Nube Soberana** | OpEx (pay-as-you-go) | Solo para ML, respaldos y picos de demanda |
| **Conectividad** | OpEx | Red mesh entre zonas, satelital como respaldo |
| **Asistentes Virtuales** | OpEx (modelos de IA) | Modelos edge-first, nube solo para entrenamiento |

### 3.4 Transparencia de Costos para el Fondo

El dashboard del fondo incluye una sección de FinOps que muestra:

- Costo total de TI por mes
- Costo por unidad productiva instrumentada
- Costo por hectárea gestionada
- Tendencia de costo (debe ser decreciente por unidad)
- Comparativa: costo de TI vs. valor habilitado

> **Regla de negocio**: Si el costo de TI por hectárea no decrece trimestre a trimestre, hay un problema de arquitectura que BeInCloud debe resolver. Sin excusas.

---

## 4. Interoperabilidad entre Despachos de TI

### 4.1 El Reto de la Coordinación

Aldea Maya enfrenta el reto de coordinar múltiples despachos de TI especializados trabajando en paralelo — posiblemente la dimensión más compleja de todo el proyecto. El backbone resuelve esto con **contratos de interfaz**:

```mermaid
sequenceDiagram
    participant D1 as Despacho IA<br/>(Asistentes Virtuales)
    participant BB as Digital Backbone<br/>(BeInCloud)
    participant D2 as Despacho Software<br/>(Sistemas de Unidad)
    participant D3 as Despacho Contable<br/>(Fiscal/Financiero)

    BB->>D1: Contrato: Formato de datos de captura
    BB->>D2: Contrato: API de sistema de unidad
    BB->>D3: Contrato: Estructura de reporte financiero

    D1->>BB: Dato capturado (formato estándar)
    BB->>D2: Evento de dominio (contrato versionado)
    D2->>BB: Confirmación de procesamiento
    BB->>D3: Flujo financiero agregado
    D3->>BB: Reporte validado

    Note over BB: El backbone es el árbitro.<br/>Define contratos, no implementaciones.
```

### 4.2 Estándares de Interoperabilidad

| Estándar | Propósito | Beneficio |
|----------|-----------|-----------|
| Eventos CloudEvents v1.0 | Formato de eventos entre sistemas | Cualquier despacho puede consumir/producir |
| APIs OpenAPI 3.1 | Contratos de interfaz de sistemas | Documentación automática, validación |
| Datos GeoJSON | Información geoespacial del territorio | Mapas, zonas, parcelas estandarizadas |
| OpenTelemetry | Métricas y observabilidad | Visibilidad unificada de todos los sistemas |

> **Regla de gobernanza (SDD)**: Cada contrato de interfaz se especifica ANTES de que cualquier despacho escriba código. La especificación es el activo. El código es la implementación.

---

*Documento vivo. Versión 0.1 — Sprint 0, Abril 2026*
*BeInCloud — Arquitectos de Sistemas Nerviosos Territoriales*
