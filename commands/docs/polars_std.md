---
title: polars std
categories: |
  expression
version: 0.96.0
expression: |
  Creates a std expression for an aggregation of std value from columns in a dataframe.
usage: |
  Creates a std expression for an aggregation of std value from columns in a dataframe.
---
<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# `polars std` for [expression](/commands/categories/expression.md)

<div class='command-title'>Creates a std expression for an aggregation of std value from columns in a dataframe.</div>

## Signature

```> polars std {flags} ```


## Input/output types:

| input | output |
| ----- | ------ |
| any   | any    |

## Examples

Std value from columns in a dataframe
```nu
> [[a b]; [6 2] [4 2] [2 2]] | polars into-df | polars std
╭───┬──────┬──────╮
│ # │  a   │  b   │
├───┼──────┼──────┤
│ 0 │ 2.00 │ 0.00 │
╰───┴──────┴──────╯

```

Std aggregation for a group-by
```nu
> [[a b]; [one 2] [one 2] [two 1] [two 1]]
    | polars into-df
    | polars group-by a
    | polars agg (polars col b | polars std)
╭───┬─────┬──────╮
│ # │  a  │  b   │
├───┼─────┼──────┤
│ 0 │ one │ 0.00 │
│ 1 │ two │ 0.00 │
╰───┴─────┴──────╯

```