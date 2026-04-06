# TP-1

## Nombre y legajo

- Legajo: **Completar** 
- Nombre: **Completar**

## Objetivos

El primer TP que preparamos para que resuelvan tiene como objetivos:

- que se empiecen a acostumbrar a usar git.
- que se familiaricen con el uso del lenguaje Haskell y de la herramienta Visual Studio Code.
- que entiendan el circuito básico del desarrollo de un ejercicio, desde bajar el enunciado desde un repositorio hasta completar cada parte e ir subiendo la solución en progreso en cada paso.
- utilizar pruebas automatizadas para facilitar la validación del código que escriben.

## Pre-requisitos

Necesitás haber instalado el ambiente según se explica en el [TP-0](https://classroom.github.com/a/iSl8Geaf).

## Ayuda

Si tienen dudas con Haskell pueden ayudarse todo el tiempo con esta documentación

- [Guía de lenguajes](https://docs.google.com/document/d/1oJ-tyQJoBtJh0kFcsV9wSUpgpopjGtoyhJdPUdjFIJQ/edit?usp=sharing), un resumen de las principales funciones que vienen con Haskell.
- [Hoogle](https://www.haskell.org/hoogle/), un motor de búsqueda específico para Haskell.

Aparte, siempre pueden preguntar a sus ayudantes en discord!

Y para comenzar a trabajar con Git les recomendamos [este apunte inicial de Git](https://docs.google.com/document/d/1ozqfYCwt-37stynmgAd5wJlNOFKWYQeIZoeqXpAEs0I/edit) o estos videos donde se explica como usar Git:
- [Parte 1: Qué es GIT y cómo clonar el repo basado en GitHub classroom](https://www.youtube.com/watch?v=rRKe7l-ZNvM)
- [Parte 2: Uso básico de GIT con status, add, reset, commit, push](https://www.youtube.com/watch?v=OgasfM5qJJE)
- [Parte 3: Resolución de conflictos](https://www.youtube.com/watch?v=sKcN7cWFniw)

### Probando cosas por consola

La forma que recomendamos de resolver el ejercicio es no programar todo de una y después ver si anda, si no ir probando en cada paso a medida que van programando cada función.

Para esto, les recomiendo que usen mucho `stack ghci` para probar cosas por consola, y vuelvo a linkear [esta página](https://github.com/pdep-utn/enunciados-miercoles-noche/blob/master/pages/haskell/trabajo.md#comandos-%C3%BAtiles) donde se explican un par de cositas de como usar `ghci`.

-------------------------------

# El enunciado

### Parte 0: git

Para cada integrante del grupo:
- Reemplazar nombre y legajo con tu nombre y legajo en el  README.md y subir los cambios al repositorio remoto para que el resto del equipo lo baje.

-----------------------------------

En cada punto van a tener que implementar las definiciones de algunas funciones para las que ya les vamos a dar tests que prueben que su solución esta funcionando correctamente y (en la mayoría de los casos) los tipos. Algunas de las funciones además de pedirles la implementación también les vamos a pedir que definan sus tipos.

### 1. Números 🔢

Empecemos definiendo algunas funciones simples sobre números:

- **siguiente**: toma un número como parámetro y devuelve ese número + 1.
- **esPositivo**: nos dice si un número es mayor a 0 o no. Es falso para 0.
- **inversa**: aplicar la inversa a un número nos da como resultado 1 dividido ese número. Por ejemplo, la inversa de 2 es 0.5 porque 1/2 es 0.5. **Para está función, también tienen que escribir el tipo ustedes**

---

### 1.5 Perímetros y áreas

Implementar las siguientes funciones, escribiendo su tipo:
- **perimetroCirculo** dado un radio. Ej:
```haskell
>>> perimetroCirculo 3
18.8495559215387587
```
- **perimetroCuadrado** dado un lado.
- **superficieCuadrado** dado un lado.
- **superficieCubo** dado un lado.
- **superficieCilindro** dado un radio y una altura.

----

### 2. Temperaturas 🌡️

-----------------
Podemos correr pruebas **automatizadas** en la terminal que prueban si nuestro código hace lo que queremos con:

```bash
stack test
```

Pero `stack test` puede ser un poco lento, así que también podemos instalar un programa que nos deja correrlos casi instantáneamente cada vez que hacemos un cambio en nuestro código: `ghcid`. [Guía para configurarlo](https://github.com/pdepviernestm/2021-clases/blob/main/clase-02/correrTestsMasRapidoConGhcid.md#okay-c%C3%B3mo-lo-uso)

Para conocer un poco más del testeo unitario automatizado recomendamos leer [este apunte](https://docs.google.com/document/d/17EPSZSw7oY_Rv2VjEX2kMZDFklMOcDVVxyve9HSG0mE/edit#)

-----------------

Ahora sí, al ejercicio en sí:

Las temperaturas en diferentes países se miden en grados, pero no todos usan el mismo sistema de medida. En la mayor partedel el mundo usamos los grados Celsius (°C) pero en algunos países como en Estados Unidos se usan los grados Fahrenheit (°F).
¿Cómo se pasa de celsius a fahrenheit? Usando la siguiente formula:

```
GradosFahrenheit = GradosCelsius × 1.8 + 32
```

Y para el otro lado se puede obtener despejando GradosCelsius:

```
GradosCelsius = (GradosFahrenheit - 32) / 1.8
```

Entonces, vamos a implementar unas funciones que hagan esto por nosotros:

- **celsiusAFahrenheit**: toma una temperatura (que la vamos a representar como un número) en celsius, y la convierte a fahrenheit. 
- **fahrenheitACelsius**: está función hace el camino inverso a la anterior, le damos una temperatura en fahrenheit y la pasa a celsius.

Ahora, queremos una función a la cuál podamos preguntarle si hace frío o no. Nuestro criterio va a ser que hace frío sólo si la temperatura es menor o igual a **8 grados Celsius**. Entonces, definamos:

- **haceFrioCelsius**: recibe una temperatura (en Celsius) y debería ser verdadero si hace igual o menos de 8 grados Celsius.
- **haceFrioFahrenheit**: ésta recibe la temperatura como parámetro en Fahrenheit, pero el criterio para saber si hace frío es el mismo de antes.

**Para las funciones de este punto hay que completar y/o escribir los tests**.
**Para `haceFrioCelsius` y `haceFrioFahrenheit` también tienen que escribir el tipo ustedes**.
