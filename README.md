# simplegradientdescent

import numpy as np

def gradient_descent(x,y):
	currentm = currentb = 0
	iterations = 1000
	n = len(x)
	learning_rate = 0.001

	for i in range(iterations):
		y_predicted = currentm * x + currentb
		mse = (1/n) * sum([val**2 for val in (y-y_predicted)])
		md = -(2/n)*sum(x*(y-y_predicted))
		bd = -(2/n)*sum(y-y_predicted)
		currentm = currentm - learning_rate * md
		currentb = currentb - learning_rate * bd
		print("m {}, b{}, cost{} iteration {}".format(currentm,currentb,msecost,i))

x = np.array([1,2,3,4,5])
y = np.array([5,7,9,11,13])

gradient_descent(x,y)
