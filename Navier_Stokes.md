# Simulación de Navier–Stokes

Implementación numérica en Python del flujo incompresible dentro de una cavidad cuadrada o cúbica con una pared móvil (*lid-driven cavity*).

El movimiento de la pared genera la circulación del fluido y permite observar la formación del vórtice principal dentro de la cavidad.

## Método utilizado

El código resuelve las ecuaciones de Navier–Stokes incompresibles mediante:

- discretización espacial en una malla escalonada;
- aproximaciones por diferencias finitas/volúmenes finitos;
- corrección iterativa de presión y velocidad tipo SIMPLE;
- integración temporal con un paso limitado por condiciones convectivas y difusivas;
- control del residuo de continuidad.

El número de Reynolds se define como

```text
Re = |U| L / nu
```

donde `U` es la velocidad de la pared, `L` el largo de la cavidad y `nu` la viscosidad cinemática.

## Archivos

- `navier_stokes_2D_estilo_cristobal.py`: simulación de la cavidad en dos dimensiones.
- `gif_navier_stokes_2D_estilo_cristobal.py`: generación del GIF 2D.
- `navier_stokes_3D_estilo_cristobal.py`: simulación tridimensional.
- `gif_navier_stokes_3D_estilo_cristobal.py`: visualización de los resultados 3D.

## Ejecución

Instalar las dependencias:

```bash
python -m pip install numpy matplotlib pillow
```

Para ejecutar la versión 2D en un notebook:

```python
%run navier_stokes_2D_estilo_cristobal.py
%run gif_navier_stokes_2D_estilo_cristobal.py
```

Los dos archivos deben ejecutarse en la misma sesión, ya que el código del GIF utiliza los resultados almacenados por la simulación.

El GIF se guarda como:

```text
navier_stokes_2D.gif
```

## Parámetros principales

Los parámetros pueden modificarse al comienzo del archivo:

```python
n_puntos = 31
n_tiempos = 1000
Re = 100
viento = -0.1
```

También pueden ajustarse las tolerancias, el número máximo de iteraciones y los factores de relajación.

## Limitaciones

- Es una implementación educativa, no un software CFD de uso industrial.
- El costo computacional aumenta rápidamente al refinar la malla, especialmente en 3D.
- Los resultados dependen de la convergencia de la corrección de presión y del tamaño del paso temporal.
- Para números de Reynolds elevados pueden ser necesarios esquemas más robustos y mallas más finas.

## Tecnologías

- Python
- NumPy
- Matplotlib
- Pillow
