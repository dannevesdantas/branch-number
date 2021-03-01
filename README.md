# Use branch name GitHub Actions
GitHub Action for exporting current branch name's number segment as an environment variable.

## Usage

```yml
- name: Get branch name
  # Produce a $BRANCH_NAME environment variable containing only the branch name without the 'refs/heads/' part
  uses: nelonoel/branch-name@v1.0.1

- name: Get branch name's number
  uses: dannevesdantas/branch-number@v0.1.0
  with:
    branch-name: '${{ env.BRANCH_NAME }}'
```

Or, specifying a hard-coded branch name

```yml
- name: Get branch name's number
  uses: dannevesdantas/branch-number@v0.1.0
  with:
    branch-name: 'release/3.2.0'
```

You can also optionally specify a delimiter to be used to separate the branch name part from the branch name's number part. For example `'/'` or `'-'`. Default value is `'/'`

```yml
- name: Get branch name's number
  uses: dannevesdantas/branch-number@v0.1.0
  with:
    branch-name: 'release-3.2.0'
    delimiter: '-'
```

The current branch name's number segment will be available at `${{ env.BRANCH_NUMBER }}` environment variable.

## Requirements
This GitHub Action is compatible with Windows based runners only.

# License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
