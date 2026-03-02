# Equivalence Partitioning (EP)

## Notes
- EP divides input ranges into **equivalent partitions**.
- Testing **1 value per partition** is enough, as all values in the same partition are expected to behave the same.
- Both **valid and invalid partitions** should be considered.

---

## Scenario 1 – Password Length Validation

### Requirement
The system must allow users to create passwords between 9 and 15 characters inclusive.

### Test Scenario
Validate that the system correctly handles valid and invalid partitions for password length.

### Partitions
- **Valid Partition:** 9–15 characters  
- **Invalid Partition (Below Minimum):** <9 characters  
- **Invalid Partition (Above Maximum):** >15 characters  

### Test Cases

| Test Case | Input (Password Length) | Expected Result |
|-----------|------------------------|----------------|
| TC01      | 10                     | Accepted       |
| TC02      | 8                      | Rejected       |
| TC03      | 16                     | Rejected       |

### Coverage
- Covers **all partitions** with minimal test cases.
- Ensures system correctly validates lengths within, below, and above allowed range.

---

## Scenario 2 – Ticket Price Validation

### Requirement
The system must allow users to purchase tickets with prices between 50 and 500 TL inclusive.

### Test Scenario
Validate that the system correctly handles valid and invalid partitions for ticket prices.

### Partitions
- **Valid Partition:** 50–500 TL  
- **Invalid Partition (Below Minimum):** <50 TL  
- **Invalid Partition (Above Maximum):** >500 TL  

### Test Cases

| Test Case | Input (Price) | Expected Result |
|-----------|---------------|----------------|
| TC01      | 100           | Accepted       |
| TC02      | 49            | Rejected       |
| TC03      | 501           | Rejected       |

### Coverage
- Covers all valid and invalid partitions using minimal test cases.
- Demonstrates that system handles values below minimum, within range, and above maximum.
