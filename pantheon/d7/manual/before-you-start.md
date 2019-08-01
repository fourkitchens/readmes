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
