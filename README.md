# git_assignment_HeroVired

# Q1: CalculatorPlus Application

## Objective
Enhance the CalculatorPlus Python application by:
- Adding a square root feature
- Handling a critical bug
- Following proper Git workflow practices

## Steps Performed
1. **Repository Setup**
   - Created private GitHub repository: `git_assignment_HeroVired`
   - Cloned repository locally
   - Added initial `README.md`

2. **Development Branch Setup**
   - Created `dev` branch
   - Added base application code in `CalculatorPlus.py` with:
     - Addition
     - Subtraction
     - Multiplication
     - Division

3. **Initial Release (v1.0)**
   - Merged `dev` branch into `main`
   - Tagged release: `v1.0`

4. **Feature Development - Square Root**
   - Created feature branch: `feature/sqrt`
   - Implemented:
     ```python
     def square_root(self, x):
         return math.sqrt(x)
     ```
   - Uncommented and tested square root functionality

5. **Bug Fix (Hotfix)**
   - Created branch: `hotfix/divide-error-fix`
   - Fixed divide function:
     ```python
     def divide(self, a, b):
         if b == 0:
             raise ValueError("Cannot divide by zero.")
         return a / b
     ```

6. **Pull Request Workflow**
   - Created PR: `hotfix/divide-error-fix → dev`
   - Merged after review
   - Updated feature branch: `git pull origin dev`
   - Created PR: `feature/sqrt → main`
   - Requested code review and applied feedback

7. **Final Integration**
   - Merged `feature/sqrt` into `dev`
   - Tested application in `dev`
   - Merged `dev → main`

8. **Final Release (v2.0)**
   - Tagged release: `v2.0`

9. **Collaboration**
   - Added classmate as collaborator
   - Participated in peer code review

---

# Q2: Git LFS (Large File Storage)

## Objective
Handle large binary files efficiently using Git LFS.

## Steps Performed
1. **LFS Setup**
   - Installed Git LFS: `git lfs install`

2. **Created LFS Branch**
   - `git checkout -b lfs`

3. **Configured Tracking**
   - `git lfs track "*.zip"`

4. **Added Large File**
   - Added file: `dummyfile01.zip` (>200MB)
   - Committed and pushed to repository

5. **Verification**
   - Cloned repository on another system
   - Installed Git LFS
   - Executed: `git lfs pull`
   - Verified file using: `git lfs ls-files`

6. **Issue Faced & Resolution**
   - Issue: Switching branches due to `.gitattributes`
   - Resolution:
     - `git stash --include-untracked`
     - Observed delay during checkout due to large file download
     - Used:
       ```bash
       GIT_LFS_SKIP_SMUDGE=1 git checkout lfs
       git lfs pull
       ```

---

# Q3: Geometry Calculator (Git Stash)

## Objective
Implement multiple features using Git stash while switching branches.

## Steps Performed
1. **Base Branch Creation**
   - `git checkout -b geometry-calculator`
   - Created `GeometryCalculator.py`
   - Added base functions:
     - Circle area
     - Rectangle area

2. **Circle Feature**
   - `git checkout -b feature/circle-area`
   - Implemented circle area logic
   - Stashed incomplete changes: `git stash`

3. **Rectangle Feature**
   - `git checkout -b feature/rectangle-area`
   - Implemented rectangle logic
   - Stashed changes: `git stash`

4. **Resume Circle Feature**
   - `git checkout feature/circle-area`
   - `git stash pop`
   - Completed implementation
   - Committed and pushed changes

5. **Resume Rectangle Feature**
   - `git checkout feature/rectangle-area`
   - `git stash pop`
   - Completed implementation
   - Committed and pushed changes

6. **Pull Requests**
   - Created PRs:
     - `feature/circle-area → dev`
     - `feature/rectangle-area → dev`
   - Merged after review

7. **Final Merge**
   - `git checkout dev`
   - `git pull dev`
   - `git checkout main`
   - `git merge dev`
   - `git push origin main`
