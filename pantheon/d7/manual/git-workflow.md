## Git workflow

- `master` The master branch is for code ready to be released to the live environment. Pantheon enforces us to traverse from dev to live so essentially, dev environment is UAT and Live is live and test is effectively a dead zone since it is not individually addressable. We want to preserve the ability to "hot patch" live so we are not using dev as a gitflow "develop" as a result of the pantheon workflow.

- `feature` Feature branches should branch from and merge back into the sprint branch. They contain code that is currently in development. When a story/feature is complete, a pull request should be created merging the feature branch into the sprint branch.
