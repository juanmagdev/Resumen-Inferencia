[[Inferencia]]
## Tabla de distribuciones
| Distribución                    | $D_X$             | Probabilidad/Densidad                                                  | E[X]                        | V[X]                                                  |
| ------------------------------- | ----------------- | ---------------------------------------------------------------------- | --------------------------- | ----------------------------------------------------- |
| $U(X_1, ..., X_n)$              | {$X_1, ..., X_n$} | $P(X = x) = \frac{1}{n}\cdot I_{[X_1, ..., X_n]}(x)$                   | $\frac{X_1 + ... + X_n}{n}$ | $\frac{(X_1 - \bar X)^2 + ... + (X_n - \bar X)^2}{n}$ |
| $Ber(p)$                        | {0, 1}            | $P(X = x) = p^x(1-p)^{1-x}$                                            | $p$                         | $p(1-p)$                                              |
| $Bi(n, p)$                      | {0, 1, ..., n}    | $P(X = k) = \binom{n}{k}p^k(1-p)^{n-k}$                                | $np$                        | $np(1-p)$                                             |
| $Ge(p)$                         | {1, 2, ...}       | $P(X = k) = p(1-p)^{k-1}$                                              | $\frac{1}{p}$               | $\frac{1-p}{p^2}$                                     |
| $Po(\lambda)$                   | {0, 1, 2, ...}    | $P(X = k) = \frac{e^{-\lambda}\lambda^k}{k!}$                          | $\lambda$                   | $\lambda$                                             |
| $U(a, b)$                       | {a, ..., b}       | $f(x) = \frac{1}{b-a}\cdot I_{[a,b]}(x)$                               | $\frac{a+b}{2}$             | $\frac{(b-a)^2}{12}$                                  |
| $Exp(\lambda)$                  | {0, ...}          | $f(x) = \lambda e^{-\lambda x}$                                        | $\frac{1}{\lambda}$         | $\frac{1}{\lambda^2}$                                 |
| $N(\mu, \sigma)$                | {-∞, ..., +∞}     | $f(x) = \frac{1}{\sqrt{2\pi\sigma^2}}e^{-\frac{(x-\mu)^2}{2\sigma^2}}$ | $\mu$                       | $\sigma^2$                                            |
| $Ga(\alpha, \beta)$             | {0, ...}          | $f(x) = \frac{\beta^\alpha x^{\alpha-1}e^{-\beta x}}{\Gamma(\alpha)}$  | $\frac{\alpha}{\beta}$      | $\frac{\alpha}{\beta^2}$                              |
| $X_{(n)}^2 \equiv Ga(n/2, 1/2)$ | {0, ..., +∞}      | $f(x) = \frac{1}{\Gamma(n/2)2^{n/2}}x^{n/2-1}e^{-x/2}$                 | $n$                         | $2n$                                                  |
| $BN(r, p)$                        | {0, 1, ...}       | $P(X = x)\binom{n+r-1}{n}(1-p)^np^r$                                   | $\frac{r(1-p)}{p}$          | $\frac{r(1-p)}{p^2}$                                                      |

### Observaciones
$$\Gamma = \int_0^{+\infty}x^{p-1}e^{-x}dx$$
$$F_{X_{(n)}}(y) = P(max{(X_i)} \leq y) = P(X_1 \leq y, ..., X_n \leq y) = \prod_{i=1}^nP(X \leq y) = P(X\leq y)^n = (F_X(y))^n$$
$$f_T(t) = n[F_{X_{(n)}}]^{n-1}f_X(t)$$
$$F_{X_{(1)}}(y) = P(min{(X_i)} \leq y) = 1 - P(X_1 > y, ..., X_n > y) = 1-\prod_{i=1}^nP(X > y) = 1 -\prod_{i=1}^n (1 - P(X_i\leq x)) = 1 - (1-F_X(y))^n$$


