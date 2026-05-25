---
marp: true
theme: gaia
paginate: true
_class: lead
math: katex
---

# EDOs de Primeira Ordem

**Curso:** Introdução a EDO — Capítulo 2
**Professor:** Saulo Henrique

---

## Objetivos da Aula

- Reconhecer e resolver EDOs separáveis pelo método de **separação de variáveis**
- Resolver EDOs **lineares de 1ª ordem** com o **fator integrante**
- Resolver EDOs **homogêneas** via substituição $v = y/x$
- Resolver equações de **Bernoulli** por linearização
- Aplicar cada método em **modelos matemáticos** reais

---

## Estrutura do Capítulo 2

| Método | Tipo de EDO |
|---|---|
| Separação de variáveis | $y' = g(x)\,h(y)$ |
| Fator integrante | $y' + p(x)\,y = q(x)$ |
| Substituição $v = y/x$ | EDO homogênea: $y' = F(y/x)$ |
| Linearização de Bernoulli | $y' + p(x)\,y = q(x)\,y^n$ |

> Cada método é uma **estratégia de reconhecimento e transformação**: identificamos a forma da EDO e aplicamos a técnica adequada.

---

## Método 1 — Separação de Variáveis

### Quando usar?

A EDO deve poder ser escrita na forma:
$$
\frac{dy}{dx} = g(x)\cdot h(y)
$$
isto é, o lado direito é um **produto** de uma função apenas de $x$ por uma função apenas de $y$.

---

### Como funciona?

Dividindo ambos os lados por $h(y)$ (supondo $h(y) \neq 0$):
$$
\frac{1}{h(y)}\,dy = g(x)\,dx
$$

Integrando dos dois lados:
$$
\int \frac{1}{h(y)}\,dy = \int g(x)\,dx + C
$$

Por fim, isolamos $y$ (quando possível) para obter a **solução explícita** ou deixamos na forma implícita.

---

### Exemplo 1 — Com PVI

$$
\frac{dy}{dx} = xy^2, \quad y(0) = 1
$$

**Passo 1 — Separar:**
$$
\frac{1}{y^2}\,dy = x\,dx
$$

**Passo 2 — Integrar:**
$$
\int y^{-2}\,dy = \int x\,dx
\;\Longrightarrow\;
-\frac{1}{y} = \frac{x^2}{2} + C
$$

---

**Passo 3 — Solução geral:**
$$
y = -\frac{2}{x^2 + C}
$$

**Passo 4 — Aplicar condição inicial** $y(0) = 1$:
$$
1 = -\frac{2}{0 + C} \;\Longrightarrow\; C = -2
$$

**Solução particular:**
$$
\boxed{y = -\frac{2}{x^2 - 2}}
$$

**Região de validade:** $x^2 - 2 \neq 0 \;\Longrightarrow\; x \neq \pm\sqrt{2}$

---

### Aplicação — Decaimento Radioativo

$$
\frac{dN}{dt} = -\lambda N, \quad N(0) = N_0, \quad \lambda > 0
$$

**Separando:**
$$
\frac{dN}{N} = -\lambda\,dt
\;\Longrightarrow\;
\ln|N| = -\lambda t + C
$$

**Solução geral:**
$$
N(t) = N_0\,e^{-\lambda t}
$$

---

> $\lambda$ é a **constante de decaimento**: quanto maior, mais rápido o material decai. O sinal negativo garante que $N$ decresce com o tempo.

---

### Exemplo 2 — Solução Implícita

$$
\frac{dy}{dx} = \frac{3x^2}{2y}
$$

**Separando e integrando:**
$$
2y\,dy = 3x^2\,dx
\;\Longrightarrow\;
y^2 = x^3 + C
$$

Não há necessidade de isolar $y$ — a relação $y^2 = x^3 + C$ é uma **solução implícita** válida.

---

## Método 2 — Fator Integrante

### Quando usar?

A EDO é **linear de 1ª ordem** na forma:
$$
\frac{dy}{dx} + p(x)\,y = q(x)
$$

onde $p(x)$ e $q(x)$ são funções contínuas de $x$.

> Importante: a EDO deve estar com coeficiente 1 na frente de $y'$ antes de identificar $p(x)$.

---

### Como funciona?

Definimos o **fator integrante**:
$$
\mu(x) = e^{\int p(x)\,dx}
$$

Multiplicamos ambos os lados da EDO por $\mu(x)$:
$$
\mu(x)\,y' + \mu(x)\,p(x)\,y = \mu(x)\,q(x)
$$

O lado esquerdo é exatamente a derivada do produto $\mu(x)\,y$:
$$
\frac{d}{dx}\!\bigl[\mu(x)\,y\bigr] = \mu(x)\,q(x)
$$

---

Integrando ambos os lados:
$$
\mu(x)\,y = \int \mu(x)\,q(x)\,dx + C
$$

