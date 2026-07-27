# COBOL → Python Conversion & Push — Steps Performed

Repo: `https://github.com/sonalbhatt369-raval/my-first_repo.git`
Branch: `feature/my-first-test-branch`
Local path: `C:\Users\sonal\my-first_repo`

## 1. Fetch remote branches and inspect the feature branch
```bash
git fetch origin
git ls-tree -r origin/feature/my-first-test-branch --name-only
```
Confirmed `src/hello.cob` existed on the branch (along with an unrelated pre-existing
`.github/workflows/cobol_to_python.yml` GitHub Action doing an automated version of
this same conversion).

## 2. Checkout and pull the feature branch locally
```bash
git checkout feature/my-first-test-branch
git pull origin feature/my-first-test-branch
```
Fast-forwarded local branch to bring down `src/hello.cob` and the workflow file.

## 3. Read the COBOL source
`src/hello.cob`:
```cobol
IDENTIFICATION DIVISION.
PROGRAM-ID. HelloWorld.

PROCEDURE DIVISION.
    DISPLAY "Hello, World!".
    STOP RUN.
```

## 4. Convert to Python and write the new file
`src/hello.py`:
```python
print("Hello, World!")
```

## 5. Stage and commit locally (no push yet — held for review)
```bash
git add src/hello.py
git commit -m "Add Python conversion of hello.cob"
```
Commit: `0c9c8a8`, 1 commit ahead of `origin/feature/my-first-test-branch`.

## 6. Developer review
Paused here — confirmed `src/hello.py` was visible at
`C:\Users\sonal\my-first_repo\src\hello.py` and reviewed before pushing.

## 7. Push to the remote feature branch
```bash
git push origin feature/my-first-test-branch
```
Result: `85b70d5..0c9c8a8  feature/my-first-test-branch -> feature/my-first-test-branch`

`src/hello.py` is now on `feature/my-first-test-branch` on GitHub.
