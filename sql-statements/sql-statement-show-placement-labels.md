---
title: SHOW PLACEMENT LABELS
summary: The usage of SHOW PLACEMENT LABELS in TiDB.
---

# SHOW PLACEMENT LABELS {#show-placement-labels}

`SHOW PLACEMENT LABELS` is used to summarize the labels and values that are available for Placement Rules.

> **Note:**
>
> This feature is not available on [{{{ .starter }}}](https://docs.pingcap.com/tidbcloud/select-cluster-tier#tidb-cloud-serverless) and [{{{ .essential }}}](https://docs.pingcap.com/tidbcloud/select-cluster-tier#essential) clusters.

## Synopsis {#synopsis}

```ebnf+diagram
ShowStmt ::=
    "SHOW" "PLACEMENT" "LABELS" ShowLikeOrWhere?
```

## Examples {#examples}

```sql
SHOW PLACEMENT LABELS;
```

    +--------+----------------+
    | Key    | Values         |
    +--------+----------------+
    | region | ["us-east-1"]  |
    | zone   | ["us-east-1a"] |
    +--------+----------------+
    2 rows in set (0.00 sec)

## MySQL compatibility {#mysql-compatibility}

This statement is a TiDB extension to MySQL syntax.

## See also {#see-also}

-   [Placement Rules in SQL](/placement-rules-in-sql.md)
-   [SHOW PLACEMENT](/sql-statements/sql-statement-show-placement.md)
-   [CREATE PLACEMENT POLICY](/sql-statements/sql-statement-create-placement-policy.md)