**Solução geral:**
$$
\boxed{y = \frac{1}{\mu(x)}\left[\int \mu(x)\,q(x)\,dx + C\right]}
$$

---

### Por que funciona? (Intuição)

O fator integrante $\mu(x) = e^{\int p(x)\,dx}$ é construído exatamente para que:
$$
\mu'(x) = \mu(x)\,p(x)
$$

Com isso, pela **regra do produto**:
$$
(\mu y)' = \mu'y + \mu y' = \mu p y + \mu y' = \mu\,(y' + py)
$$

ou seja, o lado esquerdo da EDO multiplicada por $\mu$ colapsa em uma derivada simples.

---

### Exemplo 3 — Fator Integrante

$$
\frac{dy}{dx} - \frac{2}{x}\,y = x^2, \quad x > 0
$$

**Identificar:** $p(x) = -\dfrac{2}{x}$, $\quad q(x) = x^2$

**Calcular $\mu(x)$:**
$$
\mu(x) = e^{\int -\frac{2}{x}\,dx} = e^{-2\ln x} = x^{-2}
$$

---

**Multiplicar por $\mu = x^{-2}$:**
$$
x^{-2}y' - 2x^{-3}y = 1
\;\Longrightarrow\;
\frac{d}{dx}\!\left[\frac{y}{x^2}\right] = 1
$$

**Integrar:**
$$
\frac{y}{x^2} = x + C
$$

**Solução geral:**
$$
\boxed{y = x^3 + Cx^2}
$$

---

### Aplicação — Resfriamento de Newton

$$
\frac{dT}{dt} + k\,T = k\,T_{\text{amb}}, \quad T(0) = T_0
$$

**Identificar:** $p(t) = k$, $\quad q(t) = k\,T_{\text{amb}}$

**Fator integrante:** $\mu(t) = e^{kt}$

**Integrando:**
$$
e^{kt}\,T = T_{\text{amb}}\,e^{kt} + C
\;\Longrightarrow\;
T(t) = T_{\text{amb}} + (T_0 - T_{\text{amb}})\,e^{-kt}
$$

---

> Conforme $t \to \infty$, $T(t) \to T_{\text{amb}}$ — o objeto atinge a temperatura ambiente.

---

## Método 3 — EDOs Homogêneas

### Quando usar?

A EDO pode ser escrita na forma:
$$
\frac{dy}{dx} = F\!\left(\frac{y}{x}\right)
$$

Dizemos que a EDO é **homogênea** (no sentido de grau homogêneo) quando $f(x,y)$ satisfaz $f(tx, ty) = f(x,y)$ para todo $t \neq 0$.

> **Atenção:** "homogênea" aqui tem significado **diferente** do usado em EDOs lineares!

---

### Como identificar?

Tente escrever $y' = f(x,y)$ expressando $f$ apenas em termos de $v = y/x$.

**Exemplos:**

- $\dfrac{dy}{dx} = \dfrac{x^2 + y^2}{xy}$: dividindo por $x^2$: $= \dfrac{1 + (y/x)^2}{(y/x)} = F(v)$ ✓

- $\dfrac{dy}{dx} = \dfrac{y - x}{y + x}$: dividindo por $x$: $= \dfrac{(y/x) - 1}{(y/x) + 1} = F(v)$ ✓

---

### Como funciona?

**Substituição:** $v = \dfrac{y}{x} \;\Longrightarrow\; y = vx$

Derivando $y = vx$ em relação a $x$:
$$
\frac{dy}{dx} = v + x\,\frac{dv}{dx}
$$

---

Substituindo na EDO:
$$
v + x\,\frac{dv}{dx} = F(v)
\;\Longrightarrow\;
x\,\frac{dv}{dx} = F(v) - v
$$

Esta nova EDO em $v(x)$ é **separável**!

$$
\frac{dv}{F(v) - v} = \frac{dx}{x}
$$

Integramos dos dois lados e, ao final, substituímos $v = y/x$ de volta.

---

### Exemplo 4 — EDO Homogênea

$$
\frac{dy}{dx} = \frac{y^2 - x^2}{2xy}
$$

**Verificar homogeneidade:** divida por $x^2$:
$$
\frac{dy}{dx} = \frac{(y/x)^2 - 1}{2(y/x)} = F(v), \quad v = \frac{y}{x} \;\checkmark
$$

---

**Substituição** $y = vx$, $\;y' = v + xv'$:
$$
v + x\frac{dv}{dx} = \frac{v^2 - 1}{2v}
$$

**Separando:**
$$
x\frac{dv}{dx} = \frac{v^2 - 1}{2v} - v = \frac{v^2 - 1 - 2v^2}{2v} = \frac{-v^2 - 1}{2v}
$$

$$
\frac{2v}{v^2 + 1}\,dv = -\frac{dx}{x}
$$

---

**Integrando:**
$$
\ln(v^2 + 1) = -\ln|x| + C
\;\Longrightarrow\;
v^2 + 1 = \frac{K}{|x|}
$$

**Retornando a** $v = y/x$:

$$
\frac{y^2}{x^2} + 1 = \frac{K}{|x|}
\;\Longrightarrow\;
y^2 + x^2 = K|x|
$$

**Solução implícita:**
$$
\boxed{x^2 + y^2 = Kx}
$$

---

### Aplicação — Modelo de Difusão Relativa

Em certos modelos de mistura, a concentração relativa $c = y/x$ satisfaz uma EDO da forma $c' = F(c)$ — exatamente a estrutura que a substituição $v = y/x$ revela.

> A substituição $v = y/x$ transforma o problema de uma EDO **não separável** em uma **separável** — esse é o poder da técnica.

---

## Método 4 — Equação de Bernoulli

### Quando usar?

A EDO tem a forma:
$$
\frac{dy}{dx} + p(x)\,y = q(x)\,y^n, \quad n \neq 0,\, 1
$$

Para $n = 0$ ou $n = 1$, a equação já seria linear. Quando $n \neq 0, 1$, ela é **não linear** — mas pode ser **linearizada**.

---

### Como funciona?

**Substituição:** $\;w = y^{1-n}$

Derivando:
$$
\frac{dw}{dx} = (1-n)\,y^{-n}\,\frac{dy}{dx}
$$

Dividindo a equação original por $y^n$:
$$
y^{-n}\frac{dy}{dx} + p(x)\,y^{1-n} = q(x)
$$

---

Substituindo $w = y^{1-n}$ e $w' = (1-n)y^{-n}y'$:

$$
\frac{1}{1-n}\frac{dw}{dx} + p(x)\,w = q(x)
$$

**EDO linear resultante:**
$$
\frac{dw}{dx} + (1-n)\,p(x)\,w = (1-n)\,q(x)
$$

Resolvemos pelo **fator integrante** e depois voltamos a $y = w^{1/(1-n)}$.

---

### Exemplo 5 — Equação de Bernoulli

$$
\frac{dy}{dx} - y = xy^3
$$

**Identificar:** $p(x) = -1$, $q(x) = x$, $n = 3$

**Substituição:** $w = y^{1-3} = y^{-2}$, $\quad w' = -2y^{-3}y'$

Dividindo por $y^3$:
$$
y^{-3}y' - y^{-2} = x
\;\Longrightarrow\;
-\frac{1}{2}w' - w = x
$$

---

**EDO linear em** $w$:
$$
\frac{dw}{dx} + 2w = -2x
$$

**Fator integrante:** $\mu = e^{2x}$

$$
\frac{d}{dx}\!\left[e^{2x}w\right] = -2x\,e^{2x}
$$

**Integrando por partes:**
$$
e^{2x}w = -2\left(\frac{x\,e^{2x}}{2} - \frac{e^{2x}}{4}\right) + C = -xe^{2x} + \frac{e^{2x}}{2} + C
$$

---

**Solução em** $w$:
$$
w = -x + \frac{1}{2} + Ce^{-2x}
$$

**Retornando a** $y$ com $w = y^{-2}$:
$$
\boxed{y^{-2} = \frac{1}{2} - x + Ce^{-2x}}
$$

---

### Aplicação — Modelo Logístico

A equação logística
$$
\frac{dP}{dt} = rP - \frac{r}{K}P^2
$$
pode ser reescrita como:
$$
\frac{dP}{dt} - rP = -\frac{r}{K}P^2
$$

Isso é uma **Bernoulli com** $n = 2$, $p = -r$, $q = -r/K$.

---

Substituição $w = P^{-1}$ leva a uma EDO linear, cuja solução é:
$$
P(t) = \frac{K\,P_0}{P_0 + (K - P_0)\,e^{-rt}}
$$

---

## Resumo dos Métodos

| Forma da EDO | Método | Transformação |
|---|---|---|
| $y' = g(x)h(y)$ | Separação de variáveis | $\dfrac{dy}{h(y)} = g(x)\,dx$ |
| $y' + p(x)y = q(x)$ | Fator integrante | Multiplica por $\mu = e^{\int p\,dx}$ |
| $y' = F(y/x)$ | Substituição $v = y/x$ | Reduz a separável |
| $y' + py = qy^n$ | Bernoulli | $w = y^{1-n}$, reduz a linear |

---

## Exercícios Propostos

1. Resolva as EDOs e, quando indicada, resolva também o PVI:

   a) $\dfrac{dy}{dx} = \dfrac{x}{1+y^2}, \quad y(0) = 0$

   b) $\dfrac{dy}{dx} = (2x+1)(3y^2), \quad y(0) = 1$

   c) $\dfrac{dy}{dx} = \dfrac{x^2}{y^3}$ (solução geral)

   d) $\dfrac{dy}{dx} = e^{-x}\sin y$ (solução implícita)

