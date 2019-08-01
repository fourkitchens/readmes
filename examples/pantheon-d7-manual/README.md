# Manual Pantheon Project

This is a brief overview of my manual Pantheon Project located at https://github.com/fourkitchens/readmes/tree/master/pantheon/d7/manual

## At A Glance
|   |   |
|---|---|
| Build Tool | None |
| Local Environment | <a href='https://github.com/lando/lando/'>Lando</a> |
| Deployment Method | Manual push to Pantheon |
| PHP | 7.2 |
| Core Distribution | Drupal 7 |
| Testing Enforced | None |

## Brief Foundation Architecture

* Drupal 7 vanilla
* Features

## Before You Start

### Dependencies

* [Lando >= v3.0.0-rc.13](https://docs.devwithlando.io/)
* [NVM](https://github.com/nvm-sh/nvm)
* [NodeJS v10 LTS](https://nodejs.org/en/)
* [Drush >= 8](https://github.com/drush-ops/drush)
* [Terminus >= 1](https://github.com/pantheon-systems/terminus)

### Accounts, Roles, and Permissions

* Pantheon access to this site's Dashboard

### Database

* Retrieve from Pantheon Live backup.
  `terminus backup:get site.live --element=db --to=db.sql.gz`

## Getting Started

### Initial Setup

*Nothing to do here.*

### Local Development

1. Clone the client repo
2. Download the database to a subdirectory called `reference` and save it as `db.sql.gz`
3. `lando start`
4. `lando db-import reference/db.sql.gz` or whatever the db name is
5. Use the standard `refresh` command

### Refresh notes
1. This is run by a different tool on every site and does not import a db.
2. It will check for the presence of a local settings file.
3. You may need to get development keys off last pass
4. Optional environment name argument: `local`, `dev`, `test`, and `prod`
5. Default is `local`

## Subsequent Builds

Checkout the new code and rerun steps 4-6 for local development as needed.


## Git workflow

- `master` The master branch is for code ready to be released to the live environment. Pantheon enforces us to traverse from dev to live so essentially, dev environment is UAT and Live is live and test is effectively a dead zone since it is not individually addressable. We want to preserve the ability to "hot patch" live so we are not using dev as a gitflow "develop" as a result of the pantheon workflow.

- `feature` Feature branches should branch from and merge back into the sprint branch. They contain code that is currently in development. When a story/feature is complete, a pull request should be created merging the feature branch into the sprint branch.

## Configuration Management Workflow

Use features as necessary to push configuration to the website.

## Deployment

1. Merge develop into master.
2. Push master to Pantheon.
3. `terminus dashboard PANTHEON_SITE.test`
4. Enter the tickets you are deploying into the deployment notes and click Deploy
5. Click the "Live" tab.
6. Repeat step 4.
7. run the following commands as needed:
  ```
  terminus drush PANTHEON_SITE.live -- updb -y
  terminus drush PANTHEON_SITE.live -- cc all -y
  terminus drush PANTHEON_SITE.live -- fra -y
  terminus drush PANTHEON_SITE.live -- cc all -y
  ```

## Testing

All testing is currently done manually and via the code review process.

## Known Issues

There are currently no known issues for this site.

