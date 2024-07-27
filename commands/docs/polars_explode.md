---
title: polars explode
categories: |
  lazyframe
version: 0.96.0
lazyframe: |
  Explodes a dataframe or creates a explode expression.
usage: |
  Explodes a dataframe or creates a explode expression.
---
<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# `polars explode` for [lazyframe](/commands/categories/lazyframe.md)

<div class='command-title'>Explodes a dataframe or creates a explode expression.</div>

## Signature

```> polars explode {flags} ...rest```

## Parameters

 -  `...rest`: columns to explode, only applicable for dataframes


## Input/output types:

| input | output |
| ----- | ------ |
| any   | any    |

## Examples

Explode the specified dataframe
```nu
> [[id name hobbies]; [1 Mercy [Cycling Knitting]] [2 Bob [Skiing Football]]] | polars into-df | polars explode hobbies | polars collect
╭───┬────┬───────┬──────────╮
│ # │ id │ name  │ hobbies  │
├───┼────┼───────┼──────────┤
│ 0 │  1 │ Mercy │ Cycling  │
│ 1 │  1 │ Mercy │ Knitting │
│ 2 │  2 │ Bob   │ Skiing   │
│ 3 │  2 │ Bob   │ Football │
╰───┴────┴───────┴──────────╯

```

Select a column and explode the values
```nu
> [[id name hobbies]; [1 Mercy [Cycling Knitting]] [2 Bob [Skiing Football]]] | polars into-df | polars select (polars col hobbies | polars explode)
╭───┬──────────╮
│ # │ hobbies  │
├───┼──────────┤
│ 0 │ Cycling  │
│ 1 │ Knitting │
│ 2 │ Skiing   │
│ 3 │ Football │
╰───┴──────────╯

```