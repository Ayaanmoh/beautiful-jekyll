### Brief Intro!

Computer Science graduate student at North Carolina State University. I hail from Hyderabad, a sprawling metropolitan city in India.


<table>
  <tr>
    <td>Professional</td>
     <td>Casual</td>
     <td>Holiday Mention</td>
  </tr>
  <tr>
    <td><img src="https://drive.google.com/uc?export=view&id=1HwUpK411M2Cay9ZvXUBjRTYrOfmNI-Ht" width=270 height=405></td>
    <td><img src="https://drive.google.com/uc?export=view&id=17b-MktAftWTMuZdjLRnAVO-Q5hU5VjNG" width=270 height=405></td>
    <td><img src="https://drive.google.com/uc?export=view&id=1bQfNxBupfjmNY3jDrt9sO_kqdzfseBYo" width=270 height=405></td>
  </tr>
 </table>


### Skills

* Proficient in Python
* Experience in developing full stack applications with Javascript and MongoDB
* Dabbled with deploying my applications and configuring pipelines on Microsoft Azure.

### Interests
* Love to play soccer. An avid fan of football club FC Barcelona.
* An Astrophile. Happy to stargaze all night and contemplate about the universe.
* Science fiction and courtroom drama are my favorite genres.

### Code Snippet

Gravitational N-Body Simulation with Vectorization.
Vectorized code refers to operations that are performed on multiple components of a vector at the
same time (in one statement).

* Vectorized version of the function that computes the acceleration on all the particles

```
def getAcc( pos, mass, G, softening ):
	"""
    Calculate the acceleration on each particle due to Newton's Law 
	pos  is an N x 3 matrix of positions
	mass is an N x 1 vector of masses
	G is Newton's Gravitational constant
	softening is the softening length
	a is N x 3 matrix of accelerations
	"""
	# positions r = [x,y,z] for all particles
	x = pos[:,0:1]
	y = pos[:,1:2]
	z = pos[:,2:3]

	# matrix that stores all pairwise particle separations: r_j - r_i
	dx = x.T - x
	dy = y.T - y
	dz = z.T - z

	# matrix that stores 1/r^3 for all particle pairwise particle separations 
	inv_r3 = (dx**2 + dy**2 + dz**2 + softening**2)
	inv_r3[inv_r3>0] = inv_r3[inv_r3>0]**(-1.5)

	ax = G * (dx * inv_r3) @ mass
	ay = G * (dy * inv_r3) @ mass
	az = G * (dz * inv_r3) @ mass
	
	# pack together the acceleration components
	a = np.hstack((ax,ay,az))
	return a
  
 ```
<p align="center">
  <img src="https://miro.medium.com/max/1024/1*JuuCy0bJya1__ggeG9MWTw.gif"  width=370 height=405>
</p>




