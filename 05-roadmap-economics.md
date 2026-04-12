# 📈 05 — Estrategia de Expansión y Modelo de Socio

> *"No es un año, no son dos, ni son tres. Estamos hablando de cinco, seis años."*

---

## 1. Fases de Implementación: Alineadas con la Construcción Física

El backbone digital no tiene roadmap propio. **Su roadmap es el de Aldea Maya.** Cada fase digital se activa cuando la fase física la necesita — ni antes (desperdicio) ni después (caos).

### 1.1 Roadmap Integrado: Físico + Digital

```mermaid
gantt
    title Roadmap Aldea Maya — Integración Física + Digital (5-6 años)
    dateFormat  YYYY-MM
    axisFormat  %Y

    section 🏗️ Fase 1: Diseño y Estructuración
    Estructuración legal y financiera       :f1a, 2026-01, 6M
    Diseño de ciudadela y masterplan        :f1b, 2026-01, 6M
    Sprint 0: Backbone (Gobernanza + Arq)   :milestone, 2026-04, 0d
    Blueprint MSN (Piloto)                  :f1c, 2026-04, 1M

    section 🌱 Fase 2: Establecimiento Productivo Inicial
    Construcción Unidad MSN                 :f2a, 2026-07, 4M
    Sistema MSN + Backbone v1               :f2b, 2026-07, 4M
    Inicio recolección residuos             :f2c, 2026-09, 2M
    Construcción Unidad Porcina (100 vientres) :f2d, 2026-09, 6M
    Sistema Porcino + Orquestación MSN↔Cerdo :f2e, 2026-11, 4M
    Inicio agricultura (primeros ciclos)    :f2f, 2027-01, 3M
    Sistema Agrícola + Sincronía            :f2g, 2027-01, 3M

    section 🏭 Fase 3: Consolidación Agroindustrial
    Unidades Avícola + Acuícola             :f3a, 2027-04, 8M
    Sistemas + Orquestación completa        :f3b, 2027-06, 6M
    Invernaderos + Hidroponía               :f3c, 2027-06, 6M
    Clúster social (250 casas)              :f3d, 2027-06, 12M
    Rastros y empaque                       :f3e, 2028-01, 6M
    Cadena comercial regional               :f3f, 2028-01, 6M

    section 🔄 Fase 4: Optimización y Circularidad Total
    Circularidad completa de residuos       :f4a, 2028-06, 6M
    Modelos predictivos (ML)                :f4b, 2028-06, 6M
    Certificaciones (carbono, orgánico)     :f4c, 2028-06, 6M
    Canal premium Majahual (Royal Caribbean):f4d, 2028-06, 6M

    section 🌎 Fase 5: Expansión y Replicación
    Estandarización de franquicia digital   :f5a, 2029-01, 6M
    Primera réplica México                  :f5b, 2029-06, 12M
    Expansión Latinoamérica                 :f5c, 2030-06, 12M
```

### 1.2 Principio de Alineación

| Regla | Descripción |
|-------|-------------|
| **Digital sigue a Físico** | No se desarrolla sistema para una unidad que no está en construcción |
| **Piloto antes de Escala** | Cada unidad se pilotea con backbone antes de escalar |
| **Valor desde Sprint 1** | Cada sprint entrega valor auditable, no promesas |
| **Incremental, no Big Bang** | El backbone crece unidad por unidad, no todo de golpe |

---

## 2. Modelo de Retainer de Arquitectura

### 2.1 Por Qué un Core Architecture Team

Aldea Maya requiere coordinar múltiples despachos de TI especializados. La alternativa de contratar desarrolladores por hora genera:

- Fragmentación de conocimiento
- Sin visión arquitectónica unificada
- Riesgo de incompatibilidad entre sistemas
- Imposibilidad de mantener estándares de franquicia

El modelo de **Retainer de Arquitectura** resuelve esto:

