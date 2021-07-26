## Welcome to "Hello World" with GitHub Actions

A brief overview of the workflow file used in this repo

**name:** A workflow for my Hello World file gives your workflow a name. This name appears on any pull request or in the Actions tab. The name is especially useful when there are multiple workflows in your repository.

**on:** push indicates that your workflow will execute anytime code is pushed to your repository, using the push event.

**jobs:** is the base component of a workflow run

**build:** is the identifier we're attaching to this job

**name:** is the name of the job, this is displayed on GitHub when the workflow is running

**runs-on:** defines the type of machine to run the job on. The machine can be either a GitHub-hosted runner or a self-hosted runner.

**steps:** the linear sequence of operations that make up a job

**uses:** actions/checkout@v1 uses a community action called checkout to allow the workflow to access the contents of the repository

**uses:** ./action-a provides the relative path to the action we created in the action-a directory of the repository

**with:** is used to specify the input variables that will be available to your action in the runtime environment. In this case, the input variable is MY_NAME, and it is currently initialized to "Mona".

```
name: A workflow for my Hello World file
on: push

jobs:
  build:
    name: Hello world action
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v1
      - uses: ./action-a
        with:
          MY_NAME: "Mona"
```
