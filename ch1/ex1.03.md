Exercise 1.3
============

Define a procedure that takes three numbers as arguments and returns the sum of
the squares of the two larger numbers.

Solution
--------
    (define (sum-of-squares a b)
      (+ (* a a) (* b b)))
    
    (define (fn a b c)
      (cond ((and (>= a c) (>= b c)) (sum-of-squares a b))
            ((and (>= a b) (>= c b)) (sum-of-squares a c))
            (else                    (sum-of-squares b c))))
