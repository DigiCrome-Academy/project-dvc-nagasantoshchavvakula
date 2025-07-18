[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/4Cg9amBO)
﻿# DVC-CSV-Tracker: Data Version Control with DVC and Git

This project demonstrates how to use Data Version Control (DVC) in conjunction with Git to manage and track changes in a CSV dataset. This is a fundamental skill for MLOps and data science workflows, ensuring reproducibility and collaboration.

## Project Goal

The primary goal of this project is to set up a DVC-tracked CSV file within a Git repository and demonstrate how to version control data changes.

## Setup Instructions

Follow these steps to set up your project and start tracking your CSV data.

### Step 1: Accept the GitHub Classroom Assignment

1.  Click on the assignment link provided by your instructor.
2.  Accept the assignment, which will create a new private repository for you on GitHub.
3.  Clone the repository to your local machine:
    ```bash
    git clone <YOUR_REPOSITORY_URL>
    cd <YOUR_REPOSITORY_NAME>
    ```

### Step 2: Install DVC

If you haven't already, install DVC on your system. It's recommended to install it within a virtual environment.

```bash
pip install dvc
```
### Step 3: Initialize DVC in Your Repository
Navigate to your project's root directory (the one you just cloned) and initialize DVC.

    ``` 
    dvc init
    ```
This command creates a .dvc directory and modifies .gitignore to include DVC-related files.

Step 4: Create Your CSV Data File
Create a CSV file named data.csv in the root of your repository. This file will be tracked by DVC.

Example data.csv content:

    ```
    id,name,value
    1,alpha,10
    2,beta,20
    3,gamma,30
    ```


### Step 5: Add Your CSV File to DVC
Now, add your data.csv file to DVC. This will create a .dvc file (e.g., data.csv.dvc) that acts as a pointer to the actual data stored in DVC's cache.

    ```
    Bash

    dvc add data.csv
    ```

### Step 6: Commit Changes to Git
The .dvc file is a small text file that Git does track. Commit both the .dvc file and the .gitignore changes to your Git repository.

    ```
    Bash

    git add data.csv.dvc .gitignore
    git commit -m "Initial DVC tracking for data.csv"
    ```


### Step 7: Push Changes to GitHub
Push your committed changes to your remote GitHub repository.

    ```
    Bash

    git push origin main
    ```

### Step 8: Modify and Track Data Changes
Let's simulate a change in your data and track it with DVC.

Modify data.csv. For example, add a new row:

    ```
    Code snippet

    id,name,value
    1,alpha,10
    2,beta,20
    3,gamma,30
    4,delta,40
    ```


Run dvc add again to update the .dvc file. DVC will detect the change and update the pointer.

    ```
    Bash

    dvc add data.csv
    Commit the updated .dvc file to Git.
    ```

    ```
    Bash

    git add data.csv.dvc
    git commit -m "Updated data.csv with new row"
    Push the changes to GitHub.

    Bash

    git push origin main
    ```