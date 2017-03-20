# README

This demo app expects Sphinx to be compiled with libstemmer support.

The database is currently using PostgreSQL. If you want to use a different database, you should modify `config/database.yml` before running any commands.

To set everything up and run the tests:

```
# install postgres
sudo apt-get install postgresql postgresql-contrib libpq-dev
sudo service postgresql restart
# add user to postgres
sudo -i -u postgres
createuser --interactive
bundle
# Creates the database, runs migrations, starts Sphinx:
./bin/rake morphology:setup
# Run morphology tests:
./bin/rake morphology:test
# Stops Sphinx, drops the database:
./bin/rake morphology:packdown
```
