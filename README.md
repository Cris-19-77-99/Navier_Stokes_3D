# Simulación de Navier–Stokes

Implementación numérica en Python del flujo incompresible dentro de una caja con una pared movida por el viento.

## Método utilizado

El código resuelve las ecuaciones de Navier–Stokes en el caso incompresible, para el cual se emplea una discretización espacial en una malla escalonada para luego resolver aproximaciones por diferencias finitas/volúmenes finitos agregando además una corrección iterativa de presión y velocidad. Son considerados para la integración temporal las limitaciones por condiciones convectividad y difusividad.

