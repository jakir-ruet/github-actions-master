## More About Me – [Take a Look!](http://www.mjakaria.me)

### [GitHub Actions](https://docs.github.com/en/actions/about-github-actions/understanding-github-actions)

GitHub Actions is a automation (CI/CD) service by GitHub. It's automated all kind of repository related process & actions that will run one or more jobs. Workflows are defined in the `.github/workflows` directory in a repository. It's has two main areas

- Continuous Integration (CI/CD) - Code `Test`, `Build`, `Deployment`, new app release.
- Source Code Management (SCM) - Automate `code reviews`, `issues management` etc.

 It lets you automate workflows like `testing code`, `building applications`, `deploying to servers`, `sending notifications`, and more — all triggered by GitHub events like `push`, `pull` `request`, `release`, etc.

#### The `three` main building blocks in GitHub Actions are

1. **[Workflows](https://docs.github.com/en/actions/about-github-actions/understanding-github-actions)**
2. **[Jobs](https://docs.github.com/en/actions/about-github-actions/understanding-github-actions)**
3. **[Steps](https://docs.github.com/en/actions/about-github-actions/understanding-github-actions)**

1. Workflows
   A workflow is a set of automated processes that are triggered based on specific events in your GitHub repository. Common events include pushes to the repository, pull requests, or the creation of new issues.
   - A workflow is a YAML file that defines what should happen (CI/CD logic).
   - It lives in `.github/workflows/` in your repo.
   - You can have multiple workflows for different purposes (`test`, `deploy`, `release`).

```yaml
name: Deploy Website
on: push
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - run: echo "Deploying site..."
```

2. Jobs
   A job is a set of steps in a workflow that is executed on the same runner. Each step is either a shell script that will be executed, or an action that will be run.
   - A job is a set of steps that run in the same runner (environment).
   - Jobs can run in parallel or sequentially.
   - Each job runs on its own VM or container.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - run: echo "This is a job"
```

3. Steps
   - Steps are individual tasks inside a job (`checkout code`, `run tests`).
   - They can run commands or use actions (reusable pieces of code).

```yaml
steps:
  - name: Checkout Code
    uses: actions/checkout@v3
  - name: Install Dependencies
    run: npm install
```

#### Others building blocks in GitHub Actions are

##### Trigger

A trigger is the condition that starts the workflow when the event occurs.

```yaml
on:
  push:
    branches:
      - main
```

> Here `push` is the event.

##### Events

An event is a specific activity in a repository that triggers a workflow run.

- `push` – When someone pushes to the repo.
- `pull_request` – When a PR is opened or updated.
- `schedule` – Runs on a cron schedule.
- `workflow_dispatch` – Manual trigger via GitHub UI

| Component        | Meaning              |
| ---------------- | -------------------- |
| `push`           | Event                |
| `branches: main` | Condition            |
| Entire block     | Trigger for workflow |

##### Actions

An Action is a reusable unit of code that performs a specific task inside a workflow.

```yaml
name: CI Pipeline

on: push

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v4
```

| Component             | Meaning                    |
| --------------------- | -------------------------- |
| `steps`               | Individual tasks           |
| `uses`                | Calls an **action**        |
| `actions/checkout@v4` | A ready-made GitHub Action |

##### Runners

Arunner is a `virtual machine` or `physical server` that runs the jobs defined in a GitHub Actions workflow.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
```

| Keyword         | Meaning                    |
| --------------- | -------------------------- |
| `runs-on`       | Specifies the runner       |
| `ubuntu-latest` | GitHub-hosted Linux runner |

###### Types of Runners

| Type                     | Description                                |
| ------------------------ | ------------------------------------------ |
| **GitHub-hosted runner** | Managed by GitHub (Ubuntu, Windows, macOS) |
| **Self-hosted runner**   | Your own server or machine                 |

## With Regards, `Jakir`

[![LinkedIn][linkedin-shield-jakir]][linkedin-url-jakir]
[![Facebook-Page][facebook-shield-jakir]][facebook-url-jakir]
[![Youtube][youtube-shield-jakir]][youtube-url-jakir]

### Wishing you a wonderful day! Keep in touch

<!-- Personal profile -->

[linkedin-shield-jakir]: https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white
[linkedin-url-jakir]: https://www.linkedin.com/in/jakir-ruet/
[facebook-shield-jakir]: https://img.shields.io/badge/Facebook-%231877F2.svg?style=for-the-badge&logo=Facebook&logoColor=white
[facebook-url-jakir]: https://www.facebook.com/jakir.ruet/
[youtube-shield-jakir]: https://img.shields.io/badge/YouTube-%23FF0000.svg?style=for-the-badge&logo=YouTube&logoColor=white
[youtube-url-jakir]: https://www.youtube.com/@mjakaria-ruet/featured
