# CI/CD Github Actions Workflow - Documentation

> Continuous Integration/Continuous Deployment (CI/CD) is a software engineering practice that involves continuously building, testing, and deploying code changes to an application. GitHub Actions is a CI/CD tool that automates these processes within a GitHub repository.

*Example of GitHub Actions workflow that demonstrates the CI/CD process:-*

```
on:
  push:
    branches:
      - main

    paths: 

    - 'factorial.py' 

    - 'lint.py' 
 

 jobs: 

  build: 

    runs-on: ubuntu-latest

    steps: 

    - uses: actions/checkout@v2 

    - name: Set up Python 3.8 

      uses: actions/setup-python@v2 

      with: 

        python-version: 3.8 

    - name: Install dependencies 

      run: | 

        python -m pip install --upgrade pip 

        pip install pylint 

     - name: Lint with pylint 

      run: | 


        python lint.py 
```

This workflow will:
---
* Trigger on any push to the `main`/`master` branch
* Run on an Ubuntu / windows environment
* Checkout the code from the repository
* Install dependencies using npm
* Run tests using npm
* Build the application using npm
* Deploy the application to Heroku using the Heroku Actions plugin

#### To use this workflow in our own repository, we can create a `.github/workflows` directory and save this file as a `.yml` file within it. Then, commit and push our changes to the repository. Once pushed, GitHub Actions will automatically detect the workflow and begin executing it on every push to the `main` or `master` branch.