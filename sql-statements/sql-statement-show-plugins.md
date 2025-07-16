---
title: SHOW PLUGINS
summary: An overview of the usage of SHOW PLUGINS for the TiDB database.
---

# SHOW PLUGINS {#show-plugins}

`SHOW PLUGINS` shows all plugins installed in TiDB, including each plugin's status and version information.

> **Note:**
>
> This feature is not available on [{{{ .starter }}}](https://docs.pingcap.com/tidbcloud/select-cluster-tier#tidb-cloud-serverless) clusters.

## Synopsis {#synopsis}

```ebnf+diagram
ShowPluginsStmt ::=
    "SHOW" "PLUGINS" ShowLikeOrWhere?
```

## Examples {#examples}

```sql
SHOW PLUGINS;
```

    +-------+--------------+-------+-----------------------------+---------+---------+
    | Name  | Status       | Type  | Library                     | License | Version |
    +-------+--------------+-------+-----------------------------+---------+---------+
    | audit | Ready-enable | Audit | /tmp/tidb/plugin/audit-1.so |         | 1       |
    +-------+--------------+-------+-----------------------------+---------+---------+
    1 row in set (0.000 sec)

```sql
SHOW PLUGINS LIKE 'a%';
```

    +-------+--------------+-------+-----------------------------+---------+---------+
    | Name  | Status       | Type  | Library                     | License | Version |
    +-------+--------------+-------+-----------------------------+---------+---------+
    | audit | Ready-enable | Audit | /tmp/tidb/plugin/audit-1.so |         | 1       |
    +-------+--------------+-------+-----------------------------+---------+---------+
    1 row in set (0.000 sec)

## MySQL compatibility {#mysql-compatibility}

The `SHOW PLUGINS` statement in TiDB is fully compatible with MySQL. If you find any compatibility differences, [report a bug](https://docs.pingcap.com/tidb/stable/support).

## See also {#see-also}

-   [`ADMIN PLUGINS`](/sql-statements/sql-statement-admin.md#admin-plugins-related-statement)
