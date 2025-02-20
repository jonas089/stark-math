# Revision 

## Constraint Polynomials
Constraint Polynomials emerge naturally from constraints that are enforced over the trace table.

```rust
builder.assert_eq(a_next, a + b);
```

This example will enforce a constraint over the entire trace table.

|---|---|---|
| a_next | a | b |
| 10 | 5 | 5 |

Interpolate the trace as a low degree polynomial, check that the constraint 
polynomial holds for the extended domain and the low degree polynomial.

If the trace table satisfies the constraint, then the LDE will too!
