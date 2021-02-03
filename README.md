# GitHub PR Content Checker

This action checks for the presence or absence of a word in the body or diff in a PR, as well as the number of lines and files changed. If fails if one or more of the set criteria isn't met.

# Using this action

You need to add this in a file in `.github/workflows` and set appropriate options.

```
name: "Check PR content"
on: [pull_request]

jobs:
  check_pr:
    runs-on: ubuntu-latest
    steps:
    - name: Check PR
      uses: jsoares/gh-pr-content-checker@master
      with:
        github-token: ${{github.token}}
        bodyContains: 'Add this'
        bodyDoesNotContain: "Delete this"        
        diffContains: 'Add this'
        diffDoesNotContain: "Delete this"        
        maxLinesChanged: 1
        maxFilesChanged: 1
```

An example is also provided in .github/workflows/ in this repository.


## History

This is a customisation of [JJ/github-pr-contains-action](https://github.com/JJ/github-pr-contains-action/), using updated dependencies, improving counting behaviour, and adding a diffDoesNotContain flag.

* `v0`: Proof of concept, published to marketplace
* `v1`: Adds several more checks
* `v2`: Adds check for strings to avoid and creates issues for errors.

--forked--

* `v3`: Adds diffDoesNotContain field, improves counting behaviour, update deps

## License

This is a modification of [JJ/github-pr-contains-action](https://github.com/JJ/github-pr-contains-action/) and is released under the MIT license.
