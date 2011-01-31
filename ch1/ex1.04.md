Exercise 1.4
============

Observe that our model of evaluation allows for combinations whose operators
are compound expressions. Use this observation to describe the behavior of the
following procedure:

    (define (a-plus-abs-b a b)
      ((if (> b 0) + -) a b))

Solution
--------

`(if (> b 0) + -)` returns the operator `+` or `-` depending on if `b > 0`. It
then uses the returned operator with the operands `a` and `b` returning the
result of `a + b` or `a - b`.
