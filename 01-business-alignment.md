# 🌾 01 — Sincronía Biológica y Operativa

> *"Entendemos el campo mejor que cualquier software factory."*

---

## 1. El Reloj Biológico Manda

Aldea Maya no opera con sprints de software. Opera con **ciclos biológicos** que no esperan, no se pausan y no negocian. El Digital Backbone existe para servir a estos relojes — no al revés.

### 1.1 El Ciclo del Lechón: 3 Meses, 3 Semanas, 3 Días

Este es el reloj maestro que sincroniza la mitad de las unidades productivas de Aldea Maya:

```mermaid
gantt
    title Ciclo Productivo del Cerdo — Sincronía con Agricultura y MSN
    dateFormat  YYYY-MM-DD
    axisFormat  %b %d

    section 🐷 Porcinos
    Gestación (3m 3s 3d)          :gest, 2026-05-01, 114d
    Lactancia (21 días)           :lact, after gest, 21d
    Destete y Crecimiento         :crec, after lact, 60d
    Engorda hasta sacrificio      :eng, after crec, 60d

    section 🌾 Agricultura
    Siembra Maíz (ciclo 90d)     :maiz, 2026-05-15, 90d
    Siembra Sorgo (ciclo 60d)    :sorgo, 2026-06-01, 60d
    Siembra Soya (ciclo 90d)     :soya, 2026-05-20, 90d
    Cosecha alineada a destete   :milestone, after lact, 0d

    section 🪰 MSN (Mosca Soldado Negro)
    Recolección residuos (continuo) :res, 2026-05-01, 255d
    Producción proteína larval      :prot, 2026-05-15, 240d
    Producción fertilizante         :fert, 2026-05-15, 240d
```

**Lo que el backbone orquesta:**

Cuando el asistente virtual de gestación registra que una cerda fue preñada, el backbone:

1. Calcula la fecha de nacimiento (114 días después)
2. Estima 10-14 lechones por camada
3. Notifica a **Agricultura** para que inicie los ciclos de siembra de ingredientes (maíz 90d, sorgo 60d, soya 90d)
4. Notifica a **MSN** para que incremente la producción de proteína larval proporcional al número de cabezas
5. Notifica a **Espirulina** para complemento nutricional
6. Registra todo para la **auditoría mensual** del fondo

> **Regla de negocio**: Los cultivos de 30, 60 y 90 días deben estar asignados y en producción ANTES de que nazca el lechón. El backbone no permite que un ciclo de gestación avance sin confirmación de abastecimiento de ingredientes.

---

### 1.2 Mapa de Ciclos Biológicos Interconectados

```mermaid
graph LR
    subgraph "⏱️ Ciclos Cortos (7-30 días)"
        MSN[🪰 MSN<br/>Ciclo larval: 14-18 días]
        ESP[🌿 Espirulina<br/>Cosecha: 7-10 días]
    end

    subgraph "⏱️ Ciclos Medios (30-120 días)"
        AGRO30[🌽 Cultivos 30d<br/>Hortalizas rápidas]
        AGRO60[🌾 Cultivos 60d<br/>Sorgo, forrajes]
        AGRO90[🫘 Cultivos 90d<br/>Maíz, soya]
        POLLO[🐔 Pollo<br/>Ciclo: 45-60 días]
        TILAPIA[🐟 Tilapia<br/>Ciclo: 90-120 días]
    end

    subgraph "⏱️ Ciclos Largos (120-365 días)"
        CERDO[🐷 Cerdo<br/>Gestación + Engorda: 255d]
        BOVINO[🐄 Bovino<br/>Ciclo: 12-18 meses]
        CAMARON[🦐 Camarón<br/>Ciclo: 120-150 días]
        FRUTAL[🍊 Frutales<br/>Ciclo anual+]
    end

    MSN -->|proteína| CERDO
    MSN -->|proteína| POLLO
    MSN -->|proteína| TILAPIA
    MSN -->|proteína| CAMARON
    MSN -->|fertilizante| AGRO30
    MSN -->|fertilizante| AGRO60
    MSN -->|fertilizante| AGRO90
    MSN -->|fertilizante| FRUTAL
    ESP -->|complemento| CERDO
    ESP -->|complemento| POLLO
    AGRO30 -->|ingredientes| CERDO
    AGRO60 -->|ingredientes| CERDO
    AGRO90 -->|ingredientes| CERDO
    AGRO90 -->|ingredientes| BOVINO
```

---

## 2. Optimización de Proteína MSN: El Pivote de la Economía Circular

La Mosca Soldado Negro (Hermetia illucens) no es una unidad productiva más. Es el **pivote central** de la economía circular de Aldea Maya.

### 2.1 Flujo de Transformación MSN

```mermaid
flowchart TD
    R1[🏘️ Residuos Municipales<br/>2-3 pueblos cercanos<br/>20 ton iniciales] --> SEP[🏭 Planta de Separación<br/>Orgánico vs. No-orgánico]
    R2[🐷 Residuos Pecuarios<br/>Estiércol, desechos] --> SEP
    R3[🌾 Residuos Agrícolas<br/>Rastrojo, merma] --> SEP

    SEP -->|Solo orgánico| MSN[🪰 Unidad MSN<br/>Bioconversión por<br/>larva de Hermetia illucens]

    MSN -->|40-42% proteína| PROT[🥩 Harina de Proteína<br/>Sustituto de harina<br/>de pescado/soya]
    MSN -->|Grasa larval| GRASA[🛢️ Aceite Larval<br/>Ácido láurico<br/>para dietas animales]
    MSN -->|Frass residual| FERT[🌱 Fertilizante Orgánico<br/>Rico en NPK<br/>Regenerador de suelo]

    PROT -->|Dietas| CERDO[🐷 Porcinos]
    PROT -->|Dietas| POLLO[🐔 Aves]
    PROT -->|Dietas| TILAPIA[🐟 Tilapia]
    PROT -->|Dietas| CAMARON[🦐 Camarón]
    GRASA --> CERDO
    GRASA --> POLLO
    FERT --> AGRO[🌾 Agricultura<br/>Regeneración de suelo]

    style MSN fill:#2d5016,stroke:#1a3a0a,color:#fff
    style FERT fill:#4a7c2e,stroke:#2d5016,color:#fff
    style PROT fill:#8b4513,stroke:#5c2d0e,color:#fff
```

