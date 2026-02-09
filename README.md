[![Python CI Pipeline](https://github.com/MaryamZulfiqar307/Task-1/actions/workflows/ci.yml/badge.svg)](https://github.com/MaryamZulfiqar307/Task-1/actions/workflows/ci.yml)

# Lab: Intro to Continuous Integration (CI)

This lab introduces the basics of **Continuous Integration (CI)** using **GitHub Actions**. You will observe how automated pipelines run on every code change, catch bugs early, and ensure code quality.

---

## 🏁 Step 1: Setup

1. Open your GitHub repository.
2. Click on the **Actions** tab.
3. You should see a workflow run listed (triggered by your initial fork or push).
4. Click on the workflow run to view the details.
5. Ensure that all steps have a **green checkmark ✅**, indicating a successful run.

This confirms that the CI pipeline is correctly set up.

---

## 🧪 Step 2: The “Happy Path”

In this step, you will make a harmless change and observe a successful CI run.

1. Open the file `src/calculator.py`.
2. Add a small comment to the file, for example:
   ```python
   # This is a change
   ```
3. Commit and push the change to GitHub.
4. Go to the **Actions** tab immediately.
5. Watch the pipeline start automatically.

### Observe:
- Python is set up.
- Dependencies are installed.
- Tests are executed.

The workflow should complete successfully with a **green checkmark ✅**.

---

## 💥 Step 3: Break the Build!

Now, you will intentionally introduce a bug to see how CI detects errors.

1. Open `src/calculator.py`.
2. Modify the `add` function so that it is incorrect:
   ```python
   def add(x, y):
       return x - y  # This is a bug!
   ```
3. Commit and push this change to GitHub.
4. Navigate to the **Actions** tab.

### Observe:
- The pipeline will fail.
- A **red X ❌** will appear on the workflow run.
- Click into the failed run and locate the failing test, typically `test_add`.

This demonstrates how CI catches bugs before they reach production.

---

## 🚑 Step 4: Fix the Build

Finally, you will fix the bug and restore the pipeline to a healthy state.

1. Revert the change in `src/calculator.py`:
   ```python
   def add(x, y):
       return x + y
   ```
2. Commit and push the fix.
3. Go back to the **Actions** tab.

### Verify:
- The workflow runs again automatically.
- All steps pass successfully.
- The build status returns to **green ✅**.

---

## ✅ Outcome

By completing this lab, you have:
- Observed how CI pipelines are triggered automatically.
- Seen a successful build (happy path).
- Experienced a failing build due to a bug.
- Fixed the issue and restored a passing build.

This is the core idea of Continuous Integration: **fast feedback and early bug detection**.