```mermaid
graph TD
    subgraph "Modelo por Hora ❌"
        H1[Dev 1: hace feature A] --> SILO1[Silo A]
        H2[Dev 2: hace feature B] --> SILO2[Silo B]
        H3[Dev 3: hace feature C] --> SILO3[Silo C]
        SILO1 -.- SILO2
        SILO2 -.- SILO3
        SILO1 -.->|"No se hablan"| SILO3
    end
```

```mermaid
graph TD
    subgraph "Modelo Retainer ✅"
        BIC[🏢 BeInCloud<br/>Core Architecture Team<br/>Retainer mensual] --> SPEC[📜 Especificaciones<br/>unificadas]
        BIC --> CONT[📜 Contratos de<br/>interfaz]
        BIC --> GOV[🔍 Gobernanza<br/>de calidad]
        BIC --> COORD[🤝 Coordinación<br/>de despachos]

        SPEC --> D1[Despacho IA]
        SPEC --> D2[Despacho Software]
        CONT --> D1
        CONT --> D2
        GOV --> D1
        GOV --> D2
    end
```

### 2.2 Qué Incluye el Retainer

| Servicio | Descripción | Frecuencia |
|----------|-------------|:----------:|
| **Arquitectura de backbone** | Diseño y evolución de la capa de orquestación | Continuo |
| **Especificaciones SDD** | Redacción y mantenimiento de specs para cada unidad | Por fase |
| **Contratos de interfaz** | Definición de APIs y eventos entre sistemas | Por integración |
| **Coordinación de despachos** | Alineación técnica entre todos los proveedores de TI | Semanal |
| **Revisión de calidad** | Validación de entregables vs. especificación | Por entregable |
| **Reporte al fondo** | Dashboard de progreso y métricas de TI | Mensual |
| **Evolución arquitectónica** | Adaptación del backbone a nuevas unidades | Trimestral |

### 2.3 Modelo Económico del Retainer

```mermaid
graph LR
    subgraph "Fase 1-2 (Año 1-2)"
        R1[Retainer Base<br/>Arquitectura + MSN + Porcinos<br/>+ Agricultura]
    end

    subgraph "Fase 3 (Año 2-3)"
        R2[Retainer Expandido<br/>+ Avícola + Acuícola<br/>+ Comercial]
    end

    subgraph "Fase 4 (Año 3-4)"
        R3[Retainer Optimización<br/>+ ML + Certificaciones<br/>+ Canal Premium]
    end

    subgraph "Fase 5 (Año 4-6)"
        R4[Retainer Franquicia<br/>+ Réplicas México<br/>+ Expansión LATAM]
    end

    R1 --> R2 --> R3 --> R4

    subgraph "Tendencia"
        T1[📉 Costo por unidad<br/>productiva: DECRECE]
        T2[📈 Valor del backbone<br/>como activo: CRECE]
    end
```

> **Para el fondo**: El retainer no es un costo fijo de TI. Es la inversión en el sistema nervioso que hace que cada dólar en infraestructura física rinda más. El costo por unidad productiva decrece con cada integración.

---

## 3. Estrategia de Expand: De MSN al Mega Hub

### 3.1 Secuencia de Integración al Backbone

