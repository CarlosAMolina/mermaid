flowchart TD
    WorksQ{¿Funciona?}
    WorksQ -->|Yes| Fin
    WorksQ -->|No| WhereQ
    WhereQ{¿Conoces el lugar exacto del error?}
    WhereQ -->|Si| WhyQ
    WhereQ -->|No| WhereA
    WhereA[Analiza el caso] --> WhereQ
    WhyQ{¿Entiendes el motivo exacto por el que falla?}
    WhyQ -->|No| WhyA
    WhyQ -->|Si| ReproduceQ
    WhyA[Analiza el caso] --> WhyQ
    ReproduceQ{¿Puedes reproducir el error en un entorno controlado donde hacer pruebas, ejemplo en un test?}
    ReproduceQ -->|No| ReproduceA
    ReproduceQ -->|Yes| FixA
    ReproduceA[Analiza el caso y soluciona el test si creaste uno a partir del error] --> ReproduceQ
    FixA[Trabaja en solucionarlo] --> WorksEndQ
    WorksEndQ{¿Funciona?}
    WorksEndQ -->|No| FixA
    WorksEndQ -->|Si| Fin