#### Desigualdad de Chebyshev
Sea $X$ variable aleatoria de media $\mu$ y varianza $\sigma^2$, entonces:
$$P(|X - \mu| > a\sigma) \leq \frac{1}{a^2}$$
$$P(|X - \mu| \leq a\sigma) \geq 1 -\frac{1}{a^2}$$
$$P(|X - E[x]| \geq a) \leq \frac{Var(X)}{a^2}$$
#### Teorema Central del límite
Sean $(X_1, ..., X_n)$ variables aleatorias independientes, con media y varianzas finitas. Entonces, cuando $n$ tiende a infinito:
$$Z_n = \frac{\sum X_i - n\mu}{\sigma \sqrt{n}} \sim N(0,1)$$
$$Z_n = \frac{\bar X - \mu}{\sigma /\sqrt{n}} \sim N(0,1)$$
###### Teorema cambio de variable:
Sea $f_X$ la función de densidad de una variable aleatoria, $g$ una función medible, tal que $Y = g(X)$, entonces la función de densidad de $Y$ es: $$f_Y(y) = f_X(g^{-1}(y))|g^{-1}(y)'|$$

##### Otras
 - Si $X \sim Bi(n, p)$ entonces $X \sim N(np, \sqrt{npq})$
 - Si $X_i \sim N(\mu, \sigma)$ entonces, $\bar X \sim N(\mu, \sigma/\sqrt{n})$
 - Si $X_i \sim N(\mu, \sigma)$ entonces $\frac{1}{n}X_i \sim N(\mu/n, \sigma /\sqrt n)$ 
 - Si $X \sim N(\mu, \sigma)$, entonces $aX + b \sim N( a\mu + b, \sqrt a\sigma)$
 -  Si $X \sim N(\mu, \sigma^2)$, entonces $aX + b \sim N( a\mu + b, a^2\sigma)$
 -  - Si $X \sim N(\mu, \sigma)$, entonces $\frac{X-\mu}{\sigma} \sim N(0, 1)$
 - Si $X \sim N(\mu_1, \sigma_1)$ y $Y \sim N(\mu_2, \sigma_2)$, entonces:
	 - $X + Y \sim N(\mu_1 + \mu_2, \sqrt{\sigma_1^2 + \sigma_2^2})$
	 - $X - Y \sim N(\mu_1 - \mu_2, \sqrt{\sigma_1^2 + \sigma_2^2})$

 - Si $X \sim N(\mu_1, \sigma_1^2)$ y $Y \sim N(\mu_2, \sigma_2^2)$, entonces:
	 - $X + Y \sim N(\mu_1 + \mu_2, \sigma_1^2 + \sigma_2^2)$
	 - $X - Y \sim N(\mu_1 - \mu_2, \sigma_1^2 + \sigma_2^2)$

 - $E(X_1 - X_2) = E(X_1) - E(X_2)$, si son variables aleatorias
 - $E(X_1X_2) = E(X_1)E(X_2)$, si son variables aleatorias
 - $V(X_1 - X_2) = V(X_1) + V(X_2)$, si son variables aleatorias
 - Si $X \sim Exp(\lambda)$, entonces para todo $a > 0, x>0$, entonces  $P(X > a + x|  X \geq a) = P(X> x)$
 - Si $X \sim Ga(a, p)$, entonces $Y = cX \sim Ga(\frac{a}{c}, p)$

 - Si $X_i \sim Po(\lambda)$ entonces, $\sum_{i=1}^{n}X_i \sim Po(n\lambda)$
 - Si $X_i \sim BN(r, p)$ entonces, $\sum_{i=1}^{n}X_i \sim Ge(p)$
 - Si $X_i \sim Ber(p)$, entonces $\sum_{i=1}^{n}X_i \sim Bi(n, p)$
 - Si $X_i \sim Exp(\theta)$, entonces $\sum_{i=1}^{n}X_i \sim Ga(a=\theta, p=n)$, entonces $\frac{1}{n}\sum_{i=1}^{n}X_i \sim Ga(a=n\theta, p=n)$

 - Si $X \sim N(\mu, \sigma)$, entonces $E(\bar X) = \mu$ y  $E(S^2) = Var(X) = \sigma ^2$
 - $E(S^2) = Var(X)$ independientemente de la distribución

 - $Var(X) = E(X^2) + (E(X))^2$
 - $Var(aX) = a^2Var(X)$ y $E(aX) = aE(X)$
 - $\sum_{i=1}^n E(X) = E(\sum_{i=1}^n X)$, y $\sum_{i=1}^n Var(X) = Var(\sum_{i=1}^n X)$

 - El intervalo de confianza de una normal es [-4, 4], es decir, $\phi(-10) = 0$  $\phi(10) = 1$

 - **Xi-cuadrado**:
	 - Génesis: Dadas $X_i$ variables aleatorias con distribución $N(0, 1)$. Si consideramos $Y = \sum_{i=1}^n X_i^2$,  podemos decir que $Y \sim X_{(n)}^2$
	 - TCL:
		 $\frac{Y - n}{\sqrt{2n}} \sim N(0,1)$
		  $\sqrt{2Y} - \sqrt{2n -1} \sim N(0,1)$
	 - Reproductividad: 
			Si $T \sim X_{(n)}^2$ y $W \sim X_{(m)}^2$, entonces, $T+W \sim X_{(n +m)}^2$
 - **Teorema de Fisher**: Si $X_i, ..., X_n$ es m.a.s de distribución $N(0,1 )$. Entonces:
	 $(n-1)S^2 \sim X_{(n-1)}^2$
	 $\bar X \sim N(0, \frac{1}{\sqrt{n}})$
	 Generalización: Si $X_i, ..., X_n$ es m.a.s de distribución $N(\mu,\sigma )$. Entonces:
	 $\frac{(n-1)S^2}{\sigma^2} \sim X_{(n-1)}^2$
	 $\bar X \sim N(\mu, \frac{\sigma}{\sqrt{n}})$
