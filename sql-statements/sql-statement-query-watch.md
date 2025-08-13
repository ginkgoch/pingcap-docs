---
title: QUERY WATCH
summary: An overview of the usage of QUERY WATCH for the TiDB database.
---

# QUERY WATCH {#query-watch}

The `QUERY WATCH` statement is used to manually manage the watch list of runaway queries in a resource group.

> **Note:**
>
> This feature is not available on [{{{ .starter }}}](https://docs.pingcap.com/tidbcloud/select-cluster-tier#tidb-cloud-serverless) and [{{{ .essential }}}](https://docs.pingcap.com/tidbcloud/select-cluster-tier#essential) clusters.

## Synopsis {#synopsis}

```ebnf+diagram
AddQueryWatchStmt ::=
    "QUERY" "WATCH" "ADD" QueryWatchOptionList
QueryWatchOptionList ::=
    QueryWatchOption
|   QueryWatchOptionList QueryWatchOption
|   QueryWatchOptionList ',' QueryWatchOption
QueryWatchOption ::=
    "RESOURCE" "GROUP" ResourceGroupName
|   "RESOURCE" "GROUP" UserVariable
|   "ACTION" EqOpt ResourceGroupRunawayActionOption
|   QueryWatchTextOption
ResourceGroupName ::=
    Identifier
|   "DEFAULT"
QueryWatchTextOption ::=
    "SQL" "DIGEST" SimpleExpr
|   "PLAN" "DIGEST" SimpleExpr
|   "SQL" "TEXT" ResourceGroupRunawayWatchOption "TO" SimpleExpr

ResourceGroupRunawayWatchOption ::=
    "EXACT"
|   "SIMILAR"
|   "PLAN"

DropQueryWatchStmt ::=
    "QUERY" "WATCH" "REMOVE" NUM
```

## Parameters {#parameters}

See [`QUERY WATCH` parameters](/tidb-resource-control.md#query-watch-parameters).

## MySQL compatibility {#mysql-compatibility}

This statement is a TiDB extension to MySQL syntax.

## See also {#see-also}

-   [Runaway Queries](/tidb-resource-control.md#manage-queries-that-consume-more-resources-than-expected-runaway-queries)
