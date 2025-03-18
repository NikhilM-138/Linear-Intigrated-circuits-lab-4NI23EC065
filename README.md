```mermaid
graph TD
    A[i_candidate_1] --> B(Voting Machine);
    C[i_candidate_2] --> B;
    D[i_candidate_3] --> B;
    E[i_candidate_4] --> B;
    F[i_voting_over] --> B;
    G[clk] --> B;
    H[rst] --> B;

    B --> I{State Machine};
    I --> J[r_present_state];
    I --> K[r_next_state];
    I --> L[r_hold_count];
    J --> I;
    K --> I;
    L --> I;

    B --> M{Vote Counters};
    M --> N[r_counter_1];
    M --> O[r_counter_2];
    M --> P[r_counter_3];
    M --> Q[r_counter_4];
    N --> M;
    O --> M;
    P --> M;
    Q --> M;

    B --> R{NVM};
    R --> S[nvm_count1];
    R --> T[nvm_count2];
    R --> U[nvm_count3];
    R --> V[nvm_count4];
    R --> W[nvm_data_valid];
    S --> R;
    T --> R;
    U --> R;
    V --> R;
    W --> R;

    M --> X[o_count1];
    M --> Y[o_count2];
    M --> Z[o_count3];
    M --> AA[o_count4];

    B --> AB{Beep Logic};
    AB --> AC[beep_counter];
    AB --> AD[beep_active];
    AB --> AE[o_beep];
    AC --> AB;
    AD --> AB;

    AF[i_reset_pin] --> AG{Reset Authorization Logic};
    AH[i_reset_request] --> AG;
    AG --> AI[stored_pin];
    AG --> AJ[r_reset_attempts];
    AJ --> AG;
    AG --> AK[o_status];

    G --> I;
    G --> M;
    G --> R;
    G --> AB;
    G --> AG;
    H --> I;
    H --> M;
    H --> R;
    H --> AB;
    H --> AG;

    X --> AO[Outputs];
    Y --> AO;
    Z --> AO;
    AA --> AO;
    AE --> AO;
    AK --> AO;
