Exercise 1.5
============

Ben Bitdiddle has invented a test to determine whether the interpreter he is
faced with is using applicative-order evaluation or normal-order evaluation. He
defines the following two procedures:

    (define (p) (p))
    
    (define (test x y)
      (if (= x 0)
          0
          y))

Then he evaluates the expression

    (test 0 (p))

What behavior will Ben observe with an interpreter that uses applicative-order
evaluation? What behavior will he observe with an interpreter that uses
normal-order evaluation? Explain your answer. (Assume that the evaluation rule
for the special form if is the same whether the interpreter is using normal or
applicative order: The predicate expression is evaluated first, and the result
determines whether to evaluate the consequent or the alternative expression.)

Solution
--------

__Applicative-order__

when `test` is evaluated, it will evaluate both branches of the `if`, which
will result in an infinite loop due to `p` being defined as `(p)`.

__Normal-order__

when `test` is evaluated, it will first determine the result of the `if`
condition. Since it if `true`, `test` will return `0` and we will not have the
infinite recursion problem that we saw when using normal-order evaluation.
