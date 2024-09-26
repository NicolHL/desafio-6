# desafio-6
import numpy as np
import matplotlib.pyplot as plt

# Definición de la matriz original A
A = np.array([[4, 2], [3, 1]])

# Definición de la matriz identidad
I = np.identity(2)

# Cálculo del determinante de la matriz original
det_A = np.linalg.det(A)

# Lista para almacenar determinantes modificados
det_values = []

# Realizamos cambios pequeños en el valor [0,0] de la matriz A
changes = np.linspace(4, 4.1, 50)
for change in changes:
    A_mod = np.array([[change, 2], [3, 1]])
    det_mod = np.linalg.det(A_mod)
    det_values.append(det_mod)

# Creación del gráfico
plt.figure(figsize=(10, 6))
plt.plot(changes, det_values, marker='o', linestyle='-', color='b')
plt.axhline(y=det_A, color='r', linestyle='--', label=f'Determinante Original = {det_A:.2f}')
plt.xlabel('Valor en la posición [0,0] de la matriz')
plt.ylabel('Determinante')
plt.title('Cambio del Determinante con Pequeñas Modificaciones en la Matriz')
plt.legend()
plt.grid()
plt.show()
