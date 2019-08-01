## Getting Started

### Initial Setup

Install dependencies.
```
composer install
npm install
```

### Local Development

This repo uses lando for local development. [Make sure its installed on your machine.](https://github.com/lando/lando/releases). See Using Lando below for further instructions on using lando within your development workflow.

1. Clone the client repo
2. `terminus backup:get [SITE].live --element=db --to=reference/db.sql.gz`
3. `lando start`
4. `lando db-import reference/db.sql.gz` or whatever the db name is