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
* [NVM - Node Version Manager](https://github.com/nvm-sh/nvm)

### Accounts, Roles, and Permissions

* Pantheon access to this site's Dashboard

### Database

* Retrieve from Pantheon Live backup

---
## Getting Started

### Local Development

1. Clone the repository from GitHub
2. Add Pantheon `remote` (if the project isn't using circle ci)
3. Once the repo is cloned down run
 - `cd project-name` then `lando start`
4. Download a database background from Pantheon`s live environment
5. run `lando db-import file-name/sql.gz`
6. log in to the site at `site-name.lndo/wp-admin`

---
### Theming
1. See each respective project for theme-specific details. Some projects use `gulp`, others use `grunt`, some use `sass` or `less`.

---
## Subsequent Builds

Checkout the new code and rerun steps 4-6 for local development as needed.

---
## Git workflow

- `master` The master branch is for code ready to be released to the live environment. Pantheon enforces us to traverse from dev to live so essentially, dev environment is UAT and Live is live and test is effectively a dead zone since it is not individually addressable. We want to preserve the ability to "hot patch" live so we are not using dev as a gitflow "develop" as a result of the pantheon workflow.

- `feature` Feature branches should branch from and merge back into the sprint branch. They contain code that is currently in development. When a story/feature is complete, a pull request should be created merging the feature branch into the sprint branch.

## Configuration Management Workflow

None of our WordPress sites use configuration management to date.

In the future we should look at integrating WP CFM 
- https://wordpress.org/plugins/wp-cfm/
- https://wp-cli.org/


## Deployment

1. Merge develop into master.
2. Push master to Pantheon.
3. Enter the tickets you are deploying into the deployment notes and click Deploy
4. Click the "Live" tab.
6. Repeat step 3.


## Testing

All testing is currently done manually and via the code review process.

## Known Issues

There are currently no known issues for this site.
