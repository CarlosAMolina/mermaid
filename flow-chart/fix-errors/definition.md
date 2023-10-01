flowchart TD
    WorksDecision{¿Funciona?}
    WorksDecision -->|Yes| Fin
    WorksDecision -->|No| WhereDecision
    WhereDecision{¿Conoces el lugar exacto del error?}
    WhereDecision -->|Si| WhyDecision
    WhereDecision -->|No| WhereProcess
    WhereProcess[Analiza el caso] --> WhereDecision
    WhyDecision{¿Entiendes el motivo exacto por el que falla?}
    WhyDecision -->|No| WhyProcess
    WhyDecision -->|Si| ReproduceDecision
    WhyProcess[Analiza el caso] --> WhyDecision
    ReproduceDecision{¿Puedes reproducir el error en un entorno controlado donde hacer pruebas, ejemplo en un test?}
    ReproduceDecision -->|No| ReproduceAction
    ReproduceDecision -->|Yes| FixAction
    ReproduceAction[Analiza el caso y soluciona el test si creaste uno a partir del error] --> ReproduceDecision
    FixAction[Trabaja en solucionarlo] --> WorksEndDecision
    WorksEndDecision{¿Funciona?}
    WorksEndDecision -->|No| FixAction
    WorksEndDecision -->|Si| Fin
