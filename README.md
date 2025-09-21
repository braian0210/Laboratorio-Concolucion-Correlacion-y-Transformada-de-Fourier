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

A continuación se adjuntaran imágenes de los procedimientos que realizó cada uno de los integrantes para hallar y(n).

Integranre 1 Braian

![Imagen de WhatsApp 2025-09-21 a las 15 11 36_474db755](https://github.com/user-attachments/assets/f1193ea5-e684-4993-b127-9ced3238d82e)


Integrante 2 Angélica
![Imagen de WhatsApp 2025-09-20 a las 19 40 27_a37c1d32](https://github.com/user-attachments/assets/1de222bf-f5a7-46de-a49a-6d60c41e831b)
![Imagen de WhatsApp 2025-09-20 a las 19 41 22_a929636c](https://github.com/user-attachments/assets/10aed1f4-14e1-4db8-a4b4-debe90bb5238)

Integrante 3 David
![Imagen de WhatsApp 2025-09-20 a las 20 02 44_d0926bb0](https://github.com/user-attachments/assets/e2c0794a-9709-41ed-bc54-5b0604fae241)

2.Encontrar la representación gráfica y secuencial (a mano). 

A continuación se adjuntaran imágenes de las gráficas que realizó cada uno de los integrantes. 

Integrante1-Braian 

![Imagen de WhatsApp 2025-09-21 a las 15 14 31_676438b0](https://github.com/user-attachments/assets/f6c50152-a327-4b3e-a1af-0e33a8f24b03)

![Imagen de WhatsApp 2025-09-21 a las 15 11 37_a2a36209](https://github.com/user-attachments/assets/81eea857-a327-4c9e-8985-ae4966f15951)

Integrante2 Angélica
![Imagen de WhatsApp 2025-09-20 a las 19 41 21_2be94dd1](https://github.com/user-attachments/assets/4eb5fd1d-0da2-4903-944f-0e169ee848dd)
![Imagen de WhatsApp 2025-09-20 a las 19 41 22_7997f000](https://github.com/user-attachments/assets/c685442e-bb02-4662-9a99-7776213845ca)
Integrante3 David
![Imagen de WhatsApp 2025-09-20 a las 20 08 30_8b56eadb](https://github.com/user-attachments/assets/cd572aee-5365-47ef-9286-39ee21280821)


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


Integrante2 Angélica

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


Integrante3 David

```
import numpy as np
import matplotlib.pyplot as plt
h1 = np.array([5, 6, 0, 0, 8, 5, 8])
x1 = np.array([1, 0, 5, 0, 6, 0, 4, 4, 7, 5])
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
plt.title('h1(n) = {5, 6, 0, 0, 8, 5, 8}')
plt.xlabel('n')
plt.ylabel('Amplitud')
plt.grid(True, alpha=0.3)
plt.xlim(-1, len(h1))

# Para x(n)
plt.subplot(3, 1, 2)
plt.stem(range(len(x1)), x1, basefmt='k-', linefmt='g-', markerfmt='go')
plt.title('x1(n) = {1, 0, 5, 0, 6, 0, 4, 4, 7, 5}')
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
h1(n) = [5 6 0 0 8 5 8]
x1(n) = [1 0 5 0 6 0 4 4 7 5]

==================================================

Resultado De La Concolución:
y1(n) = {5, 6, 25, 30, 38, 41, 68, 69, 147, 97, 110, 52, 108, 107, 81, 40}
```

<img width="737" height="610" alt="image" src="https://github.com/user-attachments/assets/c922797f-19c1-44f7-94c5-db1d90674b16" />


Parte B

Para la parte b de la práctica, se definiran las señales 𝑥1[𝑛𝑇𝑠] = cos(2𝜋100𝑛𝑇𝑠) 𝑝𝑎𝑟𝑎 0 ≤ 𝑛 < 9, 𝑥2[𝑛𝑇𝑠] = sin(2𝜋100𝑛𝑇𝑠) 𝑝𝑎𝑟𝑎 0 ≤ 𝑛 < 9 para 𝑇𝑠 = 1.25𝑚s, con el fin de encontar lo siguiente:

1.Encontrar la correlación cruzada entre ambas señales
```
from re import S

Ts = 0.00125   # milisegundos
n = np.arange(0, 9)   # 0 <= n < 9
f = 100               # frecuencia en Hz
w = 2 * np.pi * f

t = n * Ts
x1 = np.cos(w * n * Ts)
x2 = np.sin(w * n * Ts)

# Correlación cruzada
r = np.correlate(x1, x2, mode="full")
lags = np.arange(-len(x2)+1, len(x1))

print(lags)
print(r)

# Gráfico de la correlación
plt.stem(lags, r, basefmt=" ")
plt.xlabel("Lag (muestras)")
plt.ylabel("r_xy[L]")
plt.title("Correlación cruzada entre x1 y x2")
plt.grid(True)
plt.show()
```
<img width="598" height="566" alt="image" src="https://github.com/user-attachments/assets/85446809-aaec-42f9-9e23-b783f02ea058" />


2.Encontrar la representación gráfica y describa la secuencia resultante. 
```
from re import S

Ts = 0.00125   # milisegundos
n = np.arange(0, 9)   # 0 <= n < 9
f = 100               # frecuencia en Hz
w = 2 * np.pi * f

t = n * Ts
x1 = np.cos(w * n * Ts)
x2 = np.sin(w * n * Ts)


df = pd.DataFrame({
    "n": n,
    "t_s": t,
    "t_ms": t * 1e3,
    "x1_cos": x1,
    "x2_sin": x2
})
df.to_csv('signals_x1_x2.csv', index=False)

plt.figure(figsize=(8,4))
plt.plot(t, x1, marker='o', label='x1[nTs] = cos(2π100 n Ts)')
plt.plot(t, x2, marker='s', label='x2[nTs] = sin(2π100 n Ts)')
plt.xlabel('t (s)')
plt.ylabel('Amplitud')
plt.title('Señales muestreadas: x1 y x2 (Ts = 1.25 ms)')
plt.legend()
plt.grid(True)
plt.tight_layout()
plt.show()
```
<img width="819" height="381" alt="image" src="https://github.com/user-attachments/assets/fbfe109d-5c84-4bf9-b2ce-06c76d07c6d5" />


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
<img width="1245" height="316" alt="image" src="https://github.com/user-attachments/assets/72eba35b-6fc7-4c11-87e8-45d7c93457d9" />


3.Caracterizar la señal obteninedo:

a.Media
```
media_graficacaptura=np.mean(graficacaptura)
print(f"media de la señal:{mean_graficacaptura:.6f}")
```
<img width="242" height="33" alt="image" src="https://github.com/user-attachments/assets/3e3d2bc4-48ce-4deb-97bb-7c9385e26b17" />

b.mediana
```
mediana_graficacaptura = np.median(graficacaptura)
print(f"Mediana de la señal: {median_graficacaptura:.6f}")
```
<img width="227" height="23" alt="image" src="https://github.com/user-attachments/assets/43f15f47-489f-4e58-8fd9-a4f1ceb25faf" />

c.desviación estándar
```
valores = graficacaptura.iloc[:,0].to_numpy()

desviacion_graficacaptura = np.std(valores)

print(f"Desviación estándar: {desviacion_graficacaptura:.6f}")
```
<img width="219" height="20" alt="image" src="https://github.com/user-attachments/assets/761c669a-fc64-4e89-b227-9a93681f68ba" />



d.máximo y mínimo 
```
maximo = np.max(graficacaptura)
minimo = np.min(graficacaptura)

print(f"Valor máximo de la señal: {maximo:.6f}")
print(f"Valor mínimo de la señal: {minimo:.6f}")
```
<img width="303" height="42" alt="image" src="https://github.com/user-attachments/assets/b67ee4f9-d9a1-4a7d-b3e3-0f704a015d25" />

e.convolución
```
filtroparaconvolucion = np.ones(5) / 5
convolucion = np.convolve(x, h, mode="same")
print(f"convolucion ={convolucion}")
```
<img width="662" height="45" alt="image" src="https://github.com/user-attachments/assets/4392e28b-c977-41ef-972e-bc972a38433b" />

correlación
```
corr = np.correlate(x, x, mode="full")
lags = np.arange(-len(x) + 1, len(x))

# 3) Graficar
plt.figure(figsize=(12,4))
plt.plot(lags, corr)
plt.title("correlación de la señal")
plt.xlabel("Desplazamiento (lags)")
plt.ylabel("Correlación")
plt.grid(True)
plt.show()
```
<img width="996" height="393" alt="image" src="https://github.com/user-attachments/assets/1ec67694-37de-4f2e-a4c3-d32580cae76d" />

transformada de Fourier.
```
data = pd.read_csv("/content/drive/Shareddrives/Labs procesamiento de señales/Lab 2/EOG.txt")
x = data.iloc[:, 0].values

fs = 800
N = len(x)
duracion = N / fs
Xfurier = np.fft.rfft(x)
f = np.fft.rfftfreq(N, d=1/fs)
mag = np.abs(Xfurier)
P = (np.abs(Xfurier)**2) / N

plt.figure(figsize=(8, 5))
plt.plot(f, mag, color="Cyan", label="FFT (magnitud)")
plt.xlabel("Frecuencia (Hz)")
plt.ylabel("Magnitud")
plt.title("Transformada de Fourier")
plt.legend()
plt.grid(True)
plt.axis([1, 30, 0, 100])  # Explicitly set x-axis to match your expected range
plt.show()
```
<img width="704" height="470" alt="image" src="https://github.com/user-attachments/assets/9f85c4ec-2c35-4682-aa90-ca77f90a913f" />

b.Clasificar la señal según su tipo (determinística/aleatoria, periódica/aparádica, analógica/digital).

Es una señal determinista puesto que posee un patron en su figura a pesar de ciertas variaciones durante cada ciclo probablemente por medicion y porque inconcientemente es imposible caracterizarla de otra forma al ser generada por un equipo La señal es periodica puesto que repite un mismo ciclo constantemente es una señal digital que intenta imitar una señal analogica ocular provocando que represente las componentes fisiologicas pero sin la capacidad de imitar la variabilidad del EOG tomado directamente

4.Aplicar la Transformada de Fourier a la señal y graficar:

a.La transformada de la señal
```
data = pd.read_csv("/content/drive/Shareddrives/Labs procesamiento de señales/Lab 2/EOG.txt")
x = data.iloc[:, 0].values

fs = 800
N = len(x)
duracion = N / fs
Xfurier = np.fft.rfft(x)
f = np.fft.rfftfreq(N, d=1/fs)
mag = np.abs(Xfurier)
P = (np.abs(Xfurier)**2) / N

plt.figure(figsize=(8, 5))
plt.plot(f, mag, color="Cyan", label="FFT (magnitud)")
plt.xlabel("Frecuencia (Hz)")
plt.ylabel("Magnitud")
plt.title("Transformada de Fourier")
plt.legend()
plt.grid(True)
plt.axis([1, 30, 0, 100])  # Explicitly set x-axis to match your expected range
plt.show()
```
<img width="704" height="470" alt="image" src="https://github.com/user-attachments/assets/8a07bd91-8a4f-42d6-9844-c9c2159ea07c" />


b.Su densidad espectral de potencia

```
plt.figure(figsize=(8,5))
plt.plot(f[:N//2], P[:N//2], color="Pink")
plt.xlabel("Frecuencia (Hz)")
plt.ylabel("Potencia")
plt.title("Densidad Espectral de Potencia (PSD)")
plt.grid(True)
plt.axis([1, 10, 0, 5])
plt.show()
```

<img width="686" height="470" alt="image" src="https://github.com/user-attachments/assets/5ef855bc-e407-4bc9-8951-fcdd56c5b234" />


c.Analice los estadísticos en el dominio de la frecuencia:

i.Frecuencia media
```
lim = f <= 30
f_band = f[lim]
mag_band = mag[lim]

f_mean = np.sum(f_band * mag_band) / np.sum(mag_band)
print(f"Frecuencia media (Hz): {f_mean:.4f}")
```
<img width="253" height="20" alt="image" src="https://github.com/user-attachments/assets/06b4da81-a627-4970-bc9d-8ec732081295" />

ii.Frecuencia mediana
```
cum_energy = np.cumsum(mag_band) / np.sum(mag_band)
f_median = f_band[np.where(cum_energy >= 0.5)[0][0]]
print(f"Frecuencia mediana (Hz): {f_median:.4f}")
```
<img width="261" height="20" alt="image" src="https://github.com/user-attachments/assets/80e53ba8-afad-48a2-8b47-951b8557e00d" />

iii.Desviación estándar
```
f_standar = np.sqrt(np.sum(((f_band - f_mean)**2) * mag_band) / np.sum(mag_band))
print(f"Desviación estándar de la frecuencia (Hz): {f_standar:.4f}")
```
<img width="408" height="20" alt="image" src="https://github.com/user-attachments/assets/c4c0e6a1-6436-4005-ba07-139825de2fda" />

iv.Histograma de frecuencias
```
plt.figure(figsize=(8,4))
plt.hist(f_band, bins=20, weights=mag_band, color="Red", alpha=0.7)
plt.xlabel("Frecuencia (Hz)")
plt.ylabel("Energía espectral")
plt.title("Histograma de frecuencias (0–30 Hz)")
plt.grid(True)
plt.show()
```
<img width="696" height="393" alt="image" src="https://github.com/user-attachments/assets/159ddee1-028d-4183-8086-e692703f3811" />







