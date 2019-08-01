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
