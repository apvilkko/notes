# Databases

## Repair migration (flyway + jdbc)

```
flyway -url=jdbc:mysql://localhost:3306/dbname -user=user -password=pass -locations=filesystem:/path/to/src/main/resources/db/migration repair
```

## Pretty print specific fields in mongo

```
db.collection.find().forEach(function(doc) {print([doc._id, doc.entityId, doc.something, doc.thistoo JSON.stringify(doc.error)].join(" | "));});
```

## PostgreSQL: Dump all tables and columns as CSV

```
in psql prompt:

COPY (
SELECT c.relname AS "Table", a.attname AS "Column"
FROM pg_catalog.pg_class c
     LEFT JOIN pg_catalog.pg_namespace n ON n.oid = c.relnamespace
     LEFT JOIN pg_catalog.pg_attribute a ON a.attrelid = c.oid
WHERE c.relkind IN ('r','m','f','')
      AND n.nspname <> 'pg_catalog'
      AND n.nspname <> 'tiger'
      AND n.nspname <> 'information_schema'
      AND n.nspname !~ '^pg_toast'
      AND a.attnum > 0 AND NOT a.attisdropped
  AND pg_catalog.pg_table_is_visible(c.oid)
ORDER BY 1,2
) TO STDOUT WITH CSV HEADER;

```
