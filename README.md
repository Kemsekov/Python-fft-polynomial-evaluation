# About
This repository contains pure-python + numpy + numba implementation of fft - based polynomial evaluation

# Showcase

```py
x = np.linspace(-1,1,100000)
coefs = np.random.normal(0,1,90000)
pol = Polynomial(coefs)
```

```py
y1=pol.evaluate(x) # takes ~6.6sec
```

```py
y2=pol.evaluate_fft(x) # takes ~6.7 sec

```

```py
y3=np.polyval(coefs[::-1],x) # takes ~11.1 sec
```

Results difference
```py
print(np.max(np.abs(y1-y2)))
print(np.max(np.abs(y2-y3)))
```
```
9.109868415180244e-11
9.109868415180244e-11
```