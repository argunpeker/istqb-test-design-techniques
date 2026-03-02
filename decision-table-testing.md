# Decision Table Testing (DT)

## Notes
- Decision Table Testing is used to test **different combinations of inputs and their corresponding outputs**.
- Especially useful when a system has **multiple conditions that affect outcomes**.
- Each combination of conditions should ideally be covered by a test case.

---

## Scenario 1 – Login System with Two-Factor Authentication

### Requirement
The system must allow users to log in only if:
1. The username and password are correct.
2. The 2FA code is valid (if enabled).

### Test Scenario
Validate all combinations of username/password and 2FA input to ensure correct login behavior.

### Conditions
| Condition ID | Condition Description                    |
|--------------|------------------------------------------|
| C1           | Username & Password correct? (Yes/No)    |
| C2           | 2FA code valid? (Yes/No)                 |

### Actions
| Action ID | Action Description      |
|-----------|-------------------------|
| A1        | Login allowed           |
| A2        | Login rejected          |

### Decision Table

| Rule | C1 | C2 | Action |
|------|----|----|--------|
| R1   | Y  | Y  | A1     |
| R2   | Y  | N  | A2     |
| R3   | N  | Y  | A2     |
| R4   | N  | N  | A2     |

### Test Cases

| Test Case | Conditions (C1, C2) | Expected Result |
|-----------|--------------------|----------------|
| TC01      | Y, Y               | Login allowed  |
| TC02      | Y, N               | Login rejected |
| TC03      | N, Y               | Login rejected |
| TC04      | N, N               | Login rejected |

### Coverage
- Covers all combinations of conditions.
- Ensures that the login system correctly handles valid and invalid username/password with/without valid 2FA.