```mermaid
flowchart TD
    MSN[🪰 MSN<br/>PILOTO<br/>Mes 1-4] --> CERDO[🐷 Porcinos<br/>100 vientres<br/>Mes 4-8]
    MSN --> AGRO[🌾 Agricultura<br/>Primeros ciclos<br/>Mes 6-9]

    CERDO --> POLLO[🐔 Avícola<br/>Mes 10-14]
    CERDO --> BOVINO[🐄 Bovino<br/>Mes 12-18]
    AGRO --> INVERN[🏡 Invernaderos<br/>Mes 10-14]
    AGRO --> HIDRO[💧 Hidroponía<br/>Mes 12-16]
    AGRO --> FRUTAL[🍊 Frutales<br/>Mes 12-24]

    MSN --> TILAPIA[🐟 Tilapia<br/>Mes 10-14]
    MSN --> CAMARON[🦐 Camarón<br/>Mes 12-16]

    POLLO --> RASTRO_P[🏭 Rastro Pollo<br/>Mes 16-20]
    CERDO --> RASTRO_C[🏭 Rastro Cerdo<br/>Mes 16-20]
    BOVINO --> RASTRO_B[🏭 Rastro Bovino<br/>Mes 20-24]

    INVERN --> EMP_V[📦 Empaque Verdura<br/>Mes 16-20]
    FRUTAL --> EMP_F[📦 Empaque Fruta<br/>Mes 24-30]
    TILAPIA --> EMP_A[📦 Empaque Acuícola<br/>Mes 16-20]

    RASTRO_P --> COM[🛒 Comercialización<br/>Regional → Estatal<br/>→ Majahual Premium]
    RASTRO_C --> COM
    RASTRO_B --> COM
    EMP_V --> COM
    EMP_F --> COM
    EMP_A --> COM

    style MSN fill:#2d5016,stroke:#1a3a0a,color:#fff
    style COM fill:#1a5276,stroke:#0e2f44,color:#fff
```

### 3.2 Valor Acumulado por Fase

| Fase | Unidades Integradas | Valor del Backbone |
|------|:-------------------:|---------------------|
| **Piloto** | MSN | Prueba de concepto: trazabilidad + auditoría |
| **Fase 2** | MSN + Porcinos + Agricultura | Primera sincronía biológica completa |
| **Fase 3** | + Avícola + Acuícola + Invernaderos | Economía circular operativa |
| **Fase 4** | + Rastros + Empaque + Comercial | Cadena de valor integrada end-to-end |
| **Fase 5** | + Certificaciones + Canal Premium | Máximo valor por producto |
| **Franquicia** | Modelo completo replicable | Activo licenciable |

### 3.3 Canal Premium: Majahual y Royal Caribbean

La salida comercial premium merece mención especial:

- Royal Caribbean adquirió el puerto de Majahual
- 12,000 turistas diarios, 5 millones al año
- Pabellón de restaurantes abastecido por Aldea Maya
- El backbone garantiza trazabilidad de origen para el mercado premium
- Certificación orgánica + regenerativa = precio premium

> **Para el fondo**: El canal Majahual es el multiplicador de valor. Producto trazable + certificado + regenerativo + local = margen premium que justifica toda la inversión en backbone.

---

## 4. Modelo de Socio: La Relación de Largo Plazo

### 4.1 BeInCloud No Es un Proveedor. Es un Socio Arquitectónico.

| Dimensión | Proveedor Tradicional | BeInCloud como Socio |
|-----------|:---------------------:|:--------------------:|
| Relación | Proyecto por proyecto | Retainer de 5-6 años |
| Incentivo | Facturar más horas | Que el backbone genere valor |
| Conocimiento | Se lo lleva al irse | Queda en las specs (SDD) |
| Riesgo | Del cliente | Compartido |
| Éxito | Entregar código | Que Aldea Maya sea replicable |

### 4.2 Skin in the Game

BeInCloud propone un modelo donde parte de la compensación está atada al éxito del territorio:

```mermaid
pie title "Estructura de Compensación BeInCloud"
    "Retainer mensual base" : 60
    "Bonificación por hitos de integración" : 20
    "Participación en licencia de franquicia" : 20
```

### 4.3 Transferencia de Conocimiento

El modelo SDD garantiza que Aldea Maya pueda operar sin BeInCloud si lo decide:

| Año | Nivel de Dependencia | Transferencia |
|:---:|:--------------------:|---------------|
| 1 | Alta | BeInCloud diseña y coordina todo |
| 2 | Media-Alta | Equipo interno de Aldea Maya aprende SDD |
| 3 | Media | Equipo interno co-diseña con BeInCloud |
| 4 | Media-Baja | Equipo interno lidera, BeInCloud asesora |
| 5-6 | Baja | Aldea Maya es autónoma, BeInCloud en franquicia |

