# About
This repository contains pure-python + numpy + numba efficient implementation of fft - based polynomial evaluation, that works 2-3 times faster than `numpy` default implementation

# Showcase

```py
x = np.linspace(-1,1,100000)
coefs = np.random.normal(0,1,50001)
pol = Polynomial(coefs)
```

```py
y1=pol.evaluate(x) # takes ~26 sec
```

```py
y3=np.polyval(coefs[::-1],x) # takes ~6 sec
```

```py
y2=pol.evaluate_fft(x) # takes ~2.5 sec
```

Results difference
```py
print(np.max(np.abs(y1-y2)))
print(np.max(np.abs(y2-y3)))
```
```
1.9042545318370685e-11
1.951150352397235e-11
```