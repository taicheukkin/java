
# Summary of Mortgage Calculator Project

## Overview
In this section, we revisit the mortgage calculator built in the first part of the series. The source code for this project is included in a zip file provided earlier in the course.

## Running the Program
When running the mortgage calculator, users need to answer three key questions:
1. **Principal Amount**: The amount of money to borrow, which must be between $1,000 and $1,000,000. For example:
   - If a user inputs an invalid value like 0 or -1, an error message will be displayed.
   - Valid input example: $100,000.

2. **Annual Interest Rate**: The interest rate (e.g., 4%).

3. **Loan Term**: The duration for repayment (e.g., 10 years).

### Output
- **Monthly Payment**: The program calculates and displays the monthly payments.
- **Payment Schedule**: A breakdown of the remaining balance each month, showing how it decreases to $0 over the loan term.

## Code Review
The initial implementation of the mortgage calculator is procedural, lacking encapsulation and abstraction:
- **Unrelated Methods**: The code contains several unrelated methods such as:
  - `printPaymentSchedule()`: Responsible for outputting to the console.
  - `readNumber()`: Reads input values.
  - `calculateBalance()`: Calculates remaining balances.

### Issues Identified
- **Lack of Encapsulation**: There are no classes to encapsulate related data and behaviors.
- **Procedural Code**: The code consists of methods that call each other without a clear structure.

## Refactoring Goals
The goal is to refactor the code towards an object-oriented design without changing the functionality. This involves:
- Changing the structure of the code while maintaining its behavior.
- Extracting classes that represent related concepts (e.g., `Mortgage`, `PaymentSchedule`).

### Practice Opportunity
You are encouraged to treat this as an opportunity to practice the concepts learned in the last section:
- Spend 20-30 minutes refactoring the code.
- Extract necessary classes and come back to compare your solution with the provided approach.

## Conclusion
Refactoring the mortgage calculator toward an object-oriented design will enhance code maintainability and readability. This exercise is crucial for mastering object-oriented programming concepts.
```

This summary outlines the key elements of the mortgage calculator project, highlights the need for refactoring, and encourages hands-on practice.
