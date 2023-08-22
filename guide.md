# (WIP)
### Game Theory:
<u>Related topics</u>: recursion, graph theory, dynamic programming

For games where you win by making your opponent not able to do a move:

Related questions:
- (CCC) '08 S5 - Nukit
- (LC) Q 294 Flip Game II

## Prefix Sum and Difference
### 2D Prefix Sum Arrays
<u>Related Questions</u>
- (LC) 300 - Range Sum Query 2D (perfect example)
- **Note: Most difference array questions (found below) use the 2D prefix sum method to convert back to a regular array**

<u>Creating and using a PSA</u>
```python
# Create
psa[i][j] = psa[i-1][j] + psa[i][j-1] + a[i][j] - psa[i-1][j-1] 

# Query in O(1)
psa[r2][c2] - psa[r1-1][c2] - psa[r2][c1-1] + psa[r1-1] [c1-1]
```


### 2D Difference Arrays:
<u>Related questions</u>:
- (USACO) 2019 Feb - S2 Painting the Barn  
- (CCC) 2009 S5 - Wireles (uses geometry formulas)
- (CCC) 2014 S4 - Tinted Glass Window (uses coordiante compression)
- (DMPG) 2015 S5 - Black and White (uses XOR instead of addition)

<u>Creating and using a difference array</u>
```python
# add x for (r1, c1) to (r2, c2) 
# Create from data points, (remove +1 if needed)
dif[r1][c1] += x 
dif[r1][c2+1] -= x
dif[r2+1][c1] -= x     
dif[r2+1][c2+1] += x

# Turn back into array using PSA
arr[i+1][j+1] = arr[i+1][j] + arr[i][j+1] + diff[i][j] - arr[i][j]
```
```python
# Create directly from array
dif[i][j] = a[i][j] + a[i-1][j-1] - a[i-1][j] - a[i][j-1]
```

