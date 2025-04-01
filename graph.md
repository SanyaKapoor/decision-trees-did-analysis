```mermaid
graph TD
    A[ALl AEZs] -->|RELATIVE_BOREWELL_DENSITY <= 0.10| B[AEZ 12, 10, 6]
    A -->|RELATIVE_BOREWELL_DENSITY > 0.10| C[AEZ 2, 4, 7, 9, 11, 13]
    
    B -->|IS CANAL DENSITY HIGH?| D[SLIGHTLY POSITIVE - AEZ 6]
    B -->|IS CANAL DENSITY LOW?| E[NEGLIGIBLE - AEZ 12 and 10]
    
    C -->|IS FARM POND DENSITY LOW?| H[AEZ 4 and 7]
    C -->|IS FARM POND DENSITY MODERATE-HIGH?| I[AEZ 2, 9, 11, 13]
    
    H -->|CANAL DENSITY LOW| J[NEGLIGIBLE - AEZ 4]
    H -->|CANAL DENSITY HIGH| K[SLIGHTLY POSITIVE - AEZ 7]
    
    I -->|IS RAINFALL VERY LOW?| L[HIGHLY POSITIVE - AEZ 2]
    I -->|IS RAINFALL HIGH?| M[SLIGHTLY POSITIVE - AEZ 11, 13, 9]
    
    classDef decisionNode fill:#ffcc99,stroke:#ff9900,stroke-width:2px;
    classDef leafNode fill:#ccffcc,stroke:#00cc00,stroke-width:2px;
    
    class A,B,C,H,I decisionNode;
    class E,D,J,K,L,M leafNode;