---

## 5. Economía del Backbone: Números para el Fondo

### 5.1 Estructura de Inversión Digital

```mermaid
pie title "Distribución de Inversión Digital — 5 Años"
    "Arquitectura y Gobernanza (BeInCloud)" : 25
    "Sistemas de Unidad Productiva" : 30
    "Asistentes Virtuales (Edge AI)" : 15
    "Infraestructura (Edge + Nube)" : 15
    "Sensores IoT y Conectividad" : 10
    "Capacitación y Adopción" : 5
```

### 5.2 Retorno del Backbone

| Fuente de Retorno | Mecanismo | Horizonte |
|--------------------|-----------|:---------:|
| Reducción de merma | Sincronía evita pérdida de insumos y producción | Año 1 |
| Reducción de costo de proteína | MSN vs. harina de pescado importada | Año 1 |
| Precio premium por trazabilidad | Certificación orgánica + regenerativa | Año 2 |
| Eficiencia operativa | Optimización de recursos por datos | Año 2-3 |
| Canal Majahual | Acceso a mercado premium de 5M turistas/año | Año 3 |
| Créditos de carbono | MRV automatizado por el backbone | Año 3-4 |
| Licencia de franquicia | Modelo replicable a otras regiones | Año 4-6 |

### 5.3 Punto de Equilibrio del Backbone

El backbone se autofinancia cuando:

```
Ahorro por sincronía + Prima por trazabilidad + Ingresos por certificación
> Costo del retainer + Costo de infraestructura + Costo de operación
```

Estimación conservadora: **Año 2-3** el backbone genera más valor del que cuesta.

---

## 6. Gobernanza y Transparencia: Compromiso con el Fondo

### 6.1 Reportes Periódicos

| Reporte | Frecuencia | Contenido |
|---------|:----------:|-----------|
| Dashboard operativo | Tiempo real | Estado de cada unidad productiva |
| Reporte de auditoría | Mensual | Trazabilidad financiera completa |
| Reporte de progreso TI | Mensual | Specs completadas, sistemas integrados |
| Reporte de impacto social | Trimestral | Empleos, vivienda, educación |
| Reporte de impacto ambiental | Trimestral | Circularidad, regeneración, emisiones |
| Revisión estratégica | Semestral | Alineación roadmap físico-digital |

### 6.2 Compromiso de Transparencia

> Cada peso invertido en el backbone tiene:
> - Una especificación que lo justifica
> - Un contrato que lo respalda
> - Una métrica que lo mide
> - Un reporte que lo comunica
>
> Sin excepciones. Sin cajas negras. Sin sorpresas.

---

## 7. Próximos Pasos Inmediatos

| # | Acción | Responsable | Plazo |
|---|--------|-------------|:-----:|
| 1 | Constituir grupo de trabajo (WhatsApp + Drive) | Aldea Maya + BeInCloud | Semana 1 |
| 2 | Presentación corporativa BeInCloud al equipo Aldea Maya | BeInCloud | Semana 1 |
| 3 | Acceso al Drive con documentación completa del proyecto | Aldea Maya | Semana 1 |
| 4 | Firma de NDA | Ambas partes | Semana 2 |
| 5 | Acompañamiento para dimensionar TI completo | BeInCloud + Directora de Estrategia | Semana 2-3 |
| 6 | Blueprint MSN (4 semanas) | BeInCloud | Semana 3-6 |
| 7 | Precotización de Fase 1 | BeInCloud | Semana 6-8 |

---

*Documento vivo. Versión 0.1 — Sprint 0, Abril 2026*
*BeInCloud — Arquitectos de Sistemas Nerviosos Territoriales*
