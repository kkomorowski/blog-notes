# Cassandra

### Connecting to the cluster with `cqlsh`:

```
cqlsh --username="user" --password="pass" cassandra.example.com
```

<table data-header-hidden><thead><tr><th width="145"></th><th></th></tr></thead><tbody><tr><td>Warning</td><td>Following notes are valid for <code>cqlsh 6.0.0 | Cassandra 3.11.8</code></td></tr></tbody></table>

### Checking available keyspaces (like `SHOW databases` in SQL):

```
SELECT keyspace_name FROM system_schema.keyspaces;
```

What tables are defined in the keyspace?

```
SELECT table_name
  FROM system_schema.tables
 WHERE keyspace_name = 'your_keyspace';
```

What are the columns in the table?

```
SELECT column_name, kind, type
  FROM system_schema.columns
 WHERE keyspace_name = 'your_keyspace'
   AND table_name = 'your_table';
```

