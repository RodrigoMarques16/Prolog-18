# Logic Programming - Assignment 1

## Symbollic Manipulation

Simple program to manipulate polynomials and monomials. This includes:

- Addition;
- Scaling;
- Simplification;
- Sorting.

And other auxiliary predicates.

A polynomial is a sum of monomials.

A monomial is of the form `K*X^E`, where `K` is a floating point number and `E` is a positive integer. And `X` belongs to a list of accepted variables: `[w,x,y,z]`

This can be changed in [syntax.pl](syntax.pl).

## Running

Run program with `swipl demo.pl`

## References

<https://github.com/lucach/mvpoli_prolog/> - Comparing monomials

## Syntax

- **pvars(L)**: list of variables to be used

- **pvar(X)**: True if X is a variable.
  
- **coefficient(K)**: True if K Is a number.
  
- **power(X^Y)**: True if x is a variable and Y is a non-negative integer.

- **varpower(VP, V, E)**: Extract var and exponent from var power.

- **var_compare(Op, V1, V2)**: Compare variables in lexicographic oredr. Gives 'indep' maximum priority.

- **is_negative(K)**: True if K is negative.

## Monomials

- **monomial(M)**: True if M is a monomial.

- **monparts(M, K, V^E)**: Extracts coefficient, var and exponent from a monomial.

- **normalize_mono(M, M2)**: Transforms M into the form Coefficient*Var^Exponent

- **add_mono(M1, M2, P)**: True if M3 is the sum of M1 with M2.

- **simmono(M1, M2)**: Simplifies monomial M1.

- **scale_mono(M1, K, M2)**: True if M2 is M1 multiplied by K.

- **mono_compare(Op, M1, M2)**: Monomial comparator for predsort.

- **same_power(M1, M2)**: True if M1 and M2 have the same var power.

- **same_var(M1, M2)**: True if M1 and M2 have the same var.

- **nega_mono(M)**: True if M1 is a monomila with negative coefficient.

## Polynomials

- **polynomial(P)**: True if P is a sum of monomials.

- **poly2list(P, L)**: Transforms polynomials into lists and vice-versa.

- **sort_poly_list(P, P2)** and **sort_poly(P, P2)**: Sort a polynomial given as a list.

- **reduce_poly_list(P, P2)** and **reduce_poly(P, P2)**: Sum together all monomials with the same var power in a polynomial.

- **simpoly_list(P, P2)** and **simpoly(P, P2)**: Simplify a polymonial.
  
- **scale_poly_list(P1, K, P)** and **scalepoly(P1, K, P)**: Is true if P is P1 multiplied by the scalar K.
  
- **add_poly_list(P1,P2,P)** and **add_poly(P1,P2,P)**: Add two polynomials together