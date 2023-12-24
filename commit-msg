#!/usr/bin/env bash

if [ -z "$1" ]; then
	echo "Missing argument (commit message). Did you try to run this manually?"
	exit 1
fi

commitTitle="$(cat $1 | head -n1)"

# ignore merge requests
if echo "$commitTitle" | grep -qE "Merge branch"; then
	echo "Commit hook: ignoring branch merge"
	exit 0
fi

# check semantic versioning scheme
if ! echo "$commitTitle" | grep -qE '^(feat|fix|docs|style|refactor|perf|test|chore|build|ci|revert)(\([a-z0-9\s\-\_\,]+\))?!?:\s\w'; then
	echo "Your commit message did not follow semantic versioning: $commitTitle"
	echo ""
	echo "Format:   <type>(<optional-scope>): <subject>"
	echo "Example:  feat(api): add endpoint"
	echo ""
	echo "Valid types: build|chore|ci|docs|feat|fix|perf|refactor|revert|style|test"
	echo ""
	echo "Please see"
	echo "- https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#commit-message-format"
	echo "- https://www.conventionalcommits.org/en/v1.0.0/#summary"
	exit 1
fi
