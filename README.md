# CI/CD Github Actions Workflow - Documentation

*Example of GitHub Actions workflow that demonstrates the CI/CD process:-*

```
name: CI/CD Workflow

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2
      
      - name: Install dependencies
        run: npm install

      - name: Run tests
        run: npm test

      - name: Build application
        run: npm run build

      - name: Deploy application
        uses: heroku/actions@v3
        with:
          heroku_api_key: ${{ secrets.HEROKU_API_KEY }}
          heroku_app_name: my-app
          heroku_email: my-email@example.com
```

This workflow will:
---
* Trigger on any push to the `main` branch
* Run on an Ubuntu environment
* Checkout the code from the repository
* Install dependencies using npm
* Run tests using npm
* Build the application using npm
* Deploy the application to Heroku using the Heroku Actions plugin

#### To use this workflow in our own repository, we can create a `.github/workflows` directory and save this file as a `.yml` file within it. Then, commit and push our changes to the repository. Once pushed, GitHub Actions will automatically detect the workflow and begin executing it on every push to the `main` or `master` branch.