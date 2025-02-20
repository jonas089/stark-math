# Revision 

## Constraint Polynomials
Constraint Polynomials emerge naturally from constraints that are enforced over the trace table.

```rust
builder.assert_eq(a_next, a + b);
```

This example will enforce a constraint over the entire trace table.


| a_next | a | b |
|---|---|---|
| 10 | 5 | 5 |

Interpolate the trace as a low degree polynomial, check that the constraint 
polynomial holds for the extended domain and the low degree polynomial.

If the trace table satisfies the constraint, then the LDE will too!

Note that initially each constraint polynomial is constructed individually and later they are combined into a single constraint poly. The reason why this works is because all constraint polynomials should evaluate to 0.

A slightly simplified explanation is, that we just add them all together and if one of the is not satisfied then our result will be < or > 0. If all constraints are satisifed the result will always be 0 for the values from the trace table that we test / open.
