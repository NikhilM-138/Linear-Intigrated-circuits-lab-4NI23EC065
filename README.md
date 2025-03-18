```mermaid
%%{init: {"themeVariables": {"canvasBg": "white"}}}%%
graph LR
    direction LR

    subgraph Inputs
        A[i_candidate_1]
        C[i_candidate_2]
        D[i_candidate_3]
        E[i_candidate_4]
        F[i_voting_over]
        G[clk]
        H[rst]
        AF[i_reset_pin]
        AH[i_reset_request]
    end

    B(Voting Machine)

    subgraph State_Machine
        I{State Machine}
        J[r_present_state]
        K[r_next_state]
        L[r_hold_count]
    end

    subgraph Vote_Counters
        M{Vote Counters}
        N[r_counter_1]
        O[r_counter_2]
        P[r_counter_3]
        Q[r_counter_4]
    end

    subgraph NVM
        R{NVM}
        S[nvm_count1]
        T[nvm_count2]
        U[nvm_count3]
        V[nvm_count4]
        W[nvm_data_valid]
    end

    subgraph Beep_Logic
        AB{Beep Logic}
        AC[beep_counter]
        AD[beep_active]
        AE[o_beep]
    end

    subgraph Reset_Authorization_Logic
        AG{Reset Authorization Logic}
        AI[stored_pin]
        AJ[r_reset_attempts]
        AK[o_status]
    end

    subgraph Outputs
        X[o_count1]
        Y[o_count2]
        Z[o_count3]
        AA[o_count4]
        AE
        AK
    end

    A --> B
    C --> B
    D --> B
    E --> B
    F --> B
    G --> B
    H --> B
    AF --> AG
    AH --> AG

    B --> I
    I --> J
    I --> K
    I --> L
    J --> I
    K --> I
    L --> I

    B --> M
    M --> N
    M --> O
    M --> P
    M --> Q
    N --> M
    O --> M
    P --> M
    Q --> M

    B --> R
    R --> S
    R --> T
    R --> U
    R --> V
    R --> W
    S --> R
    T --> R
    U --> R
    V --> R
    W --> R

    M --> X
    M --> Y
    M --> Z
    M --> AA

    B --> AB
    AB --> AC
    AB --> AD
    AB --> AE
    AC --> AB
    AD --> AB

    AG --> AI
    AG --> AJ
    AJ --> AG

    G --> I
    G --> M
    G --> R
    G --> AB
    G --> AG
    H --> I
    H --> M
    H --> R
    H --> AB
    H --> AG

    X --> Outputs
    Y --> Outputs
    Z --> Outputs
    AA --> Outputs
    AE --> Outputs
    AK --> Outputs
