# bare-critital-mass-alpha-rossi
bare critial mass and alpha rossi


## density
+ $\rho_0 = 19.85 \ {\rm g/cm^3}$.
+ $M = 8 \ {\rm kg}$.
+ $x \in \{0.2, 0.4, 0.6, 0.8, 1, 2, 3, 4, 5, 6\}$.

```python
import math
rho0 = 19.8 # g/cm^3
M = 8 # kg
x = [0.2, 0.4, 0.6, 0.8, 1, 2, 3, 4, 5, 6]
rho = [i * rho0 for i in x] # g/cm^3

print("No\tx\trho\tR")

for i in range(len(x)):
  print(f'{i+1:02d}', end='\t')
  print(f'{x[i]:.2f}', end='\t')
  print(f'{rho[i]:.2f}', end='\t')
  R = 100 * (3 / (4 * math.pi) * (M / (rho[i] * 1000)))**(1. / 3.) # cm
  print(f'{R:.04f}')
```



## parameters
MCNP44 code
+ SQ mass: 8 kg
+ Normal Plutonium density $\rho_0$: Alpha Phases
+ Nuclear Data Library: JENDL3.3

$$
R = \sqrt[3]{\left( \frac{3}{4\pi} \right) \frac{M}{\rho}}
$$

  + $M$ Mass SQ [kg]
  + $\rho$ Plutonium Density [g/cc]
  
$$
x = \frac{\rho}{\rho_0}, \ \ \ \ \rho = x \rho_0
$$


$$
\alpha = \frac{k_{\rm eff} - 1}{\tau_0}
$$


No | Evaluated Perameters | Unit
:-: | :- | :-:
1 | $k_{\rm eff}$ | [-]
2 | Prompt Life Time | [s]
3 | Alfa Rossi | [1/s]