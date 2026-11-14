# Experiment 1.A (`exp1.pdf`): Employee Data Display Using Python

## 🎯 Aim

To collect employee details, validate inputs, and calculate gross and net salary using Python.

## 📊 Payroll Calculation Rules

The program computes employee allowances, gross pay, tax deductions, and net salary based on the entered **Basic Pay**:

* **House Rent Allowance ($\text{HRA}$):** $15\%$ of Basic Pay ($0.15 \times \text{Basic}$)
* **Dearness Allowance ($\text{DA}$):** $10\%$ of Basic Pay ($0.10 \times \text{Basic}$)
* **Gross Salary:** $\text{Basic} + \text{HRA} + \text{DA}$
* **Tax Deducted:** $8\%$ of Gross Salary ($0.08 \times \text{Gross}$)
* **Net Salary:** $\text{Gross} - \text{Tax}$

## ⚙️ Algorithm

1. **Start** the program.
2. **Read Employee Details** from the user:
   * Input `name` (String) for the employee's full name.
   * Input `emp_id` (String) for the employee's identification number.
   * Input `basic` (Float) for the employee's basic salary.
3. **Validate Input**:
   * Ensure `basic` is a valid numeric value and check if `basic < 0`. If invalid or negative, display an appropriate error message and terminate the program.
4. **Compute Allowances**:
   * Calculate House Rent Allowance: $\text{HRA} = 0.15 \times \text{basic}$.
   * Calculate Dearness Allowance: $\text{DA} = 0.10 \times \text{basic}$.
5. **Compute Gross Salary**:
   * Calculate total earnings before deductions: $\text{Gross Salary} = \text{basic} + \text{HRA} + \text{DA}$.
6. **Compute Tax Deduction**:
   * Calculate income tax at $8\%$ of gross pay: $\text{Tax} = 0.08 \times \text{Gross Salary}$.
7. **Compute Net Salary**:
   * Calculate take-home pay: $\text{Net Salary} = \text{Gross Salary} - \text{Tax}$.
8. **Display Formatted Payroll Report**:
   * Print a structured summary displaying `name`, `emp_id`, `basic`, `HRA`, `DA`, `Gross Salary`, `Tax`, and `Net Salary` formatted to two decimal places.
9. **Stop** the program.

### 📝 Pseudocode

```text
BEGIN
    INPUT name, emp_id, basic
    CONVERT basic TO FLOAT

    IF basic < 0 THEN
        PRINT "Error: Basic Pay cannot be negative."
        EXIT
    ENDIF

    hra ← 0.15 * basic
    da ← 0.10 * basic
    gross ← basic + hra + da
    tax ← 0.08 * gross
    net ← gross - tax

    PRINT "--- Employee Salary Report ---"
    PRINT "Employee Name :", name
    PRINT "Employee ID   :", emp_id
    PRINT "Basic Pay     :", FORMAT(basic, 2)
    PRINT "HRA (15%)     :", FORMAT(hra, 2)
    PRINT "DA (10%)      :", FORMAT(da, 2)
    PRINT "Gross Salary  :", FORMAT(gross, 2)
    PRINT "Tax Deducted  :", FORMAT(tax, 2)
    PRINT "Net Salary    :", FORMAT(net, 2)
END
```

## 🛠️ Functions and Methods Used

| Category | Function / Construct | Purpose / Description |
| :--- | :--- | :--- |
| **User Input** | `input()` & `.strip()` | Reads and trims employee name, ID, and basic salary from standard input |
| **Type Conversion & Validation** | `float()` & `try-except` | Converts the basic pay input string into a float and handles non-numeric/negative input errors |
| **Output Formatting** | `print()` & f-strings (`f"{val:.2f}"`) | Displays the structured employee payroll report rounded to two decimal places |

## 💻 Program / Code

```python
# Employee Payroll Calculation

def generate_payroll():
    name = input("Enter Employee Name: ").strip()
    emp_id = input("Enter Employee ID: ").strip()

    try:
        basic = float(input("Enter Basic Pay: "))
        if basic < 0:
            print("Error: Basic Pay cannot be negative.")
            return
    except ValueError:
        print("Error: Please enter a valid numeric value for Basic Pay.")
        return

    # Allowance and Deduction Calculations
    hra = 0.15 * basic
    da = 0.10 * basic
    gross = basic + hra + da
    tax = 0.08 * gross
    net = gross - tax

    # Formatted Output Report
    print("\n--- Employee Salary Report ---")
    print(f"Employee Name : {name}")
    print(f"Employee ID   : {emp_id}")
    print(f"Basic Pay     : {basic:.2f}")
    print(f"HRA (15%)     : {hra:.2f}")
    print(f"DA (10%)      : {da:.2f}")
    print(f"Gross Salary  : {gross:.2f}")
    print(f"Tax Deducted  : {tax:.2f}")
    print(f"Net Salary    : {net:.2f}")

if __name__ == "__main__":
    generate_payroll()
```

## 🖥️ Sample Input & Output

```text
Enter Employee Name: Divya
Enter Employee ID: 12617
Enter Basic Pay: 30000

--- Employee Salary Report ---
Employee Name : Divya
Employee ID   : 12617
Basic Pay     : 30000.00
HRA (15%)     : 4500.00
DA (10%)      : 3000.00
Gross Salary  : 37500.00
Tax Deducted  : 3000.00
Net Salary    : 34500.00
```

## ✅ Result

The program successfully accepts and validates employee details, calculates allowances and deductions, and displays a well-formatted salary report.

## 🚀 How to Run

1. Ensure Python 3 is installed on your system (no external packages required).
2. Run the script from your terminal:
   ```bash
   python exp1_employee_payroll.py
   ```