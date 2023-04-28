# s
**Sum** or, **S**lightly **S**killful/**S**olid/**S**imple/**S**illy **S**hell **S**cript that **S**hall **S**ummation in an **S**-expre**SS**ion **S**tyle with **S**avvy. (**S**o many **S**'**s**!)

![](./s.gif)

# SYNOPSIS

**s** \[list of numbers\] \
**s** \[**-rv**\] \[**-h** *headertype*\] \[file \...\]

# DESCRIPTION

s performs one of the following:

  - Sums the list of numbers given as arguments and outputs the result.
  - Reads the specified file, or standard input if no file is specified, then prints a list of numbers summed vertically. 
    When there is only one line of input, sums row-wise.

# OPTIONS

**-r**
:   Sum by row instead of vertically.

**-v**
:   Print the original input and summation result.

**-h** x\|y
:   Specifies a heading with the given arguments. x for the header row and y for the header column. The specified header row or column is excluded from summation.

# EXAMPLES

Sum arguments:
```shell
s 14 28
# output: 42

s {1..100}
# output: 5050
```

Sum by standard input:
```shell
cat <<eof |s
> 20
> 22
eof
# output: 42
```

Sum horizontally when the input is one line.

```shell
echo 21 21 |s
# output: 42
```

If there are 2 or more rows, show the sum for each column.

```shell
cat <<eof |s
> 13 6 7
> 8 5 3
> eof
# output: 21 11 10
```

Execute **s** again with a pipe, it will print the total sum of all
numbers.

```shell
cat <<eof |s|s
> 13 6 7
> 8 5 3
> eof
# output: 42
```
