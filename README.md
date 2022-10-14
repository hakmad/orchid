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
implement a WHILE interepreter (and also a useful tool to have to hand when I
want to run WHILE programs).
