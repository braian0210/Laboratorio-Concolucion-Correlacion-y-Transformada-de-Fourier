# Laboratorio-Concolucion-Correlacion-y-Transformada-de-Fourier
Objetivos

-Comprender la convolución como una operación que permite obtener la
respuesta de un sistema discreto ante una entrada determinada.

-Analizar la correlación como medida de similitud entre dos señales. 

-Aplicar la Transformada de Fourier como herramienta de análisis en el
dominio de la frecuencia. 

Resumen

Parte A

Para ésta parte de la práctica, teniendo en cuenta el sistema h[n] = {dígitos del código del carnet estudiantil } y la
señal x[n] = {dígitos de la cédula de ciudadania} cada integrante del grupo, realizará lo siguiente:

1.Encuentrar la señal 𝑦[𝑛] resultante de la convolución usando sumatorias (a
mano).

2.Encontrar la representación gráfica y secuencial (a mano). 

A continuación se adjuntaran imágenes de los procedimientos que realizó cada uno de los integrantes para el desarrollo de los numerales 1 y 2.

Integrante1-Braian 

Integrante2 David

Integrante3 Angélica

3.Encontrar la señal 𝑦[𝑛] resultante de la convolución usando Python

4.Encontrar la representación gráfica y secuencial usando Python. 

Para resolver los numerales 3 y 4, se adjuntaran los códigos y gráficas elaborados en google colab.

Integrante1-Braian 

```
import numpy as np
import matplotlib.pyplot as plt
h1 = np.array([5, 6, 0, 0, 8, 5, 3])
x1 = np.array([1, 0, 0, 3, 6, 6, 1, 2, 7, 2])
y1 = np.convolve(h1, x1, mode='full')
print("h1(n) =", h1)
print("x1(n) =", x1)
print("\n" + "="*50)
print("\nResultado De La Concolución:")
print("y1(n) = {", end="")
for i, valor in enumerate(y1):
    if i < len(y1) - 1:
        print(f"{int(valor)}, ", end="")
    else:
        print(f"{int(valor)}", end="")
print("}")
# Graficar las secuencias
plt.figure(figsize=(12, 10))
# Para h(n)
plt.subplot(3, 1, 1)
plt.stem(range(len(h1)), h1, basefmt='k-', linefmt='b-', markerfmt='bo')
plt.title('h1(n) = {5,6,0,0,8, 5, 3}')
plt.xlabel('n')
plt.ylabel('Amplitud')
plt.grid(True, alpha=0.3)
plt.xlim(-1, len(h1))

# Para x(n)
plt.subplot(3, 1, 2)
plt.stem(range(len(x1)), x1, basefmt='k-', linefmt='g-', markerfmt='go')
plt.title('x1(n) = {1, 0, 0, 3, 6, 6, 1, 2, 7, 2}')
plt.xlabel('n')
plt.ylabel('Amplitud')
plt.grid(True, alpha=0.3)
plt.xlim(-1, len(x1))

# Subplot para y1(n) - convolución
plt.subplot(3, 1, 3)
plt.stem(range(len(y1)), y1, basefmt='k-', linefmt='r-', markerfmt='ro')
plt.title('y1(n) = h1(n) * x1(n) (Convolución)')
plt.xlabel('n')
plt.ylabel('Amplitud')
plt.grid(True, alpha=0.3)
plt.xlim(-1, len(y1))

plt.tight_layout()
plt.show()
```

Obteniendo

```
h1(n) = [5 6 0 0 8 5 3]
x1(n) = [1 0 0 3 6 6 1 2 7 2]
==================================================
Resultado De La Concolución:
y1(n) = {5, 6, 0, 15, 56, 71, 44, 40, 110, 139, 68, 39, 69, 57, 31, 6}
```

<img width="739" height="614" alt="image" src="https://github.com/user-attachments/assets/802bcb90-230d-4669-9763-03ec72e65e13" />


Integrante2 David

