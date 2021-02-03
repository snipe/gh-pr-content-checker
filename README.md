# Checking PRs for words

This action checks for the presence of a word in the body or diff in a PR.

# Using this action

You need to add this in a file in `.github/workflows` and set appropriate options.

```
name: "Check PR for word"
on: [pull_request]

jobs:
  check_pr:
    runs-on: ubuntu-latest
    steps:
    - name: Check PR
      uses: jsoares/github-pr-contains-action@master
      with:
        github-token: ${{github.token}}
        bodyContains: 'Add this'
        bodyDoesNotContain: "Delete this"        
        diffContains: 'Add this'
        diffDoesNotContain: "Delete this"        
        linesChanged: 1
        filesChanged: 1
```

An example is provided in .github/workflows/ in this repository.

## Contributing to development

This is a customisation of [JJ/github-pr-contains-action](https://github.com/JJ/github-pr-contains-action/). I suggest you contribute to the upstream repository.

## History

* `v0`: proof of concept, published to marketplace
* `v1`: Adds several more checks
* `v2`: Adds check for strings to avoid and creates issues for errors.
* `v3`: Adds diffDoesNotContain field

## License

This is a modification of [JJ/github-pr-contains-action](https://github.com/JJ/github-pr-contains-action/) and is released under the MIT license.
