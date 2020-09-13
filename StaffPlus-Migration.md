StaffPlus Migration

Steps:

Download your staffplusplus version from Spigot: https://www.spigotmc.org/resources/staff.83562/history

Replace the Old Staff+.jar with the new Staff++ jar.

In the config file change storage type from `flatfile` to 'sqlite' or `mysql`:

```
storage:
  #Type is how it will store either a sqlite or mysql
  type: 'sqlite'
```

StaffPlusPlus dropped support for flatfile storage. We know support MySql or Sqlite.
We do not yet support a migration from flatfile to sql database. This means you will lose your previous reports/warning should you have them.
This is a one time loss and everything from this point out will always be gracefully migrated.
