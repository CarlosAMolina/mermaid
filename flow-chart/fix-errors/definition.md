flowchart TD
    A{¿Funciona?}
    A -->|Yes| Fin
    A -->|No| B
    B{¿Conoces el lugar exacto del error?}
    B -->|Si| C
    B -->|No| D 
    D[Analiza el caso] --> B
    C{¿Entiendes el motivo exacto por el que falla?}
    C -->|No| E
    C -->|Si| F
    E[Analiza el caso] --> C
    F{¿Puedes reproducir el error en un entorno controlado donde hacer pruebas, ejemplo en un test?}
    F -->|No| G
    F -->|Yes| H
    E[Analiza el caso y soluciona el test si creaste uno a partir del error] --> F
    H[Trabaja en solucionarlo] --> I
    I{¿Funciona?}
    I -->|No| H
    I -->|Si| Fin

