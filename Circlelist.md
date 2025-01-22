```python
import numpy as np
```

## Lets define a variable list, that specifies the number of points we want


```python
degrees = []
```


```python
for i in range(0,10):
    degrees.append(i)
print(degrees)
```

    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]


This gives us a list of numbers, lets make it mapped to the range of numbers accepted on on circle.

Refering to the numpy sin function the input value is radians. Since $$2*\pi\ radians $$  is the range on a circle, lets map our resolution to that.


```python
klist = []

for i in range(0,len(degrees)):
    k = 2*np.pi*degrees[i] / max(degrees)
    klist.append(k)

klist
```




    [0.0,
     0.6981317007977318,
     1.3962634015954636,
     2.0943951023931953,
     2.792526803190927,
     3.490658503988659,
     4.1887902047863905,
     4.886921905584122,
     5.585053606381854,
     6.283185307179586]



Now we have a list that is in the range of our function, lets see what the output is when we take the sin and cos.


```python
xlist = []

for i in range(0, len(klist)):
    x = np.cos(klist[i])
    xlist.append(x)

xlist
```




    [np.float64(1.0),
     np.float64(0.766044443118978),
     np.float64(0.17364817766693041),
     np.float64(-0.4999999999999998),
     np.float64(-0.9396926207859083),
     np.float64(-0.9396926207859084),
     np.float64(-0.5000000000000004),
     np.float64(0.17364817766692997),
     np.float64(0.7660444431189779),
     np.float64(1.0)]



This is in np float, lets convert to python native


```python
native_xlist = []
for i in range(0,len(xlist)):
    j = xlist[i].item()
    native_xlist.append(j)
native_xlist    
```




    [1.0,
     0.766044443118978,
     0.17364817766693041,
     -0.4999999999999998,
     -0.9396926207859083,
     -0.9396926207859084,
     -0.5000000000000004,
     0.17364817766692997,
     0.7660444431189779,
     1.0]



There it is, one can refer to [this](https://stackoverflow.com/questions/9452775/converting-numpy-dtypes-to-native-python-types) for converting types


```python
ylist = []

for i in range(0, len(klist)):
    x = np.sin(klist[i])
    ylist.append(x)

native_ylist = []
for i in range(0,len(ylist)):
    j = ylist[i].item()
    native_ylist.append(j)
native_ylist    
```




    [0.0,
     0.6427876096865393,
     0.984807753012208,
     0.8660254037844388,
     0.3420201433256689,
     -0.34202014332566866,
     -0.8660254037844384,
     -0.9848077530122081,
     -0.6427876096865396,
     -2.4492935982947064e-16]



### All works, lets throw some known values to check


```python
degrees = [2*np.pi, np.pi,np.pi/2]


klist = []

for i in range(0,len(degrees)):
    k = 2*np.pi*degrees[i] / max(degrees)
    klist.append(k)



xlist = []

for i in range(0, len(klist)):
    x = np.cos(klist[i])
    xlist.append(x)

native_xlist = []
for i in range(0,len(xlist)):
    j = xlist[i].item()
    native_xlist.append(j)


ylist = []

for i in range(0, len(klist)):
    y = np.sin(klist[i])
    ylist.append(y)

native_ylist = []
for i in range(0,len(ylist)):
    j = ylist[i].item()
    native_ylist.append(j)

print(native_xlist)

print(native_ylist)
```

    [1.0, -1.0, 6.123233995736766e-17]
    [-2.4492935982947064e-16, 1.2246467991473532e-16, 1.0]


It works Lets go, lets try drawing next [[Drawing]] 