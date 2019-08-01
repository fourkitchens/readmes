# Manual Pantheon WordPress Project

This is a brief overview of our Pantheon Project located at https://github.com/fourkitchens/readmes/tree/master/pantheon/wordpress/manual

## At A Glance
|   |   |
|---|---|
| Build Tool | None |
| Local Environment | <a href='https://docs.devwithlando.io/'>Lando</a> |
| Deployment Method | Manual push to Pantheon |
| PHP | 7.0 |
| Core Distribution | <a href='https://github.com/pantheon-systems/WordPress'> WordPress Pantheon Systems</a>
| Testing Enforced | None |

## Brief Foundation Architecture

* WordPress Pantheon Systems
* Features

## Before You Start

### Dependencies

* [Lando](https://docs.devwithlando.io)
* [NodeJS LTS](https://nodejs.org/en/)

### Accounts, Roles, and Permissions

* Pantheon access to this site's Dashboard

### Database

* Retrive from Pantheon Live backup

## Getting Started

### Initial Setup

*Nothing to do here.*

### Local Development

1. Use Kalabox to download and create a local environment.
2. `cd ~/Kalabox/SITE_NAME/code`
3. Add the github repository as a remote using `git remote add fourkitchens GIT_REPO`
4. `npm install`
5. Use Kalabox to pull live database.
6. `kbox drush cc all`



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
