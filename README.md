# Digital Time Scheduler Block Diagram

```mermaid
graph TD
    A[Time Scheduler\nInputs: i_task_start, i_task_stop, i_set_time, i_priority, i_reset\nOutputs: o_task_active, o_time_remaining, o_task_complete, o_alert] --> B[State Machine\nStates: IDLE, SETUP, RUNNING, PAUSED, COMPLETE\nRegisters: r_present_state, r_next_state, r_task_duration];
    B --> C[Task Timer\nRegisters: r_timer_count, r_elapsed_time];
    B --> D[Task Queue\nRegisters: r_task1_duration, r_task1_priority, ..., r_queue_count];
    C --> E[Non-Volatile Memory NVM\nRegisters: nvm_task_count, nvm_last_task_duration, nvm_data_valid];
    C --> F[Outputs: o_time_remaining, o_task_complete];
    B --> G[Alert Logic\nComponents: alert_counter, alert_active, o_alert];
    H[Clock and Reset\nSignals: clk, rst] --> A;
    H --> B;
    H --> C;
    H --> D;
    H --> E;
    H --> G;
    A -- Data --> B;
    B -- Data --> C;
    B -- Data --> D;
    C -- Data --> E;
    B -- Data --> G;
    G -- o_alert --> A;
    C -- o_time_remaining, o_task_complete --> A;
    A -- o_task_active --> user;
