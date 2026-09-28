# Student Visits Portal

## Student Registration Flowchart

```mermaid
flowchart TD
    A[Student Visits Portal] --> B[Login/Sign Up]
    B --> C{User Type?}
    C -->|New Student| D[Enter Personal Info]
    C -->|Returning Student| E[Verify Credentials]
    D --> F[Select School/Program]
    E --> F
    F --> G[Choose Courses]
    G --> H[Review Schedule]
    H --> I{Conflicts?}
    I -->|Yes| J[Adjust Selection]
    J --> H
    I -->|No| K[Proceed to Payment]
    K --> L[Enter Payment Details]
    L --> M{Payment Success?}
    M -->|Failed| N[Retry Payment]
    N --> L
    M -->|Success| O[Generate Confirmation]
    O --> P[Send Confirmation Email]
    P --> Q[Registration Complete]

    classDef entry stroke:#818cf8,fill:#eef2ff
    classDef process stroke:#2dd4bf,fill:#f0fdfa
    classDef decision stroke:#a78bfa,fill:#f5f3ff
    classDef payment stroke:#fb923c,fill:#fff7ed
    classDef success stroke:#4ade80,fill:#f0fdf4
    classDef error stroke:#f87171,fill:#fef2f2

    class A entry
    class B,D,E,F,G,H,L,O,P process
    class C,I,M decision
    class K,N payment
    class Q success
    class J error
