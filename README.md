# Medical-Image-Encryption
The medical image encryption system that we have developed here uses a multi-level encryption mechanism to encrypt images. We have used the application of chaotic maps to encrypt the images. 
We have mainly focused on two types of chaotic maps in our project: 

1. Logistic Map
The logistic map is defined by the following formula:
                                            
                                            Xn+1 = rXn(1-Xn)
Where Xn is the population size at time n, Xn+1 is the population size at the next time step, and r
is a parameter that represents the growth rate of the population.

2. Lorenz System.
The Lorenz system is defined by the following set of equations:
                                             
                                             dx/dt = σ(y-x)
                                             dy/dt = x(ρ-z)-y
                                             dz/dt = xy-βz
Where x, y, and z are the state variables, t is time, and σ, ρ, and β are parameters that determine
the behavior of the system. The Lorenz system is often visualized using a three-dimensional phase
space, where the three state variables are plotted against each other.

We have also defined over own encryption algorithm which is as follows:
Right-shift and down-shift algorithm shifts the pixels of the image by Z which is defined as:

                                  Z = (height_of_image*width_of_image / (x+y)) % height_of_image)
Here x and y are two variables for which we have calculated them using an unique method. The
method goes by:

                                  xkey, ykey, zkey = lorenz_key(0.01, 0.02, 0.03, img.shape[0]*img.shape[1])
                                  shiftkey = sum(xkey+ykey+zkey)
                                  x,y=divide(shiftkey)
                                  x=digSum(x)
                                  y=digSum(y)
