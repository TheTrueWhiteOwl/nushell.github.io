---
title: polars sample
categories: |
  dataframe
version: 0.96.0
dataframe: |
  Create sample dataframe.
usage: |
  Create sample dataframe.
---
<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# `polars sample` for [dataframe](/commands/categories/dataframe.md)

<div class='command-title'>Create sample dataframe.</div>

## Signature

```> polars sample {flags} ```

## Flags

 -  `--n-rows, -n {int}`: number of rows to be taken from dataframe
 -  `--fraction, -f {number}`: fraction of dataframe to be taken
 -  `--seed, -s {number}`: seed for the selection
 -  `--replace, -e`: sample with replace
 -  `--shuffle, -u`: shuffle sample


## Input/output types:

| input | output |
| ----- | ------ |
| any   | any    |

## Examples

Sample rows from dataframe
```nu
> [[a b]; [1 2] [3 4]] | polars into-df | polars sample --n-rows 1

```

Shows sample row using fraction and replace
```nu
> [[a b]; [1 2] [3 4] [5 6]] | polars into-df | polars sample --fraction 0.5 --replace

```

Shows sample row using using predefined seed 1
```nu
> [[a b]; [1 2] [3 4] [5 6]] | polars into-df | polars sample --seed 1 --n-rows 1
╭───┬───┬───╮
│ # │ a │ b │
├───┼───┼───┤
│ 0 │ 5 │ 6 │
╰───┴───┴───╯

```