```
import numpy as np
import matplotlib.pyplot as plt
h1 = np.array([5, 6, 0, 0, 8, 2, 0])
x1 = np.array([1, 0, 2, 7, 5, 2, 2, 9, 0, 3])
y1 = np.convolve(h1, x1, mode='full')
print("h1(n) =", h1)
print("x1(n) =", x1)
print("\n" + "="*50)
print("\nResultado De La Concolución:")
print("y1(n) = {", end="")
for i, valor in enumerate(y1):
    if i < len(y1) - 1:
        print(f"{int(valor)}, ", end="")
    else:
        print(f"{int(valor)}", end="")
print("}")
# Graficar las secuencias
plt.figure(figsize=(12, 10))
# Para h(n)
plt.subplot(3, 1, 1)
plt.stem(range(len(h1)), h1, basefmt='k-', linefmt='b-', markerfmt='bo')
plt.title('h1(n) = {5, 6, 0, 0, 8, 2, 0}')
plt.xlabel('n')
plt.ylabel('Amplitud')
plt.grid(True, alpha=0.3)
plt.xlim(-1, len(h1))

# Para x(n)
plt.subplot(3, 1, 2)
plt.stem(range(len(x1)), x1, basefmt='k-', linefmt='g-', markerfmt='go')
plt.title('x1(n) = {1, 0, 2, 7, 5, 2, 2, 9, 0, 3}')
plt.xlabel('n')
plt.ylabel('Amplitud')
plt.grid(True, alpha=0.3)
plt.xlim(-1, len(x1))

# Subplot para y1(n) - convolución
plt.subplot(3, 1, 3)
plt.stem(range(len(y1)), y1, basefmt='k-', linefmt='r-', markerfmt='ro')
plt.title('y1(n) = h1(n) * x1(n) (Convolución)')
plt.xlabel('n')
plt.ylabel('Amplitud')
plt.grid(True, alpha=0.3)
plt.xlim(-1, len(y1))

plt.tight_layout()
plt.show()
```

Obteniendo

```
h1(n) = [5 6 0 0 8 2 0]
x1(n) = [1 0 2 7 5 2 2 9 0 3]
==================================================
Resultado De La Concolución:
y1(n) = {5, 6, 10, 47, 75, 42, 38, 117, 108, 41, 38, 76, 18, 24, 6, 0}
```

<img width="736" height="613" alt="image" src="https://github.com/user-attachments/assets/25675f1e-d2b2-42fb-a0a9-cb40faf1ca2b" />


Integrante3 Angélica

Parte B

Para la parte b de la práctica, se definiran las señales 𝑥1[𝑛𝑇𝑠] = cos(2𝜋100𝑛𝑇𝑠) 𝑝𝑎𝑟𝑎 0 ≤ 𝑛 < 9, 𝑥2[𝑛𝑇𝑠] = sin(2𝜋100𝑛𝑇𝑠) 𝑝𝑎𝑟𝑎 0 ≤ 𝑛 < 9 para 𝑇𝑠 = 1.25𝑚s, con el fin de encontar lo siguiente:

1.Encontrar la correlación cruzada entre ambas señales

2.Encontrar la representación gráfica y describa la secuencia resultante. 

3.Responder ¿En qué situaciones resulta útil aplicar la correlación cruzada en
el procesamiento digital de señales? 

Parte C

Para la parte c, con ayuda del generador de señales biológicas, se generará una señal biológica Eog, con el fin de:

1.Determinar la frecuencia de Nyquist para la señal generada

Tomando la frecuencia maxima de 100 y como Fnyquist es 2 veces Fmaxima, entonces Fnyquist es de 200

2.Digitalizar la señal usando una frecuencia de muestreo de 4 veces la frecuencia de Nyquist

tomando una frecuencia de muestreo de 800hz se realizo el siguiente codigo de captura de la señal EOG con daq

```
import numpy as np  
import nidaqmx
from nidaqmx.constants import AcquisitionType, READ_ALL_AVAILABLE
import matplotlib.pyplot as plt

rate = 800.0  # Hz
duration = 5  # segundos
muestras = int(rate * duration)

with nidaqmx.Task() as task:
    task.ai_channels.add_ai_voltage_chan("Dev2/ai1")
    task.timing.cfg_samp_clk_timing(rate, sample_mode=AcquisitionType.FINITE, samps_per_chan=muestras)
    data = task.read(READ_ALL_AVAILABLE)
    plt.plot(data)
    plt.ylabel('Amplitud')
    plt.title('señal EOG')
    plt.ylim(-3, 3) 
    plt.show()
    
np.savetxt(r"C:\Users\USUARIO\Desktop\datos_parteC2.csv", data, delimiter=",")
```
Y su visualizacion en Colab con una grafica mas comoda de ver con el codigo:

```
graficacaptura = pd.read_csv("/content/drive/Shareddrives/Labs procesamiento de señales/Lab 2/datos_parteC3.csv")

# Graficar la señal
plt.figure(figsize=(15, 3)) # Increased the width to 12
plt.plot(graficacaptura, label="Señal ECG")
plt.xlabel("(800muestras/seg)")
plt.ylabel("Amplitud (V)")
plt.title("Señal EOG Capturada")
plt.legend()
plt.show()
```

3.Caracterizar la señal obteninedo:

a.Media, mediana, desviación estándar, máximo, mínimo, convolución,  correlación y transformada de Fourier.

b.Clasificar la señal según su tipo (determinística/aleatoria,
periódica/aparádica, analógica/digital).

4.Aplicar la Transformada de Fourier a la señal y graficar:

a.La transformada de la señal

b.Su densidad espectral de potencia

c.Analice los estadísticos en el dominio de la frecuencia:

i.Frecuencia media

ii.Frecuencia mediana

iii.Desviación estándar

iv.Histograma de frecuencias






