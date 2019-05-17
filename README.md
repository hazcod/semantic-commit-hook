# semantic-commit-hook
Git hook that enforces semantic commit messages.

## What is it
Semantic versioning automatically assigns version numbers on your code based on your commit messages.
This means that it recognizes hotfixes, refactors, breaking and non-breaking changes.
Read more about it [here](https://github.com/semantic-release/semantic-release#how-does-it-work).

## How to use
Any commit to your local git repository will be rejected if the first line (the title) does not follow [the semantic versioning format](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#commit-message-format).

For releasing, I use [go-semantic-release](https://github.com/go-semantic-release/semantic-release).

## Installation
```curl https://raw.githubusercontent.com/hazcod/semantic-commit-hook/master/pre-commit > .git/hooks/pre-commit && chmod 500 .git/hooks/pre-commit```
