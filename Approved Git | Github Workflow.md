# **Gitflow/Git Workflow**


## **Workflow Overview**

1.  Develop and Main Branches:

    -   Gitflow uses two primary branches:

        -   **Main Branch**: Stores the official release history.

        -   **Develop Branch**: Serves as an integration branch for
            features.
    -   Developers create feature branches from the develop branch.

2.  **Feature Branches**:

    -   Feature branches are created for specific features or changes.

    -   Developers work on these branches independently.

    -   Once a feature is complete, it is merged back into the develop
        branch.

3.  **Release Branches**:

    -   Release branches are created to prepare for a new release.

    -   Bug fixes and minor adjustments are made on the release branch.

    -   Once ready, the release branch is merged into both develop and
        main branches.

4.  **Hotfix Branches**:

    -   Hotfix branches address critical issues in the production code.

    -   They are created from the main branch.

    -   Once the hotfix is complete, it is merged into both develop and
        main branches.

## **Step-by-Step Implementation**

1.  **Initialize Gitflow**:

    -   Create an empty develop branch locally and push it to the
        server:

        `git branch develop`
        
         `git push -u origin develop`

2.  **Feature Development**:

    -   Create a feature branch for a specific task:

    -   `git checkout -b feature/my-feature develop`

    -   Work on the feature, commit changes, and push to the remote
        repository.

    -   When complete, merge the feature branch into develop:
       
        `git checkout develop`

        `git merge \--no-ff feature/my-feature`

3.  **Release Preparation**:

    -   Create a release branch:

         `git checkout -b release/1.0 develop`

    -   Perform any necessary bug fixes or adjustments.

    -   Merge the release branch into both develop and main:

        `git checkout develop`

         `git merge \--no-ff release/1.0`

         `git checkout main`

         `git merge \--no-ff release/1.0`  
4.  **Hotfix Handling**:

    -   Create a hotfix branch: 

        `git checkout -b hotfix/fix-bug main`

    -   Fix the critical issue.

    -   Merge the hotfix branch into both develop and main:

        `git checkout develop`

         `git merge \--no-ff hotfix/fix-bug`

         `git checkout main`

         `git merge \--no-ff hotfix/fix-bug`

