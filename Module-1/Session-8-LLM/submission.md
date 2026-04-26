1. Design Note
It is a bad idea to do all calculations inside the LLM because LLMs have limitations in numerical accuracy, consistency, and handling structured data at scale. With 80 rows, errors like incorrect sums or missed conditions (hours > 48) can occur. Instead, Python code execution should be used to compute gross pay and totals reliably. The LLM should then interpret results, explain insights, and format the final output for the user. This separation ensures accuracy (via tools) and clarity (via LLM reasoning and communication).

2. Think-Stage Prompt
Role: You are an AI planning assistant.
Context: The user uploaded a CSV file with columns: employee_id, hours_worked, hourly_rate. Sample: [CSV_SAMPLE]. A Python tool is available for computation.
Task: Generate Python code to calculate:

Gross pay per row (hours_worked × hourly_rate)
Total gross pay
Flag rows where hours_worked > 48

Ensure the code reads the CSV, performs calculations, and outputs a structured result (table + summary).

Output Format:

Step-by-step plan (brief)
Python code only (clean and executable)

Do not explain results; only prepare the computation step.

3. What Can Still Go Wrong?
A possible failure is incorrect or malformed CSV input (e.g., missing columns or wrong data types), causing code errors or wrong calculations.
Mitigation: Add a data validation step before execution (check column names, types, and missing values) and handle errors gracefully.