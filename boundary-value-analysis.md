# Boundary Value Analysis (BVA)

## Notes
- BVA focuses on **testing the edges** of input ranges.
- Test cases are selected as: **min-1, min, min+1, max-1, max, max+1**

---

## Scenario 1 – Password Length Validation

### Requirement
The system must allow users to create passwords between 9 and 15 characters inclusive.

### Test Scenario
Validate that the system correctly handles boundary values for password length.

### Valid Range
- Minimum length: 9
- Maximum length: 15

### Test Cases

| Test Case | Input (Password Length) | Expected Result |
|-----------|------------------------|----------------|
| TC01      | 8                      | Rejected       |
| TC02      | 9                      | Accepted       |
| TC03      | 10                     | Accepted       |
| TC04      | 14                     | Accepted       |
| TC05      | 15                     | Accepted       |
| TC06      | 16                     | Rejected       |

### Coverage
- Tested values: 8, 9, 10, 14, 15, 16
- Ensures validation logic correctly handles values below minimum, at minimum, within range, at maximum, and above maximum.

---

## Scenario 2 – Ticket Price Validation

### Requirement
The system must allow users to purchase tickets with prices between 50 and 500 TL inclusive.

### Test Scenario
Validate that the system correctly handles boundary values for ticket prices.

### Valid Range
- Minimum price: 50
- Maximum price: 500

### Test Cases

| Test Case | Input (Price) | Expected Result |
|-----------|---------------|----------------|
| TC01      | 49            | Rejected       |
| TC02      | 50            | Accepted       |
| TC03      | 51            | Accepted       |
| TC04      | 499           | Accepted       |
| TC05      | 500           | Accepted       |
| TC06      | 501           | Rejected       |

### Coverage
- Tested values: 49, 50, 51, 499, 500, 501
- Ensures validation logic correctly handles values below minimum, at minimum, within range, at maximum, and above maximum.
