import numpy as np
import matplotlib.pyplot as plt
from scipy.interpolate import CubicSpline

# Définition des points de la fonction et de leurs valeurs
points = np.array([-2, -1, 0, 1, 2, 3])
valeurs = np.array([1, 0.5, 0.5, -1.5, -3, -1])

# Création d'un intervalle pour l'axe des x
x = np.linspace(-2, 3, 500)

# Approximation de la fonction f(x) avec une interpolation spline cubique
cs = CubicSpline(points, valeurs, bc_type='natural')

# Tracer la courbe
plt.figure(figsize=(8, 6))
plt.plot(x, cs(x), label="Courbe approximée de f(x)", color='b')
plt.scatter(points, valeurs, color='red', zorder=5, label="Points donnés")
plt.title("Approximation de la courbe de la fonction f(x)")
plt.xlabel("x")
plt.ylabel("f(x)")
plt.grid(True)
plt.legend()
plt.show()