---

2. Uma cultura bacteriana cresce de acordo com $\dfrac{dB}{dt} = kB$. Se $B(0) = 500$ e $B(2) = 2000$, determine:

   a) A constante $k$.

   b) $B(t)$ para todo $t \geq 0$.

   c) O tempo $t^*$ para que a população dobre pela primeira vez.

---

3. Resolva pelo método do fator integrante:

   a) $y' + 3y = e^{-x}$

   b) $y' - \dfrac{y}{x} = x^2, \quad x > 0$

   c) $xy' + 2y = x^3\ln x, \quad x > 0$ *(atenção: divida por $x$ antes)*

   d) $y' + y\cos x = \cos x$

---

4. A corrente $i(t)$ em um circuito com resistência $R$ e indutância $L$ sob tensão constante $V$ satisfaz:
$$
L\frac{di}{dt} + Ri = V, \quad i(0) = 0
$$

   a) Reescreva na forma padrão $i' + p(t)\,i = q(t)$.

   b) Determine o fator integrante $\mu(t)$.

   c) Resolva e interprete: o que ocorre com $i(t)$ quando $t \to \infty$?

---

5. Verifique que as EDOs são homogêneas e resolva-as:

   a) $\dfrac{dy}{dx} = \dfrac{y - x}{y + x}$

   b) $\dfrac{dy}{dx} = \dfrac{x^2 + y^2}{xy}$

   c) $\dfrac{dy}{dx} = \dfrac{2xy}{x^2 - y^2}$

   d) $\dfrac{y'}{xy} = 1$

---

6. Em certos problemas geométricos, a tangente e a reta à origem satisfazem uma EDO homogênea. Considere:
$$
\frac{dy}{dx} = \frac{y^2 + xy}{x^2}
$$

   a) Verifique que é homogênea.

   b) Resolva pela substituição $v = y/x$.

   c) Esboce (ou descreva) a família de curvas solução.

