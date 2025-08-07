code

import numpy as np
import matplotlib.pyplot as plt
from sklearn.linear_model import Perceptron
X = np.array([[0,0],[0,1],[1,0],[1,1]])
y = np.array([0,1,1,0])
clf = Perceptron(tol=1e-3, random_state=0)
clf.fit(X, y)
print("Predictions:", clf.predict(X))
for i in range(len(X)):
    if y[i] == 0:
        plt.scatter(X[i][0], X[i][1], color='red')
    else:
        plt.scatter(X[i][0], X[i][1], color='blue')
x_values = np.array([0, 1])
if clf.coef_[0][1] != 0:
    y_values = -(clf.coef_[0][0] * x_values + clf.intercept_) / clf.coef_[0][1]
    plt.plot(x_values, y_values, label='Decision boundary')
else:

    plt.axvline(x=-clf.intercept_/clf.coef_[0][0], color='green', label='Decision boundary')
plt.title('Perceptron Decision Boundary for XOR')
plt.xlabel('X1')
plt.ylabel('X2')
plt.legend()
plt.show()


output:
![Screenshot_7-8-2025_20514_colab research google com](https://github.com/user-attachments/assets/470e23ad-186a-4520-837e-dc35dcf01f12)