- **t de Student**:
$$\frac{N(0,1)}{\sqrt{X_{(n)}^2/n}} \sim tn$$

$$\frac{\bar{X} - \mu}{\sqrt{S^2}/\sqrt{n}} \sim t_{n-1}$$

	- Si $t_n$ converge en $N(0,1)$ cuando $n$ tiende a infinito.
	- Si $n = 1$, la función de densidad de $t_1$ es $\frac{1}{\pi(1+x^2)}$
	- Si $n \leq 1$, no tiene momentos de primer orden, no tiene varianza
	- Si $n >1$, la media es finita y vale cero.
	- Si $n=2$, $var(X) = \frac{n}{n-2}$
- **F de Snedecor**:
Sean $X_1, ..., X_n$ y $Y_1, ..., Y_m$ variables aleatorias con distribución $N(0,1)$. Entonces:
$$\frac{\sum_{i=1}^nX_i/n}{\sum_{i=1}^mX_i/m} \sim F_{n, m}$$
Su media $\mu = \frac{m}{m-2}$, si $m >2$. Su varianza existe si $m >4$. 
Se tiene la siguiente relación del percentil $\alpha$:
$$F_{n, m;\alpha} = \frac{1}{F_{n, m;1 -\alpha}}$$
### Definiciones Importantes
##### Inferencia Paramétrica: 
Tipo de inferencia que admite que la distribución de probabilidad pertenece a una cierta familia paramétrica de distribuciones, siendo necesario únicamente precisar el valor de los parámetros para determinar la distribución poblacional. Dos enfoques:
 - Enfoque clásico: Los parámetros se consideran constantes.
 - Enfoque bayesiano: Los parámetros se consideran variables aleatorias.

Sus elementos son: 
 - **Población**: Conjunto de elementos sobre los que se observa una característica común. Esta característica viene representada por una variable aleatoria $X$ de distribución $F_X$ desconocida o que no se conoce en su totalidad.
 - **Muestra**: Conjunto de unidades de la población. Cuanto mas significativa, mejor será para el estudio.
 - **Parámetros poblacionales**: Índices centrales y de dispersión que definen una población.

##### Muestra Aleatoria Simple:
Una muestra aleatoria simple de tamaño n de una variable aleatoria $X$ con distribución $F_X$, es un conjunto sobre $n$ variables aleatorias independientes $(X_1, ..., X_n)$ e igualmente distribuidas.

##### Estadístico
Un estadístico es una función matemática que se aplica a una muestra de datos para resumir o describir alguna característica de interés de la población subyacente a la muestra.
Es una función $$ T: (X_1, ..., X_n) \rightarrow \mathbb{R}^k$$
$T$ es una nueva variable aleatoria que tendrá una distribución asocidad (distribución empírica)

##### Estimador
Un estimador es una regla o fórmula que se utiliza para estimar un parámetro desconocido de la población subyacente, basandose en la información de la muestra. 

Todo estimador es un estadístico. Un estadístico puede ser estimador, ej: Media muestral como estimador de la media poblacional.

### Estimadores útiles:

Media: $T(X_1, ..., X_n) = \bar X = \frac{\sum_{i=1}^nX_i}{n}$

Varianza muestral: $T(X_1, ..., X_n) = Var_n(X) = \frac{\sum_{i=1}^n(X_i - \bar X)^2}{n}$

