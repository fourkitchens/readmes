# Pantheon/Wordpress/Composer Project

This is a brief overview of a Pantheon/Wordpress/Composer Project located at https://github.com/fourkitchens/readmes/tree/master/pantheon/wordpress/composer

## At A Glance
|   |   |
|---|---|
| Build Tool | <a href='https://getcomposer.org/download/'>Composer</a> |
| Local Environment | <a href='https://github.com/lando/lando/releases'>Lando</a> |
| Deployment Method | Manual push to Pantheon |
| PHP | 7.2 |
| Core Distribution | Wordpress 5.x |
| Testing Enforced | None |

## Brief Foundation Architecture

* Wordpress 5.x
* Twenty Nineteen Child Theme
* Gutenburg Editor

## Before You Start

### Dependencies

* [Lando](https://github.com/lando/lando/releases)
* [NodeJS LTS](https://nodejs.org/en/)
* [wp-cli](https://wp-cli.org/)
* [Terminus >= 1](https://github.com/pantheon-systems/terminus)

### Accounts, Roles, and Permissions

* Pantheon access to this site's Dashboard

### Database

* Retrive from Pantheon Live backup

## Getting Started

### Initial Setup

Install dependencies.
```
composer install
npm install
```

### Local Development

This repo uses lando for local development. [Make sure its installed on your machine.](https://docs.devwithlando.io/installation/installing.html). See Using Lando below for further instructions on using lando within your development workflow.

## Subsequent Builds

Checkout the new code and rerun steps 4-6 for local development as needed.


## Git workflow

- `master` The master branch is for code ready to be released to the live environment. Pantheon enforces us to traverse from dev to live so essentially, dev environment is UAT and Live is live and test is effectively a dead zone since it is not individually addressable. We want to preserve the ability to "hot patch" live so we are not using dev as a gitflow "develop" as a result of the pantheon workflow.

- `develop` Feature branches should branch from and merge back into this branch. They contain code that is currently in development. When a story/feature is complete, a pull request should be created merging the develop branch.

## Configuration Management Workflow

No configuration management. Configuration is stored in the database.

## Deployment

1. Merge develop into master.
2. Push master to Pantheon.
3. `terminus dashboard PANTHEON_SITE.test`
4. Enter the tickets you are deploying into the deployment notes and click Deploy
5. Click the "Live" tab.
6. Create a manual backup and wait for it to complete.
6. Repeat step 4.
## Testing

All testing is currently done manually and via the code review process.

## Known Issues

There are currently no known issues for this site.

