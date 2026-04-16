Tarjetas Astrum

``mermaid

flowchart TB
    A["<b>INICIO</b>"] --> B["Espera 90 segundos"]
    B --> C{"<b>¿Hay internet?</b>"}

    C -- Sí --> D["Mostrar ONLINE Esperar 30s"]
    D --> C

    C -- No --> E{"<b>¿En pausa de 4h?</b>"}
    E -- Sí --> F["Esperar hasta que termine"]
    F --> C

    E -- No --> G{"<b>¿Límite diario 40 reinicios?</b>"}
    G -- Sí --> H["Mostrar: LÍMITE DIARIO AGOTADO "]
    H --> C

    G -- No --> I{"<b>¿5 reinicios instantáneos?</b>"}
    I -- Sí --> J["Activar pausa de 4h"]
    J --> C

    I -- No --> K["Incrementar contadores Guardar en archivo"]
    K --> L["Activar Relé + Buzzer"]
    L --> M["Esperar 90s boot del modem"]
    M --> C

    style A fill:#1a1a1a,color:#fff,stroke:#000,stroke-width:2px
    style C fill:#fff3cd,color:#856404,stroke:#ffeeba,stroke-width:2px
    style E fill:#fff3cd,color:#856404,stroke:#ffeeba,stroke-width:2px
    style G fill:#fff3cd,color:#856404,stroke:#ffeeba,stroke-width:2px
    style I fill:#fff3cd,color:#856404,stroke:#ffeeba,stroke-width:2px

    classDef paso fill:#fff,stroke:#333,color:#000
    class B,D,F,H,J,K,L,M paso
    ``