Cuasivarianza muestral: $T(X_1, ..., X_n) =S^2(X) = \frac{\sum_{i=1}^n(X_i - \bar X)^2}{n-1}$

Máximo: $T(X_1, ..., X_n) = X_{(n)} = \max(X_1, ..., X_n)$

Mínimo: $T(X_1, ..., X_n) = X_{(0)} = \min(X_1, ..., X_n)$

## Estimación Puntual Paramétrica
### Estadísticos y Estimadores. Métodos para construirlos.
##### Método de los momentos: 
Igualar momento poblacional y momento muestral. Si algún momento es constante, hay que ir al siguiente. Necesitamos tantos momentos como parámetros.
$m_r = \frac{\sum_{i=1}^{n}X_i^r}{n}$
$\alpha_r = E[X^r]$
**Fórmulas útiles**:   $E(X^2) = Var(X) + (E(X))^2$
							$E(X) = \int{xf_Xdx}$, en el caso continua
							$E(X) = \sum_{i=1}^n X_i P(X_i = x_i)$, en el caso discreto 
							$Var(X) = V(X) = E[(X - E(X)^2]$

##### Método de la máxima verosimilitud
Consiste en hacer máximo el parámetro $\theta$ de la función de verosimilitud L. Para ello es útil trabajar en logaritmo y hacer la derivada para calcular el máximo. 

La función de verosimilitud es una función matemática que describe la probabilidad de que los datos observados se generen a partir de un modelo estadístico con un conjunto de parámetros desconocidos. 

El estimador de máxima verosimilitud (EMV) es un método para encontrar el valor más probable de los parámetros desconocidos del modelo estadístico utilizando la función de verosimilitud.

**Relaciones útiles**:
	$I_{(0, \theta)}(x) = I_{(max({x_i}), +\infty)}(\theta)$
	$I_{(\theta, +\infty)}(x) = I_{(-\infty, min({x_i}))}(\theta)$

#### Teorema de Invarianza de EMV (Zenha)
Sea $X \sim f(x, \theta)$ y sea $\hat\theta$ el EMV para $\theta$. Sea $y$ una función biyectiva, entonces el estimador para $y(\theta)$ es $y(\hat \theta)$

### Propiedades de los estimadores
 - Comparación de estimadores
Sean $T_1$ y $T_2$ dos estimadores de $g(\theta)$. Diremos que $T_1$ es mas concentrado que $T_2$ si y solo si 
$$P(|T_1 - g(\theta)| < 1) \geq P(|T_2 - g(\theta)| < \lambda), \forall \lambda>0$$

 ###### Error Cuadrático Medio
 - $ECM_T(\theta) = E_\theta((T-g(\theta))^2)$
 - $ECM_T(\theta) = Var_{\theta}(T) + (E_\theta(T) - g(\theta))^2$
 - ¿Mas propiedades?

##### Definiciones y resultados
 - **Insegado:** $T$ estimador de $g(\theta)$ es insesgado si y solo si $E_\theta(T) = g(\theta)$. Si es insesgado, el sesgo es $0$, es decir, $E_\theta(T) - g(\theta)=0$
 - **Consistente debil:** Una sucesión ${T_n}$ de estimadores es consistente para $g(\theta)$ si $P_\theta(|T_n - g(\theta)| > \epsilon) \rightarrow 0$ cuando $n \rightarrow \infty$
	 Es útil probar la consistencia con $ECM_T$, si $ECM_T \rightarrow 0$ cuando $n$ tiende a infinito, entonces es consistente en media cuadrática, entonces es consistente.
 - **Suficiente:** $T$ es suficiente si y solo si la distribución de $(X_1, ..., X_n)$ dado que $T(X_1, ..., X_n) = t$ no depende de $\theta$
 - **Suficiente**:  T es suficiente si y solo si la distribución de un estadístico $S$ dado que $T(X_1, ..., X_n) = t$ no depende de $\theta$
 - **Insesgado de Mínima Varianza(EIUMV):** $T^*$ es EIUMV de $\theta$ si:
		1. $E_\theta(T^*) = g(\theta)$
		2. $Var_\theta(T^*) \leq Var_\theta(T)$, para todo $T$ estimador insesgado.
 - **Completo:** $T$ es completo si y solo si $E_\theta(g(T)) = 0$ entonces $P_\theta(g(T) = 0) = 1$ para casi todo punto.
	 $E_\theta(G(T)) = \int_a^bg(t)f_\theta(t)dt$
 - **Minimal:** $T$ suficiente diremos que es minimal si dado un estadístico suficiente $T'$ y una función $\phi$ medible, $T = \phi(T')$
 - **Eficiente**: $T$ es eficiente si verifica la cota de Cramer-Rao

