# Move assigned issue to column

> ✨ GitHub action to create cards for new issues and automagically move assigned issue to a column.


## How to use

To use this action we need the project name and the name of the column for the new issues will go into. The project and column names will be used to get a column ID for automation.

In your project create a new workflow file `.github/workflows/issues.yml:
```
on: issues
name: ✨ Create and move project cards
jobs:
  build:
    name: EricKuck/github-issues-to-projects
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@master
    - name: EricKuck/github-issues-to-projects
      uses: EricKuck/github-issues-to-projects@master
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
      with:
        args: Backlog Inbox "Up next"
```

> Note: Replace `Backlog` with your project name, `Inbox` with your inbox column name, and `Up next` with your assigned column name.
