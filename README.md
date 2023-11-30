# gpu-desktop-calculator

need to add two columns of numbers an exabyte in size from the cli?

definite work-in-progress. I eventually want to do more complex calculations you might find in AI

## usage

	./gpu f1.dat f2.dat out.dat

Files should be organized in columns of numbers. The code will add across (axis=0). Multiple columns of data per file are forthcoming.

A hypothetical usage to calculate a logistic regresion given a pre-trained w.dat might be

	./gpu mul w.dat x.dat - | ./gpu add bias.dat - | ./gpu mul -1 - | ./gpu exp - | ./gpu add 1 - | ./gpu div 1 yhat.dat 

y^​=1+e−(w⋅x+b)1​

## data

Test data can be generated by `datagen.sh`. These will create 1.6 GB of test data.

			complexPhysicsCalculation	  addArrays  
	cpu 		75.9				  67.3
	gpu 		61.7				  61.8

	implementation vs average time in seconds for generated data

