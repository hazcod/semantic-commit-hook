# Changelog

## 2023-12-24

- always require a valid type (do not allow this anymore: 'myscope: my message' or ': myscope: test'
  - https://www.conventionalcommits.org/en/v1.0.0/#specification (1)

- add all valid semantic versioning types (build, ci, revert)
  - https://github.com/conventional-changelog/commitlint/blob/master/%40commitlint/config-conventional/index.js#L22

- allow more characters in the scope (example: 'feat(my-scope, other-scope): my message')
  - https://github.com/conventional-changelog/commitlint/blob/master/%40commitlint/rules/src/scope-enum.test.ts#L11

- allow optional exclamation mark before the colon to indicate a breaking change (example: 'feat(api)!: changed endpoint for travel times')
  - https://www.conventionalcommits.org/en/v1.0.0/#commit-message-with-scope-and--to-draw-attention-to-breaking-change

- tested the regex on https://regex101.com with these values:

```
===== Valid commit messages: =====
build: my message
chore: my message
ci: my message
docs: my message
feat: my message
fix: my message
perf: my message
refactor: my message
revert: my message
style: my message
test: my message
build(my-scope): my message
chore(my-scope): my message
ci(my-scope): my message
docs(my-scope): my message
feat(my-scope): my message
fix(my-scope): my message
perf(my-scope): my message
refactor(my-scope): my message
revert(my-scope): my message
style(my-scope): my message
test(my-scope): my message
feat(my-scope, other-scope): my message
feat(my_scope): my message
feat(my_scope): MY MESSAGE
feat(my_scope)!: MY MESSAGE

===== Valid commit message examples from https://www.conventionalcommits.org/en/v1.0.0/#examples: =====
feat: allow provided config object to extend other configs
feat!: send an email to the customer when a product is shipped
feat(api)!: send an email to the customer when a product is shipped
chore!: drop support for Node 6
docs: correct spelling of CHANGELOG
feat(lang): add Polish language
fix: prevent racing of requests
revert: let us never again speak of the noodle incident

===== Invalid commit messages: =====
feat:my message (no space after the colon)
feat : my message (additional space not allowed)
 feat: my message (starting space not allowed)
feat!(scope): my message (exclamation mark for blocking change should be right behind the colon)
feat(!scope): my message (exclamation mark for blocking change should be right behind the colon)
feat(scope!): my message (exclamation mark for blocking change should be right behind the colon)
feat(scope):! my message (exclamation mark for blocking change should be right behind the colon)
: myscope my message (no type)
: myscope::: my message (no type)
: my message (no type)
myscope: my message (invalid type)
myscope: my message (invalid type)
FEAT(my-scope): my message (only lowercase allowed for type)
feat(MY-SCOPE): my message (only lowercase allowed for scope)
```

## 2023-05-01

- fix: Fix vs code merges

## 2019-05-27

- updated regex

## 2019-05-20

- initial
