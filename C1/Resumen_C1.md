# Apunte Señales y Sistemas I
Por: Tomás Rojas
## Señales, sistemas y procesamiento de señales

> Definición: Una __señal__ es cualquier cantidad física que varia en el tiempo, en el espacio o cualquier otra variable.

Algunos ejemplos de señales pueden ser polinomios que dependan del tiempo o del espacio o cualquier cosa.

Hay señales que pueden ser especificadas de manera funcional (con funciones), pero este no es siempre el caso.

Si tomamos un audio de una charla, no es una señal definida funcionalmente, pero podemos descomponerla en suma de senos y cosenos:

$$\sum_{i=1}^NA_i(t)\sin[2\pi F_i(t)t+\theta_i(t)]$$

Donde $\{A_i\},\{F_i\},\{\theta_i\}$ son conjuntos de Amplitudes, Frecuencias y Fases respectivamente, que bien podrían variar en el tiempo.

Otro ejemplo de señal puede ser un electrocardiograma. Esta señal le entrega información a un médico sobre la condición en que se encuentra el corazón de su paciente. De manera similar, un electroencefalograma da información de la actividad cerebral.

Todos los sistemas mencionados son ejemplos de sistemas que dependen se solo una variable independiente, el tiempo... Un ejemplo de un sistema con más variables independientes puede ser una imagen.


Un sistema también puede ser definido como un aparato físico que ejecuta cierta operación sobre una señal. Por ejemplo un filtro puede ser tratado como un sistema.


Cuando pasamos una señal por un sistema, decimos que la procesamos. En general, un sistema está caracterizado por el tipo de operación que aplica a una señal.

## Clasificación de señales
> lo voy a dejar en blanco ya que no es tan importante para el C1, más adelante volveré a llenar esto


## Señales en tiempo continuo versus señales en tiempo discreto

### Señales sinusoidales continuas

Un oscilador armónico simple puede ser descrito matemáticamente como:

$$x_a(t)=A\cos(\Omega t + \theta); \quad -\infty<t<\infty$$


El subíndice $a$ hace referencia a que esta señal es analógica.

La frecuencia $\Omega$ es frecuencia angular, en radianes, es común usar $F$ que es en Hertz, donde $\Omega=2\pi F$

La señal sinusoidal analógica está caracterizada por las siguientes propiedades:

  + _Para cualquier valor fijo de frecuencia $F$, $x_a(t)$ es periódica._ Esto es
  $$x_a(t+T_p)=x_a(t), \quad T=1/F$$
  + _Señales análogas sinusoidales con distintas frecuencias, __son__ distintas_.
  + _Incrementar la frecuencia implica incrementar las oscilaciones de una señal en un tiempo dado._


Podemos notar que para $F\to 0$ entonces $F \to \infty$

### Señales sinusoidales discretas

Podemos expresar matemáticamente una señal sinusoidal discreta de la siguiente manera:

$$x(n)=A\cos(\omega n + \theta); \quad -\infty<n<\infty$$

Acá también tenemos otra frecuencia:

$$\omega \equiv 2\pi f$$

Podemos ver las siguientes propiedades de este tipo de señales:

  + _Una señal sinusoidal discreta es periódica __solo__ si su frecuencia $f$ es un nro racional_.

Por definición tenemos que una señal discreta es periódica con periodo $N \quad (N>0)$  ssi:
$$x(n+N)=x(n)\quad \forall n$$

El valor más pequeño de $N$ para el que esto se cumple, se llama _periodo fundamental_.

> __Demostración:__
> $$\cos[2\pi f_0(N+n)+\theta]=\cos(2\pi f_0n+\theta)$$
> $$2\pi f_0 N =2k\pi$$
> $$f_0=\frac{k}{N}$$

Por lo que es periódica sólo si su frecuencia $f_0$ es una fracción entre dos enteros i.e. es racional.




  + _Sinusoides discretas cuyas frecuencias están separadas por un múltiplo entero de $2\pi$ son __indénticas__._

Para probar esto, consideremos $\cos(\omega_0n+\theta)$
$$\cos[(\omega_0 +2\pi)n+\theta]=\cos (\omega_0 n + 2\pi +\theta)= \cos(\omega_0n+\theta)$$

Como consecuencia de esto, __todas__ las secuencias sinusoidales que cumplan:

$$x_k(n)=A\cos(\omega_k n+\theta); \quad k=0,1,2,3,...$$

Donde:

$$\omega k =\omega_0+2k\pi, \quad -\pi \leq \omega_0 \leq \pi$$

Son __indistinguibles__, por lo mismo, nos interesan frecuencias en los rangos $-\pi \leq \omega \leq\pi$ o bien $-1/2\leq f\leq1/2$

  + _La oscilación más rápida que puede tener una señal sinusoidal discreta es cuando $\omega=\pm\pi$ o bien $f=\pm 1/2$

En la siguiente imagen podemos ver la señal $x(n)=\cos\omega_0n$ con distintos valores para $\omega_0$

![](./img/img1.png)
__Figura 1:__ Imagen sacada de _Digital Signal Processing_


## Analógico a digital y digital a analógico
