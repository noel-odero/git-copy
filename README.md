# Gym Git Exercise Solutions

## Bundle 1

### Exercise 1


#### Step 1: Create a project folder and initialize Git
```bash
mkdir gym-git-exercise
cd gym-git-exercise
git init
```

#### Step 2: Make changes to the project
```bash
echo "git exercises" > README.md

```

#### Step 3: Rename the branch from `master` to `main` (or vice versa and back)
```bash
git branch -m master main
git branch -m main master
git branch -m master main
```

#### Step 4: Stage changes and commit them
```bash
git add .
git commit -m "Initial commit"
```

#### Step 5: Create a GitHub repository and connect it to the project
```bash
git remote add origin github-link
git push -u origin main
```

#### Step 6: Create a new branch `dev`
```bash
git checkout -b dev
```

#### Step 7: From `dev`, create another branch `test`
```bash
git checkout -b test
```

#### Step 8: Go back to the `dev` branch and delete the `test` branch
```bash
git checkout dev / git switch dev
git branch -d test
```

### Exercise 2

#### Step 1: Create a new `home.html` file, add changes, and save them
```bash
echo "<h1>Home Page</h1>" > home.html
```

#### Step 2: Stash save the current changes
```bash
git add home.html
git stash save "Home page changes"
```

#### Step 3: Repeat the process for `about.html`
```bash
echo "<h1>About Us</h1>" > about.html
git add about.html
git stash save "About page changes"
```

#### Step 4: Repeat the process for `team.html`
```bash
echo "<h1>Meet team 2</h1>" > team.html
git add team.html
git stash save "Team page changes"
```

#### Step 5: Restore the changes of the `about.html` page using `stash pop`
```bash
git stash pop "stash@{1}"
```
#### Step 6: Restore the `home.html` page changes using `stash pop` with an index
```bash
git stash pop "stash@{2}"
```

#### Step 7: Commit the current changes and push them
```bash
git add .
git commit -m "changes"
git push
```

#### Step 8: Restore the changes of the `team.html` page using `stash pop`
```bash
git stash pop "stash@{0}"
```

#### Step 9: Reset the current changes using `git reset` to go back without the `team.html` page
```bash
git reset HEAD .
git checkout -- team.html
```

## Bundle 2
### Exercise 1
### Create a New Branch and Add Changes
1. **Create a new branch:**
    ```bash
    git checkout -b ft/bundle-2
    ```
2. **Create a new page (`services.html`):**
    ```bash
    touch service.html
    ```
3. **Add content to `services.html`:**
    ```html

        <h1>Our Services</h1>
    ```
4. **Stage the new file:**
    ```bash
    git add services.html
    ```
5. **Commit the changes:**
    ```bash
    git commit -m "ci: services"
    ```
### Push and Create a Pull Request
6. **Push the branch to GitHub:**
    ```bash
    git push origin ft/bundle-2
    ```

### Exercise 2

1. **Checkout the `main` branch and pull the latest changes:**
    ```bash
    git checkout main
    git pull origin main
    ```
2. **Create a new branch `ft/service-redesign`:**
    ```bash
    git checkout -b ft/service-redesign
    ```
3. **Add new changes to `services.html` and commit them:**
    ```bash

    git add services.html
    git commit -m "Redesign services.html page"
    ```
4. **Push the branch to GitHub:**
    ```bash
    git push origin ft/service-redesign
    ```
5. **Create a Pull Request for the `ft/service-redesign` branch:**
    - Go to GitHub and create a PR.

6. **Go back to the `main` branch and add conflicting changes:**
    ```bash
    git checkout main

    git add services.html
    git commit -m "Update services.html page with new changes"
    git push origin main
    ```
7. **Observe conflicts on the GitHub PR:**
    - Go back to the PR for `ft/service-redesign` and note the conflicts.

8. **Checkout the `ft/service-redesign` branch locally:**
    ```bash
    git checkout ft/service-redesign
    ```
9. **Compare the `ft/service-redesign` branch with `main` using `git diff`:**
    ```bash
    git diff main
    ```
10. **Merge the `main` branch into `ft/service-redesign` and resolve conflicts:**
    ```bash
    git merge main
    # Manually resolved conflicts in service.html
    git add services.html
    git commit -m "Resolve merge conflicts between main and ft/service-redesign"
    ```
11. **Push the resolved branch to GitHub:**
    ```bash
    git push origin ft/service-redesign


## Bundle 3
### Exercise 1


1. **Create a new branch named `ft/team-page`:**
    ```bash
    git checkout -b ft/team-page
    ```

2. **Create a new HTML page named `team.html` and add some changes:**
    - Create the file `team.html` and add desired HTML content.

3. **Commit and push those changes:**
    ```bash
    git add team.html
    git commit -m "Add team.html page"
    git push origin ft/team-page
    ```

4. **Create a new Pull Request for the changes:**
    - Go to your GitHub repository and create a PR from `ft/team-page` to `main`.

5. **Go back to the `main` branch:**
    ```bash
    git checkout main
    ```

6. **Create a new branch named `ft/contact-page`:**
    ```bash
    git checkout -b ft/contact-page
    ```

7. **Go back to the `ft/team-page` branch:**
    ```bash
    git checkout ft/team-page
    ```

8. **With the help of `git log`, look for the last commit and copy its hash:**
    ```bash
    git log --oneline
    ```
    - Copy the hash of the most recent commit

9. **Checkout the `ft/contact-page` branch:**
    ```bash
    git checkout ft/contact-page
    ```

10. **Cherry-pick the last commit from the `ft/team-page` branch:**
    ```bash
    git cherry-pick 6d132c9
    ```

11. **Add new changes for the contact page, commit, and push them:**
    ```bash
    git add contact.html
    git commit -m "Add contact.html page"
    git push origin ft/contact-page
    ```

12. **Create a new PR for the contact page:**
    - Go to your GitHub repository and create a PR from `ft/contact-page` to `main`.

13. **From the `ft/contact-page` branch, create a new branch called `ft/faq-page`:**
    ```bash
    git checkout -b ft/faq-page
    ```

14. **Create a new `faq.html` page and add some changes:**
    - Create the file `faq.html` and add desired content.

15. **Commit and push those changes:**
    ```bash
    git add faq.html
    git commit -m "Add faq.html page"
    git push origin ft/faq-page
    ```

16. **Using `git revert`, revert the changes of the last commit of the `ft/team-page` branch:**

    1. Switch to the `ft/team-page` branch:
        ```bash
        git checkout ft/team-page
        ```

    2. Revert the last commit:
        ```bash
        git revert 6d132c9
        ```

    3. Push the reverted changes:
        ```bash
        git push origin ft/team-page
        ```

17. **Create a new PR for the reverted changes:**


### Exercise 2

1. **Create a new branch from `ft/faq-page` named `ft/home-page-redesign`:**
   ```bash
   git checkout ft/faq-page
   git checkout -b ft/home-page-redesign
   ```

2. **Switch to the `main` branch and make changes:**
   ```bash
   git checkout main
   git add .
   git commit -m "Update main branch with new changes"
   git push origin main
   ```

3. **Switch back to the `ft/home-page-redesign` branch:**
   ```bash
   git checkout ft/home-page-redesign
   ```

4. **Rebase the `ft/home-page-redesign` branch onto `main`:**
   ```bash
   git rebase main
   ```

5. **Add changes to the home page:**
     ```bash
     git add home.html
     git commit -m "Redesign home page"
     ```

6. **Push the changes to the `ft/home-page-redesign` branch:**
   ```bash
   git push origin ft/home-page-redesign
   ```

7. **Create a Pull Request for the changes:**



