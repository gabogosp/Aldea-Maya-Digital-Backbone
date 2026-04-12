# 🪰 04 — Blueprint del Proyecto Piloto: Unidad de Transformación MSN

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
| **Demuestra el modelo** | Si MSN funciona orquestada por el backbone, el fondo ve el patrón para las demás unidades. |
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

## 4. Entregable en 4 Semanas: Alcance del Blueprint Técnico

### 4.1 Semana 1-2: Especificación

| Entregable | Descripción |
|------------|-------------|
| Spec de flujo de recolección | Desde alianza municipal hasta planta de separación |
| Spec de ciclo larval | Control de naves, temperatura, humedad, tiempos |
| Spec de producción | Rendimiento, calidad, distribución de productos |
| Spec de integración con backbone | Eventos, contratos, SLAs |
| Modelo de datos MSN | Entidades, relaciones, cadena de custodia |

### 4.2 Semana 3: Validación

| Entregable | Descripción |
|------------|-------------|
| Revisión con aliado MSN | El líder especialista valida la lógica de negocio |
| Revisión con Dirección Estratégica | Alineación con visión estratégica de Aldea Maya |
| Revisión de auditoría | Verificar que cada dato es trazable para el fondo |
| Ajustes a especificaciones | Incorporar feedback |

### 4.3 Semana 4: Blueprint Técnico

| Entregable | Descripción |
|------------|-------------|
| Blueprint de sistema MSN | Arquitectura, componentes, tecnologías recomendadas |
| Contratos de interfaz | APIs y eventos para integración con backbone |
| Plan de implementación | Fases, tiempos, recursos, costos estimados |
| Precotización detallada | Alineada con el proceso de Aldea Maya |

### 4.4 Criterios de Éxito del Blueprint

- [ ] El aliado MSN puede leer la spec y confirmar que refleja su operación
- [ ] El fondo puede leer el blueprint y entender el flujo de inversión
- [ ] Cualquier despacho de TI puede tomar el blueprint e implementar
- [ ] Los contratos de interfaz permiten integración futura con porcinos, agricultura, etc.
- [ ] Las métricas de auditoría están definidas y son medibles

---

## 5. Gobernanza y Transparencia del Piloto

### 5.1 Reporte al Fondo — Piloto MSN

El piloto MSN genera el primer reporte de auditoría real del backbone:

```mermaid
pie title "Distribución de Inversión — Piloto MSN"
    "Especificación SDD" : 25
    "Infraestructura física" : 35
    "Sistema digital (desarrollo)" : 20
    "Asistente virtual (Edge AI)" : 10
    "Capacitación de aldeanos" : 10
```

### 5.2 KPIs del Piloto para el Fondo

| KPI | Definición | Frecuencia |
|-----|------------|:----------:|
| Toneladas procesadas | Residuo convertido en producto | Semanal |
| Costo por kg de proteína | Competitividad vs. mercado | Mensual |
| Tasa de conversión | Eficiencia del proceso biológico | Por lote |
| Empleos generados | Impacto social directo | Mensual |
| Trazabilidad | % de flujos con registro completo | Mensual |
| Tiempo de reporte | Días entre cierre de mes y reporte listo | Mensual |

> **Para el fondo**: El piloto MSN es la prueba de concepto del modelo completo. Si funciona aquí — con trazabilidad, auditoría y orquestación — funciona en las 20+ unidades restantes.

---

*Documento vivo. Versión 0.1 — Sprint 0, Abril 2026*
*BeInCloud — Arquitectos de Sistemas Nerviosos Territoriales*
