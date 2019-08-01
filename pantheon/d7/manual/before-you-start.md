## Before You Start

### Dependencies

* [Lando](https://docs.devwithlando.io/)
* [NodeJS LTS](https://nodejs.org/en/)
* [Drush >= 7](https://github.com/drush-ops/drush)
* [Terminus >= 1](https://github.com/pantheon-systems/terminus)

### Accounts, Roles, and Permissions

* Pantheon access to this site's Dashboard

### Database

* Retrieve from Pantheon Live backup.
  `terminus backup:get site.live --element=db --to=db.sql.gz`
