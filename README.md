# orchid
An interpreter for the WHILE programming language.

## Introduction

WHILE is a toy language designed as an alternative to Turing machines when
studying computability and complexity. It is not designed as a serious
language; its purpose is to help students understand what is computable and to
do so in a format in which they are more familiar with (high level imperative
programming languages, such as Python and Java). Despite being simple, it is
powerful enough to test the limits of computability and develop a students
understanding of what computers can and cannot do.

WHILE was invented by Neil Jones (see *Computability and Complexity From a
Programming Perspective*, ISBN 9780262100649) and expanded on by Bernhard Reus
(see *Limits of Computation From a Programming Perspective*, ISBN
9783319278896). The language itself is very small: there is only one datatype,
the entire syntax and semantics of the language is covered in chapters 3 and 4
of *Limits of Computation*, and overall it seemed like a fun exercise to try to
implement a WHILE interpreter (and also a useful tool to have to hand when I
want to run WHILE programs).

## Data Types

WHILE supports only one data type: a binary tree. Specifically, each node of
the binary tree is either the leaf `nil` or two subtrees. These trees can be
encoded as lists, for example:

```
        /\
       /  \
      /    \
     nil   /\
          /  \
         /    \
        /\    nil
       /  \
      /    \
     nil  nil
```

Would be represented as:

```
[nil, [[nil, nil], nil]]
```

On its own, a binary tree doesn't really do much, but it's possible to encode
different kinds of data as binary trees. WHILE supports the following types of
data:

- Booleans
- Natural numbers
- Lists

### Booleans

Boolean values are encoded as follows:

- `False`: `nil`
- `True`: anything that isn't `False`

### Lists

Lists are encoded as follows:

- `[]`: `nil`
- `[a, b, ..., n]`: `[a, [b, [..., [n, nil]]...]]`

### Natural numbers

Natural numbers are encoded recursively as follows:

- 0: `nil`
- `n`: `[nil, n - 1]`

Note that the definition of natural numbers here includes 0.

### Notes on Type Strength

WHILE is untyped. As a result, 0, `False`, and empty lists are all equivalent.
The impetus is therefore on the programmer to know what type they are working
with and program accordingly.
