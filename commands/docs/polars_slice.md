---
title: polars slice
categories: |
  dataframe
version: 0.96.0
dataframe: |
  Creates new dataframe from a slice of rows.
usage: |
  Creates new dataframe from a slice of rows.
---
<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# `polars slice` for [dataframe](/commands/categories/dataframe.md)

<div class='command-title'>Creates new dataframe from a slice of rows.</div>

## Signature

```> polars slice {flags} (offset) (size)```

## Parameters

 -  `offset`: start of slice
 -  `size`: size of slice


## Input/output types:

| input | output |
| ----- | ------ |
| any   | any    |

## Examples

Create new dataframe from a slice of the rows
```nu
> [[a b]; [1 2] [3 4]] | polars into-df | polars slice 0 1
╭───┬───┬───╮
│ # │ a │ b │
├───┼───┼───┤
│ 0 │ 1 │ 2 │
╰───┴───┴───╯

```