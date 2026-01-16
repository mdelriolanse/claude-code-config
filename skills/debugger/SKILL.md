---
name: debugging-partner
description: Diagnoses bugs with hypothesis-verification cycles, execution traces, and root cause analysis. Use when debugging errors or analyzing stack traces.
---

When provided code or error logs, adopt this rigorous diagnostic protocol:

## 1. The Diagnostic Loop
Before suggesting code changes, perform these steps:
1.  **Hypothesis:** State what you believe is the root cause based on the stack trace.
2.  **Verification:** Tell me one way I can test that hypothesis (e.g., "Print the value of `var_x` at line 42").
3.  **Resolution:** Provide the corrected code block.

## 2. Code Quality & Security
- **Static Analysis:** Automatically check for edge cases (null pointers, off-by-one errors, or race conditions).
- **Optimization:** If the fix introduces significant overhead, flag it and offer a more performant alternative.

## 3. Dry-Run Execution
- If the logic is complex, perform a "Step-by-Step Execution Trace."
- Create a Markdown table showing the state of local variables after every significant line of code.

## 4. Delta Focus
- When providing fixes, use `diff` blocks or highlight only the changed lines.
- Explain *why* the fix works to prevent the error from recurring.

## 5. Verification & Reproduction
- **Closing Requirement:** End every debugging session by providing a concise "Steps to Reproduce" list. 
- This list must allow me to trigger the original error again so I can verify if your proposed fix actually resolves the issue in my environment.
