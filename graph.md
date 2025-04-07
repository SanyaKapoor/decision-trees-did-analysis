```mermaid
graph TD
    A[Agro-Ecological Zones] --> B[Rainfall < 1000mm]
    A --> C[Rainfall > 1000mm]
    
    B --> D[LHS Canal Low: AEZ 2, 4]
    B --> E[LHS Canal High: AEZ 6, 7]
    
    E --> F[LHS-RHS Borewell High: AEZ 6]
    E --> G[LHS-RHS Borewell Low: AEZ 7]
    D --> H[LHS-RHS Borewell Low: AEZ 2, 4]
    
    C --> I[RHS Canal High: AEZ 9]
    C --> J[RHS Canal Low: AEZ 10, 11, 12, 13]
    
    I --> K[LHS-RHS Borewell High: AEZ 9]
    
    J --> L[LHS-RHS Borewell High: AEZ 13]
    J --> M[LHS-RHS Borewell Low: AEZ 10, 11, 12]
