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
    
    %% Notes for AEZ 2
    H -.-> AEZ2note["AEZ 2 Lacks all three factors.<br>Farm pond interventions help these marginal farmers despite low suitability.<br>Negative Rabi & Zaid due to skewed borewell density.<br>Drought sensitivity reduced post-intervention."]
    
    %% Moderate Suitability Branch
    C --> I[Canal Density High: AEZ 6, 7<br>Difference in distance from Canal: 0m]
    C --> J[Canal Density Low: AEZ 4, 11, 12]
    
    I --> K[Borewell Density High: AEZ 6]
    I --> L[Borewell Density Low: AEZ 7]
    
    J --> M[Difference in distance from Canal: 0m<br>AEZ 4, 11]
    J --> N[Difference in distance from Canal: 8000m<br>AEZ 12]
    
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
    
    %% Notes for moderate AEZs
    W -.-> AEZ6note["AEZ 6 Due to the high borewell density and assignment of farms to marginal farmers - we can observe a negative treatment affect in Rabi & Zaid. So sensitity to droughts has increased at treated sites (Given that control sites may have more access to water)"]
    X -.-> AEZ7note["[LINED]<br>AEZ 7 Very similar to AEZ 6 in terms of endowment, however these farmers do not have as many borewells and assignment does not indicate Marginal justifying the equal effect seen in Rabi & Zaid."]
    Y -.-> AEZ4note["AEZ 4: This suggests that in AEZ 4, farmers were already using groundwater from borewells as their primary water source, which provided them with a certain baseline level of drought resilience before farm pond interventions. The high borewell density means they already had access to groundwater during dry periods, so adding farm ponds didn't significantly change their drought sensitivity."]
    Z -.-> AEZ11note["AEZ 11: Very similar to AEZ 2 in terms of factors, however moderately endowed so ATE observed is not as high."]
    AA -.-> AEZ12note["AEZ 12: A factor contributing to lower effect is control sites being closer to canals. Perhaps farm ponds were assigned to approved for locations with low reachability of canals."]
    
    %% High Suitability Branch
    D --> AB[Canal Density High: AEZ 9, 10, 13<br>Difference in Distance from Canal: 0m]
    
    AB --> AC[Borewell Density High: AEZ 9, 13]
    AB --> AD[Borewell Density Low: AEZ 10]

    AC --> AE[Farm Pond Density Low]
    AD --> AF[Farm Pond Density Low]
    
    AE --> AG[AEZ 9: Kharif: 2%, Rabi: 2%, Zaid: 4%<br>RQ-2: Not significant, 0.1%<br>RQ-3: Positive impact for most freq > 4]:::high
    AE --> AZ[AEZ 13: Kharif: 2%, Rabi: -4%, Zaid: -0.80%<br>RQ-2: Significant, 3%<br>RQ-3: Positive impact only for freq <= 4]:::high
    AF --> AH[AEZ 10: Kharif: -0.4%, Rabi: 0%, Zaid: 0%<br>RQ-2: Not sufficient values<br>RQ-3: Negative impact other than freq = 6 and 12]:::low
    
    %% Notes for high suitability AEZs
    AG -.-> AEZ9note["AEZ 9: The region has a high groundwater table which supports irrigation-based farming. This is also called the Rice Belt and is known for extensive GW extraction, plastic lined FP are prevalent."]
    AZ -.-> AEZ13note["AEZ 13: Comparitively marginalised farmers get the FPs and the rainfall is high, so there is positive impact on an average for these farmers with farm ponds. However in Rabi and Zaid the results indicate that there may be inequity in the distribution of borewell access - one possible explanation for negative results is that the control sites also have access to Borewells to irrigate which is why the treatment affect is negative in those 2 seasons."]
    AH -.-> AEZ10note["AEZ 10: We can observe that the area is naturally endowned with great conditions. Borewell density is low. Control sites are performing similarly to treated sites."]
    
    %% Farm Pond Typology Nodes
    UNLINED[Unlined Farm Ponds]:::typology
    BOTH[Both Lined & Unlined Farm Ponds]:::typology
    
    %% Marginal Farmers Node
    MARGINAL[Marginal farmers<br>Lined Farm Ponds]:::marginal
    
    %% Connect nodes to Marginal farmers
    H --> MARGINAL
    W --> MARGINAL
    %% X --> MARGINAL
    
    %% Connect nodes to typology
    Y --> BOTH
    %% Z --> BOTH
    AA --> UNLINED
    AG --> BOTH
    AH --> UNLINED
    AZ --> UNLINED

    Z --> n[Lined & Unlined<br>Marginal Farmers]
    
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
    
    %% Notes Styling
    classDef notes fill:none,stroke:none,color:#333333,font-style:italic
    
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
    class AEZ2note,AEZ4note,AEZ6note,AEZ7note,AEZ9note,AEZ10note,AEZ11note,AEZ12note,AEZ13note notes
