## Git workflow

- `master` The master branch is for hotfixes and code ready to be released to the live environment.

- `develop` The develop branch is for new features and routine bugfixes, new branches should default to using this base branch. They contain code that is currently in development. When a story/feature is complete, a pull request should be created merging the feature branch into the sprint branch.

- `release-*` Feature branches should branch from and merge back into this default sprint branch. They contain code that is currently in development. When a story/feature is complete, a pull request should be created merging the feature branch into the sprint branch.

- `abc-123` PRs should have a ticket assicated with them and the branch name should be the ticket number in all lower case.