### 2.2 Por Qué MSN Es el Pivote

| Dimensión | Impacto |
|-----------|---------|
| **Económica** | Reduce costo de proteína animal en 30-50% vs. harina de pescado importada |
| **Circular** | Convierte residuo municipal (costo negativo) en insumo productivo (ingreso) |
| **Ambiental** | Cada tonelada de residuo procesado = reducción medible de emisiones |
| **Social** | Alianza con gobierno municipal para recolección = empleo + limpieza urbana |
| **Escalable** | El ciclo larval de 14-18 días permite escalar producción rápidamente |

### 2.3 Lo Que el Backbone Orquesta en MSN

- Volumen de residuo recolectado vs. capacidad de procesamiento
- Producción de proteína vs. demanda de las unidades pecuarias
- Producción de fertilizante vs. necesidad de los ciclos agrícolas
- Trazabilidad completa: del residuo municipal al plato del animal
- Métricas de circularidad para reporte al fondo y certificaciones

> **Regla de negocio**: La producción de MSN debe escalar proporcionalmente al número de cabezas en las unidades pecuarias. El backbone calcula y proyecta esta demanda automáticamente.

---

## 3. Impacto Social Estructural: La Dignidad del Aldeano

Aldea Maya no contrata mano de obra. **Integra familias a un ecosistema productivo.**

### 3.1 Modelo de Integración Social

```mermaid
flowchart TD
    FAM[👨‍👩‍👧‍👦 Familias de<br/>José María Morelos,<br/>La Presumida, San Felipe I] --> VIV[🏠 Clúster de 250 Casas<br/>Ecológicas, energías limpias,<br/>biodigestores, agua tratada]

    VIV --> EMP[💼 Empleo Formal<br/>en Unidades Productivas]
    VIV --> EDU[🎓 Escuela Integrada<br/>Hijos de aldeanos]

    EDU -->|Años 1-6: Primaria| IA[🤖 Educación con IA<br/>Caricaturas y presentaciones<br/>sobre las 15-20 unidades<br/>productivas]
    EDU -->|Año 7+: Talleres| CAMPO[🌾 Talleres de Campo<br/>Eligen 3 unidades<br/>productivas de interés]
    CAMPO -->|Buen promedio| BECA[🎓 Becas Prepa<br/>y Universidad]
    BECA -->|Retorno| ALDEA[🏘️ Reintegración<br/>a Aldea Maya como<br/>profesional]

    EMP --> COOP[🤝 Cooperativas<br/>Los aldeanos son parte<br/>de la estructura productiva]

    style FAM fill:#1a5276,stroke:#0e2f44,color:#fff
    style ALDEA fill:#1a5276,stroke:#0e2f44,color:#fff
```

### 3.2 Lo Que el Backbone Digitaliza

La "dignidad del aldeano" no es un eslogan. Es un conjunto de métricas que el backbone captura y reporta:

| Indicador | Captura | Reporte |
|-----------|---------|---------|
| Empleo formal generado | Registro de contratos y cooperativas | Trimestral al fondo |
| Retención escolar | Asistencia y rendimiento en escuela integrada | Semestral |
| Capacitación técnica | Horas de formación por aldeano | Mensual |
| Ingreso familiar | Flujo de compensación por cooperativa | Mensual |
| Vivienda digna | Ocupación del clúster, servicios activos | Trimestral |
| Migración evitada | Permanencia territorial vs. baseline regional | Anual |

### 3.3 Edge AI: Interfaces de Captura Simplificadas

Los aldeanos no son usuarios de software. Son operadores de campo que necesitan **interfaces que no estorben**:

- Asistentes virtuales de voz en español regional (maya-español donde aplique)
- Captura por voz: "Ya parió la cerda 47, tuvo 12 lechones"
- El asistente traduce a datos estructurados y alimenta el sistema de la unidad productiva
- Sin pantallas complejas, sin formularios, sin capacitación de semanas
- Funciona offline (edge) y sincroniza cuando hay conexión

> **Regla de negocio**: Si un aldeano necesita más de 30 segundos para registrar un dato, la interfaz está mal diseñada. El backbone se adapta al campo, no el campo al backbone.

---

## 4. Gobernanza y Transparencia

### 4.1 Trazabilidad para el Fondo

Cada dato capturado en campo tiene una línea directa hasta el reporte de auditoría:

```
Aldeano registra dato → Asistente Virtual valida → Sistema de Unidad Productiva
    → Bus de Orquestación → Agregación Financiera → Dashboard del Fondo
```

### 4.2 SDD (Spec-Driven Development)

Cada flujo de sincronía biológica está documentado como especificación antes de ser código. Esto significa que:

- El fondo puede auditar la lógica de negocio sin leer código
- Cualquier despacho de TI puede implementar a partir de la especificación
- Aldea Maya es dueña del conocimiento, no del proveedor

---

*Documento vivo. Versión 0.1 — Sprint 0, Abril 2026*
*BeInCloud — Arquitectos de Sistemas Nerviosos Territoriales*
