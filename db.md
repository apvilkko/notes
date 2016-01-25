# Databases

## Repair migration (flyway + jdbc)

```
flyway -url=jdbc:mysql://localhost:3306/dbname -user=user -password=pass -locations=filesystem:/path/to/src/main/resources/db/migration repair
```
