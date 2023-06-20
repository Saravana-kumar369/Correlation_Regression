# Correlation and regression for data analysis
# Aim : 

To analyse given data using coeffificient of correlation and regression line
![image](https://user-images.githubusercontent.com/104613195/168224136-d6b64e64-7d3d-4775-9337-c8f96fe41f2d.png)


# Software required :  

Python

# Theory:

Correlation describes the strength of an association between two variables, and is completely symmetrical, the correlation between A and B is the same as the correlation between B and A. However, if the two variables are related it means that when one changes by a certain amount the other changes on an average by a certain amount.  

If y represents the dependent variable and x the independent variable, this relationship is described as the regression of y on x. The relationship can be represented by a simple equation called the regression equation. The regression equation representing how much y changes with any given change of x can be used to construct a regression line on a scatter diagram, and in the simplest case this is assumed to be a straight line.

# Procedure :

![image](https://user-images.githubusercontent.com/104613195/168225866-ac8f6610-bdc3-4ac2-a24e-2b24ba08e189.png)

# Program :
```
import numpy as np
import math
import matplotlib.pyplot as plt

x = list(map(int, input().split()))
y = list(map(int, input().split()))
N = len(x)

Sx = sum(x)
Sy = sum(y)
Sxy = sum(xi * yi for xi, yi in zip(x, y))
Sx2 = sum(xi ** 2 for xi in x)
Sy2 = sum(yi ** 2 for yi in y)

c= (N * Sxy - Sx * Sy) / (math.sqrt(N * Sx2 - Sx ** 2) * math.sqrt(N * Sy2 - Sy ** 2))
print("The Correlation coefficient is %.3f" % c)

byx = (N * Sxy - Sx * Sy) / (N * Sx2 - Sx ** 2)
xmean = Sx / N
ymean = Sy / N
print("The Regression line Y on X is: y = %.3f + %.3f (x - %.3f)" % (ymean, byx, xmean))

plt.scatter(x, y)

def Reg(x):
    return ymean + byx * (x - xmean)

x_vals = np.linspace(20, 80, 51)
y_vals = Reg(x_vals)
plt.plot(x_vals, y_vals, 'c')

plt.xlabel('x-data')
plt.ylabel('y-data')
plt.legend(['Regression Line', 'Data points'])

plt.show()
```
# Output 
![Screenshot 2023-06-07 112405](https://github.com/Saravana-kumar369/Correlation_Regression/assets/117925254/9f291be8-677e-441c-8690-25abf2226e92)

# Result
The Correlation and regression for data analysis of objects from feeder using probability distribution are calculated.
