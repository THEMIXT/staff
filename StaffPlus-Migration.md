# StaffPlus Migration

## Steps:
- Start by backing up your old StaffPlus folder.

- Download your staffplusplus version from Spigot: https://www.spigotmc.org/resources/staff.83562/history

- Replace the Old Staff+.jar with the new Staff++ jar.

- In the config file change storage type from `flatfile` to 'sqlite' or `mysql`:

```yaml
storage:
  #Type is how it will store either a sqlite or mysql
  type: 'sqlite'
```

StaffPlusPlus dropped support for flatfile storage. We now support MySql or Sqlite.
We do not yet support a migration from flatfile to the sql database. **This means you will lose your previous reports/warning should you have them.**
This is a one time loss and everything from this point out will always be gracefully migrated.

- All other properties should be migrated automatically if you are using the latest version of Staff++.

- Start up the server and see if everything runs.


Should you still encounter errors, compare your config with the [default configuration file](https://github.com/garagepoort/StaffPlusPlus/blob/master/StaffPlusCore/src/main/resources/config.yml).

