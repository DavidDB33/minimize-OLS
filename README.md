# minimize-OLS
A learning exercise to understand the OLS solutions

## Analytical form

Define the residuals where B are the linear coefficients:
`e = Y - XB`

Define the function to optimize (the least squared error) as the quadratic of the residuals. Since it is a columnar row, multiply it this way to get an 1 by 1 matrix (a scalar).
`S(B) = (Y - XB)'(Y - XB)`
Note that the symbol `A'` in `A` is the transpose.

Now derive w.r.t. B and solve when equal to 0.
```
S(B) = (Y - XB)'(Y - XB)
 = (Y' - B'X')(Y - XB)
 = Y'Y - B'X'Y - Y'XB + B'X'XB
 = Y'Y - (Y'XB)' - Y'XB + B'GB # Substitute G = X'X = (X'X)' = G'
dS(B)/dB = 0 - Y'X - Y'X + B'(G' + G)
 = -2Y'X + 2B'X'X
dS(B)/dB = 0
-2Y'X + 2B'X'X = 0
B'X'X = Y'X
X'XB = X'Y
B = (X'X)^{-1}X'Y
```