## Exporaxia 
in Peter Watts Novels, after Blind Sight a man experiences 1/4 the gravity and is concerned about 200m falls, lets see how time, distance and acceleration affect one another in a hypothetical situation.

since we know that space ships have reduced air pressure, and a higher ratio of oxygen we can neglect drag, it is afterall a very annoying thing to deal with.

## Linear Approximation

We make the acceration of our man a linear approximation


```python
gravity = 9.8 #m/(s*s)
fall = 200 #m
```

since well say our man starts at 0 velocity, as he is on a ladder falling well.


```python
velocity_0 = 0 #m/s
```

Now we can do some of that sweet sweet infinity calculus, sponsored by lebinez notation and marvel.

$$ velocity = \int gravity \ ds = \int acceleration \ ds $$

$$ power rule \int k/{s^2} \,ds \,= -k/{s} + C = \frac{acceleration}{2}*s$$
$$ velocity = \frac{-k}{s} + C = \frac{a}{2}*s$$

Since we know that velocity is zero at the start we can solve for c (all we really need is just one defined point to start assuming a postive t time (for this equation at least)

$$ {velocity}_0 = 0$$
$$ 0 + C = 0$$

$$ C = 0 $$



Lets solve for time because we know our acceleration and distance of the fall

$$ s* \frac{-k}{s}= \frac{a}{2}*s*s$$




$$ -k = \frac{as^2}{2} $$
$$ \frac{-2k}{a} = s^2 $$
$$ \sqrt{\frac{-2k}{a}} = s $$

Now that we have an equation for time in seconds whose variables are known to us, lets plug them in. Well swap the sign on s and approach it to be backwards so the sign lines up and we don't have an imaginary number. This is a safer assumption as general motion is described as being reversible, although that's not true in newer models, it's enough for a falling person.


```python
s = ((2*fall)/(gravity))**(1/2)
print( s, "in seconds")
```

    6.388765649999399 in seconds


Great, now lets plug in our time to our velocity equation $$ \frac{m}{s} $$ to see how fast a normal fall is.



```python
velocity = fall/s
print(velocity, "m/s")
```

    31.304951684997054 m/s


We'll call that a splatter on the ground

## Trying with 1/4th the gravity


```python
gravity = 9.8/4 #m/(s*s)
fall = 200 #m
```


```python
s = ((2*fall)/(gravity))**(1/2)
print( s, "in seconds")
```

    12.777531299998799 in seconds



```python
velocity = fall/s
print(velocity, "m/s")
```

    15.652475842498527 m/s


Lets convert to freedom units, as a person excluded from the USA I'm sure Peter Watt's will appreciate it


```python
ratio = 2.24 #mph/(m/s)

velocity_mph = ratio*velocity

print(velocity_mph, "mph")
```

    35.0615458871967 mph


## Analysis
According to [Motor Biscuit](https://www.motorbiscuit.com/speed-die-car-crash/) you have ~90% chance of surviving that speed of a car crash as a pedestrian. Now my mother was hit at 45 mph and still survived, only  with completely shattered arm, and two feet. So it is survivable, but you be in a pulp. With the sci fi tech to revive humans exposed to massive radiation tumors in blind sight, the concern is there, but now sounds a bit whiny but thats a biologist for you.

# Below is my failure to try to reason velocity by liking it to distance

## Converting Velocity to meters

Since velocity is in $$ \frac{m}{s} $$ lets take the integral of velocity with respect to time to get meters traveled.

$$ \int -k/{s} \,ds $$

$$ k* \ln | s | + C $$

Since are starting point is at the top we can assume that we havent moved until the fall, thus 

$$ distance_0 = 0 $$

$$ 0 + C = 0 $$
$$ C = 0 $$

$$ {e^ {\ln s} }^k $$ = $$ s^k $$

## Lets try to determine how a change in distance affects the change in time, since we know the distance, lets solve for time and then plug that time into our acceleration equation to know our velocity.

$$ \int_{0}^{200} -m/{s} \,dm $$
$$ \frac{m^2}{2s} + C $$

Since we start at the top of the fall, having fallen no distance, lets assume that distance travelled 0 at time 0.

$$ 0 + C = 0 $$
Thus
$$ \frac{m^2}{2s} $$

Now lets solve to time in seconds, since we have units $$\frac{m^2}{2s} $$ lets divide by accleration $$ 9.8\frac{m}{s^2}$$ 
to get $$ \frac{m*s}{2*9.8} $$

Now we know that we have a fall of  200m so lets divide by distance to get our time in seconds

$$ \frac{\frac{m*s}{2}}{distance* 9.8}$$



```python

```


```python
(9.8/2)/200
```




    0.0245



Now since we previously defined accleration as $$m/{s^2} $$ let make an equation relating distance to velocity, and since we know that velocity is $$ -\frac{m}{s} + 0 $$ lets multiple accleraton by time in seconds to get velocity.

$$ (m/{s^2})(\frac{\frac{9.8m}{2}}{distance (fallen)}s) = \frac{\frac{9.8m^2}{2s}}{distance\ m}$$

Thus we see that under linear acceleration velocity is the average of the start of time and end time plus our intital velocity.

## Now the Programing

After solving for the equation of distance 

$$ \frac{9.8}{2} m/s * distance(fallen)$$


```python

```
