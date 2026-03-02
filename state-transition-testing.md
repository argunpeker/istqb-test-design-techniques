# State Transition Testing (STT)

## Notes
- State Transition Testing is used when system behavior **depends on its current state**.  
- Focuses on **valid state transitions** and ensures **invalid transitions are handled properly**.  
- Useful for systems with **multiple states and events**, e.g., login, payment, workflow.

---

## Scenario 1 – ATM Withdrawal

### Requirement
The ATM system must allow cash withdrawal only if the account is in an **Active** state and has sufficient balance.  
The system has the following states:
- **Active**  
- **Overdrawn**  
- **Locked**  

### Test Scenario
Validate state transitions based on account state and withdrawal attempt.

### States & Events

| Current State | Event                | Next State        |
|---------------|--------------------|-----------------|
| Active        | Withdraw ≤ Balance | Active          |
| Active        | Withdraw > Balance | Overdrawn       |
| Active        | Lock Account       | Locked          |
| Overdrawn     | Deposit             | Active          |
| Overdrawn     | Lock Account        | Locked          |
| Locked        | Unlock Account      | Active          |
| Locked        | Withdraw             | Locked (Rejected) |

---

### Test Cases

| Test Case | Current State | Event            | Expected Result / Next State |
|-----------|---------------|----------------|-----------------------------|
| TC01      | Active        | Withdraw 100   | Active (success)            |
| TC02      | Active        | Withdraw 1000  | Overdrawn                   |
| TC03      | Active        | Lock Account   | Locked                      |
| TC04      | Overdrawn     | Deposit 500    | Active                      |
| TC05      | Overdrawn     | Lock Account   | Locked                      |
| TC06      | Locked        | Unlock Account | Active                      |
| TC07      | Locked        | Withdraw 100   | Locked (Rejected)           |

### Coverage
- All valid and invalid state transitions are covered.  
- Ensures system correctly handles withdrawals, deposits, locking, and unlocking.  
- Demonstrates proper state-dependent behavior of the ATM system.
