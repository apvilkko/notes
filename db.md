# Databases

## Repair migration (flyway + jdbc)

```
flyway -url=jdbc:mysql://localhost:3306/dbname -user=user -password=pass -locations=filesystem:/path/to/src/main/resources/db/migration repair
```

## Pretty print specific fields in mongo

```
db.collection.find().forEach(function(doc) {print([doc._id, doc.entityId, doc.something, doc.thistoo JSON.stringify(doc.error)].join(" | "));});
```
