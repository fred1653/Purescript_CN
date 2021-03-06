# `ArgListLengthsDiffer` 错误

## 举例

Differing number of arguments for each foo declaration:

```purescript
foo 0 y = 0
foo x y z = x * y * z
```

Forgotten parenthesis around ADT deconstruction:

```purescript
data Some = Three Int Int Int
          | NoneHere
           
bar Three x y z = x * y * z -- needs parenthesis around
bar NoneHere = 0

-- corrected with parenthesis
bar (Three x y z) = x * y * z
bar NoneHere = 0
```

## 原因

ArgListLengthsDiffer arrises from a function having different numbers of argument variables.

Commonly seen when parenthesis are forgotten around an ADT deconstruction argument.

## 修复

Ensure that there are the same number of arguments for each pattern matching function declaration.

Check to ensure that there are parenthesis around ADT deconstruction.

## 备注

- Additional notes.