##### Teorema de Factorización (Neymar-Fisher)
Sea $X \sim F_\theta$, y sea $(X_1, ..., X_n)$ muestra aleatoria simple. Diremos que $T = T(X_1, ..., X_n)$ es un estadístico **suficiente** para $\theta$ si y solo si
$$f(X_1, ...,X_m;\theta) = g(T(X_1, ...,X_m))h(X_1, ...,X_m)$$
con $h$ y $g$ medibles y no negativas.

##### Propiedades Estadísticos Suficientes
1. Si $T$ es suficiente para $F_\theta$, con $\theta \in H$ entonces es suficiente para $F_\theta$, con $\theta \in H' \subset H$
2. Si $T$ es suficiente para $F_\theta$ y $T = m(u)$ con $m$ medible y $u$ estadístico para $\theta$, entonces $u$ es suficiente para $\theta$
3. Si $T$ es suficiente y $m$ función biyectiva, entonces $m(u)$ es suficiente

##### Familia Exponencial Uniparamétrica
Diremos que $f(x;\theta)$ pertenece a la familia exponencial uniparamétrica si
$$f(x;\theta) = a(\theta)b(x)exp(c(\theta)d(x))$$
Entonces, 
$$f(X_1, ..., X_n; \theta) = \prod f(X_i) = a^n(\theta)\prod b(X_i)exp(c(\theta), \sum d(X_i))$$
Siendo $T = \sum d(X_i)$ estadístico suficiente para $\theta$

##### Teorema de Cramer-Rao
Sea $(X_1, ..., X_n)$ muestra aleatoria simple de $f(x; \theta)$. Sea $T^*$ estimador insesgado de $g(\theta)$. Si se verifican las condiciones de regularidad:
1. $\{(X_1, ..., X_n) \in \mathcal{X}: f_\theta(X_1, ..., X_n) > 0 \}$ no depende de $\theta$
2. $\frac{d}{d\theta}log f(x;\theta)$ existe
3. $\frac{d}{d\theta}\int ... \int \prod f(x_i; \theta) dx_1 ... dx_n=\int ... \int \prod f(x_i; \theta) dx_1 ... dx_n$
4. $\frac{d}{d\theta}\int ... \int T^*(X_1, ..., X_n)\prod f(x_i; \theta) dx_1 ... dx_n=\int ... \int T^*(X_1, ..., X_n)\prod f(x_i; \theta) dx_1 ... dx_n$
5. $0 < E_\theta((\frac{d}{d\theta}logf(X;\theta))^2)$
Entonces, $$Var_\theta(T^*) \geq \frac{(g'(\theta))^2}{nE_\theta((\frac{d}{d\theta}logf(X;\theta))^2)}$$
##### Teorema de Rao-Blackwell
Sea $(X_1, ..., X_n)$ muestra aleatoria simple de $f(x; \theta)$. Sean $(S_1, ..., S_n)$ un conjunto de estadísticos conjuntamente suficientes para $\theta$. Sea $T$ un estimador insesgado para $g(\theta)$. Entonces el estimador $T^* = E_\theta(T|S_1, ..., S_k)$ verifica:
 - $T^*$ es función de un conjunto de estadísticos suficientes.
 - $T^*$ es insesgado para $g(\theta)$
 - $Var_\theta(T^*) \leq Var_\theta(T)$

##### Teorema de Lehman-Scheffé
Sea $(X_1, ..., X_n)$ m.a.s de una variable aleatoria $X$ con función de distribución $f(x;\theta)$. 
1. Sea $S$ un estadístico suficiente y completo para $h(\theta)$. Si $T^*(S)$ es insesgado para $h(\theta)$ entonces  $T^*(S)$ es el EIUMV para $h(\theta)$
2. Si $T_2$ es un estadístico suficiente y completo para $h(\theta)$ y $T_1$ es estadistico insesgado para $h(\theta)$ entonces $E_\theta(T_1, T_2)$ es el EIUMV para $h(\theta)$