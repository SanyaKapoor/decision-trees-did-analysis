```mermaid
graph TD
    A[Agro-Ecological Zones] --> B[Low Agricultural Suitability<br>AEZ 2]
    A --> C[Moderate Agricultural Suitability<br>AEZ 4, 6, 7, 11, 12]
    A --> D[High Agricultural Suitability<br>AEZ 9, 10, 13]
    
    %% Low Suitability Branch
    B --> E[Canal Density Low: AEZ 2<br>Difference in distance from Canal: 0m]
    E --> F[Borewell Density Low: AEZ 2]
    F --> G[Farm Pond Density Low]
    G --> H[AEZ 2:<br>Kharif: 4%, Rabi: -1%, Zaid: -1%<br>RQ-2: -0.60%<br>RQ-3: Positive impact for freq <= 8]:::high
    
    %% Moderate Suitability Branch
    C --> I[Canal Density High: AEZ 6, 7<br>Difference in distance from Canal: 0m]
    C --> J[Canal Density Low: AEZ 4, 11, 12]
    
    I --> K[Borewell Density High: AEZ 6]
    I --> L[Borewell Density Low: AEZ 7]
    
    J --> M[Differnce in distance from Canal: 0m<br>AEZ 4, 11]
    J --> N[Differnce in distance from Canal: 8000m<br>AEZ 12]
    
    M --> O[Borewell Density High: AEZ 4]
    M --> P[Borewell Density Low: AEZ 11]
    N --> Q[Borewell Density Low: AEZ 12]
    
    K --> R[Farm Pond Density Low]
    L --> S[Farm Pond Density Low]
    O --> T[Farm Pond Density Low]
    P --> U[Farm Pond Density High]
    Q --> V[Farm Pond Density High]
    
    R --> W[AEZ 6:<br>Kharif: 1%, Rabi: -3%, Zaid: -0.50%<br>RQ-2: Significant, 0.6%<br>RQ-3: No positive impact]:::medium
    S --> X[AEZ 7:<br>Kharif: 1%, Rabi: 1%, Zaid: -4%<br>RQ-2: Significant, 0.3%<br>RQ-3: Positive impact for freq <= 10]:::medium
    T --> Y[AEZ 4:<br>Kharif: 0.20%, Rabi: 0.20%, Zaid: 0%<br>RQ-2: -0.20%<br>RQ-3: Positive impact for freq > 4]:::low
    U --> Z[AEZ 11:<br>Kharif: 2%, Rabi: -0.30%, Zaid: -0.50%<br>RQ-2: Not significant, 0.6%<br>RQ-3: Positive impact for all frequencies]:::high
    V --> AA[AEZ 12:<br>Kharif: 0.20%, Rabi: 0%, Zaid: 0%<br>RQ-2: -0.05%<br>RQ-3: Positive impact till freq <= 8]:::low
    
    %% High Suitability Branch
    D --> AB[Canal Density High: AEZ 9, 10, 13<br>Difference in Distance from Canal: 0m]
    
    AB --> AC[Borewell Density High: AEZ 9, 13]
    AB --> AD[Borewell Density Low: AEZ 10]

    AC --> AE[Farm Pond Density Low]
    AD --> AF[Farm Pond Density Low]
    
    AE --> AG[AEZ 9: Kharif: 2%, Rabi: 2%, Zaid: 4%<br>RQ-2: Not significant, 0.1%<br>RQ-3: Positive impact for most freq > 4<br>]:::high
    AE --> new[AEZ 13: Kharif: 2%, Rabi: -4%, Zaid: -0.80%<br>RQ-2: Significant, 3%<br>RQ-3: Positive impact only for freq <= 4]:::high
    AF --> AH[AEZ 10: Kharif: -0.4%, Rabi: -0%, Zaid: 0%<br>RQ-2: Not sufficient values<br>RQ-3: Negative impact other than freq = 6 and 12]:::low
    
    %% %% Farm Pond Typology Nodes
    %% LINED[Lined Farm Ponds]:::typology
    UNLINED[Unlined Farm Ponds]:::typology
    BOTH[Both Lined & Unlined Farm Ponds]:::typology
    
    %% Marginal Farmers Node
    MARGINAL[Marginal farmers<br>Lined Farm Ponds]:::marginal
    
    %% Connect nodes 2, 6, 11 to Marginal farmers
    H --> MARGINAL
    W --> MARGINAL
    X --> MARGINAL
    
    %% %% Connect all nodes to typology nodes
    %% H --> LINED
    %% W --> BOTH
    %% X --> LINED
    Y --> BOTH
    Z --> BOTH
    AA --> UNLINED
    AG --> BOTH
    AH --> UNLINED
    new --> UNLINED
    
    %% Natural Suitability Styling
    classDef suitability fill:#e3f2fd,stroke:#0d47a1,stroke-width:1px
    classDef lowSuit fill:#ffebee,stroke:#b71c1c,stroke-width:1px
    classDef modSuit fill:#fff9c4,stroke:#f57f17,stroke-width:1px
    classDef highSuit fill:#e8f5e9,stroke:#1b5e20,stroke-width:1px
    
    %% Infrastructure Styling
    classDef canalLow fill:#ffecb3,stroke:#ff6f00,stroke-width:1px
    classDef canalHigh fill:#fff9c4,stroke:#f57f17,stroke-width:1px
    classDef canalDistance fill:#ffe0b2,stroke:#e65100,stroke-width:1px
    classDef borewellLow fill:#e1bee7,stroke:#6a1b9a,stroke-width:1px
    classDef borewellHigh fill:#d1c4e9,stroke:#4527a0,stroke-width:1px
    
    %% Intervention Styling
    classDef farmPondLow fill:#bbdefb,stroke:#1565c0,stroke-width:1px
    classDef farmPondHigh fill:#90caf9,stroke:#0d47a1,stroke-width:1px
    
    %% Outcome Styling
    classDef low fill:#ffcdd2,stroke:#c62828,stroke-width:2px
    classDef high fill:#c8e6c9,stroke:#2e7d32,stroke-width:2px
    classDef medium fill:#ffecb3,stroke:#ff6f00,stroke-width:2px
    
    %% Typology Styling
    classDef typology fill:#b3e5fc,stroke:#0277bd,stroke-width:2px
    
    %% Marginal Farmers Styling
    classDef marginal fill:#ffffff,stroke:#000000,stroke-width:2px
    
    %% Applying Classes
    class A suitability
    class B lowSuit
    class C modSuit
    class D highSuit
    class E,J canalLow
    class I,AB canalHigh
    class M,N canalDistance
    class F,L,P,Q,AD borewellLow
    class K,O,AC borewellHigh
    class G,R,S,T,AE,AF farmPondLow
    class U,V farmPondHigh
