# Ex: 02 - Huffman - Shannon_fano
## AIM:
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. Apply the Huffman and Shannon-Fano to this source. Show that draw the tree diagram, the average codeword length, Entropy, Variance, Redundancy, Efficiency.

## TOOLS REQUIRED:
Python IDE with Numpy and Scipy.

## PROGRAM:

```

#Huffman and Shannon-Fano coding
import numpy as np
import math
L=0
hs =0
p=[]
lk =[] # Changed from 1k to lk
n =int(input("Enter the number of Samples :"))
for i in range (n):
    pr = float(input(f"Enter the probability of sample values {i + 1}:")) # Added closing parenthesis
    p.append(pr)
for j in range (n):
    length_val = float(input(f"Enter the length of the sample values {j + 1}:")) # Changed from 1 to length_val
    lk.append(length_val) # Appending length_val to lk
# Avg length of the code word
for k in range (n):
    Avg1 = p[k]*lk[k]
    L=L+Avg1
# Entropy
for k in range(n):
    e =p[k]*math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)
# Efficiency
eff = hs /L
eff = round(eff,3)
# Redundancy
red = round(1 - eff,3)
# Variance
var = 0
for k in range(n):
    var1 = p[k]*(lk[k]-L)**2 # Changed 1k[K] to lk[k]
    var = var + var1
var = round(var,3)
print(f"Average Codeword Length is :{L}")
print(f"Entropy is :{hs}")
print(f"Efficiency is : {eff}")
print(f"Redudancy is :{red}")
print(f"Variance is :{var}")
```

## CALCULATION:



## OUTPUT:

<img width="561" height="429" alt="image" src="https://github.com/user-attachments/assets/3275e90e-c16a-4ac3-8de1-c729e9f209c5" />


## RESULT:
The Huffman and Shannon-Fano of the given statistics {} using python are verified.