---

7. Resolva as equações de Bernoulli:

   a) $y' + y = y^2$

   b) $y' - \dfrac{y}{x} = \dfrac{y^3}{x^2}, \quad x > 0$

   c) $y' + \dfrac{y}{x} = x^2 y^{1/2}$ *(aqui $n = 1/2$)*

---

8. Considere $\dfrac{dP}{dt} = rP\!\left(1 - \dfrac{P}{K}\right)$.

   a) Reescreva como uma Bernoulli com $n = 2$.

   b) Faça a substituição $w = P^{-1}$ e obtenha a EDO linear em $w$.

   c) Resolva para $w(t)$ e retorne a $P(t)$.

   d) Verifique que $P(t) \to K$ quando $t \to \infty$ (capacidade de suporte).

---

9. Considere $\dfrac{dy}{dx} = \dfrac{x^2 + 1}{y^2 + y}$.

   a) Que tipo de EDO é essa?
   b) Resolva implicitamente.

10. Determine se as EDOs abaixo são separáveis, lineares, homogêneas ou de Bernoulli — e resolva usando o método apropriado:

    a) $y' = \dfrac{x + y}{x}$

    b) $(x^2 + 1)y' + 2xy = x$

    c) $y' - 2y = 4y^{-1}$

---

## Conexão com o Próximo Capítulo

Dominamos agora os **quatro principais métodos** de resolução de EDOs de 1ª ordem.

**Capítulo 3 — EDOs de Segunda Ordem:**
- Equações com coeficientes constantes: $ay'' + by' + cy = f(x)$
- Equações homogêneas e o polinômio característico
- Método dos coeficientes a determinar
- Variação de parâmetros

---

## Referências

- OLIVEIRA, Rafael Lima. *Equações diferenciais ordinárias: métodos de resolução e aplicações.* Curitiba: Intersaberes, 2019.
- UNIVERSIDADE ESTADUAL DE LONDRINA (UEL). *Equações diferenciais ordinárias.* Disponível em: <http://www.uel.br/projetos/matessencial/superior/pdfs/edo.pdf>.
- UNIVERSIDADE FEDERAL DA BAHIA. *Equações diferenciais ordinárias: Licenciatura Matemática UFBA.* Disponível em: <https://educapes.capes.gov.br/retrieve/166324/eBook_Equacoes_Diferenciais-Licenciatura_Matematica_UFBA.pdf>.

---

**Listas de Exercícios BONUS:**
1. https://docs.ufpr.br/~eidam/2012/2/CM121/CM121_Listas.pdf
2. https://sites.icmc.usp.br/frasson/ALED/listas/lista-edo-ordem1-naolin.pdf