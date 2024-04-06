# `doctrine:schema:validate` reproducer

```txt
Requirements:
  - PHP: 8.2
  - Symfony: 7.0
  - postgreSQL: 16
```

After setting up the project and migrating the database, execute this command:
```bash
bin/console doctrine:schema:validate
```
You'll see this error message
```txt
[OK] The mapping files are correct.

Database
--------
[ERROR] The database schema is not in sync with the current mapping file.
```

To find out why the command produces an error, execute this command
```bash
bin/console doctrine:schema:update --dump-sql
```
and you will see:
```sql
DROP TABLE doctrine_migration_versions;
```
