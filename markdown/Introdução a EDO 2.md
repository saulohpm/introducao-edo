---
marp: true
theme: gaia
paginate: true
_class: lead
math: katex
---

<!-- Slide 1: Título -->
# EDOs Lineares de 1ª Ordem
# e Equações de Bernoulli

**Aula:** Introdução a EDO (Aula 2)
**Professor:** Saulo Henrique

---

<!-- Slide 2: Objetivos da Aula -->
## Objetivos
- Definir EDOs lineares de 1ª ordem
- Apresentar o método do fator integrante
- Definir e transformar Equações de Bernoulli
- Resolver exemplos passo a passo
- Propor exercícios para fixação

---

<!-- Slide 3: Revisão Rápida -->
## Revisão Rápida
- **EDO de 1ª ordem:** envolve $y$ e $\frac{dy}{dx}$
- **Linear e Não-linear:**
  - Linear: $a_1(x)\frac{dy}{dx} + a_0(x)y = b(x)$
  - Não-linear: termos como $y^n$ com $n\neq1$ e $n\neq0$

---

<!-- Slide 4: Definição – EDO Linear -->
## Definição - EDO Linear de 1ª Ordem

Sejam $I \subset \mathbb{R}$ um intervalo aberto e as funções $P, Q : I \to \mathbb{R}$ contínuas em $I$. Considera-se a equação diferencial ordinária (EDO):

$$
\frac{dy}{dx} + P(x) y = Q(x), \quad x \in I.
$$

Um **função solução** é uma função $y: I \to \mathbb{R}$ que seja diferenciável em $I$ e que satisfaça a equação para todo $x \in I$.

---

**Teorema (Existência e Unicidade):**  
Para cada ponto $x_0 \in I$ e valor inicial $y_0 \in \mathbb{R}$, existe uma única função solução $y \in C^1(I)$ da EDO que satisfaz a condição inicial  
$$
y(x_0) = y_0.
$$

**Observação:** A equação é chamada **linear** pois a função incógnita $y$ e sua derivada aparecem apenas com expoente 1 e sem produtos entre elas.

---

## Método do Fator Integrante

Considere a EDO linear de 1ª ordem:

$$
\frac{dy}{dx} + P(x) y = Q(x),
$$

onde $P, Q : I \to \mathbb{R}$ são funções contínuas em um intervalo aberto $I \subset \mathbb{R}$.

---

### Passo 1: Reconhecer a estrutura da derivada do produto

Multiplicamos toda a equação por uma função $\mu(x)$, que será determinada, tal que a expressão do lado esquerdo se torne a derivada do produto $\mu(x) y(x)$, isto é, buscamos $\mu$ tal que:

$$
\mu(x) \frac{dy}{dx} + \mu(x) P(x) y = \frac{d}{dx} \big[ \mu(x) y \big].
$$

Pela regra do produto, sabemos que:

---

$$
\frac{d}{dx} \big[ \mu(x) y \big] = \mu'(x) y + \mu(x) \frac{dy}{dx}.
$$

Comparando os dois lados da equação, obtemos:

$$
\mu(x) \frac{dy}{dx} + \mu(x) P(x) y = \mu'(x) y + \mu(x) \frac{dy}{dx}.
$$

Cancelando $\mu(x) \frac{dy}{dx}$ dos dois lados, resta:

$$
\mu(x) P(x) y = \mu'(x) y.
$$

---

Como essa igualdade deve valer para todo $y$, concluímos que:

$$
\mu'(x) = \mu(x) P(x).
$$

### Passo 2: Encontrar o fator integrante $\mu(x)$

Temos a equação diferencial para $\mu$:

$$
\frac{d\mu}{dx} = P(x) \mu(x).
$$

Esta é uma EDO separável. Separando variáveis e integrando:

---

$$
\int \frac{d\mu}{\mu} = \int P(x) dx,
$$

o que implica que:

$$
\ln |\mu(x)| = \int P(x) dx + C_0.
$$

Tomando $C_0 = 0$ (pois uma constante multiplicativa no fator integrante não altera a solução):

$$
\boxed{
\mu(x) = e^{\int P(x) dx}
}
$$

---

### Passo 3: Resolver a EDO com o fator integrante

Voltando à equação original multiplicada por $\mu$:

$$
\frac{d}{dx} \big[ \mu(x) y(x) \big] = \mu(x) Q(x).
$$

Integramos ambos os lados:

$$
\mu(x) y(x) = \int \mu(x) Q(x) dx + C.
$$

---

Finalmente, isolamos $y(x)$:

$$
\boxed{
y(x) = \frac{1}{\mu(x)} \left( \int \mu(x) Q(x) dx + C \right)
}
$$

---

<!-- Slide 6: Exemplo 1 – Linear -->
## Exemplo I
Dada a EDO abaixo, iremos resolver pelo método do fator integrante.
$$
\frac{dy}{dx} + 2y = e^x.
$$
Identificamos: $P(x)=2,\;Q(x)=e^x$  
Calculamos o fator integrante: $\mu=e^{\int 2\,dx}=e^{2x}$  
Multiplicamos a equação pelo fator integrante:
 $\frac{d}{dx}[e^{2x}y] = e^{2x}e^x = e^{3x}$  
Após aplicar a regra do produto temos que: $e^{2x}y = \tfrac{1}{3}e^{3x} + C$
Isolando $y$, temos: $y = \tfrac{1}{3}e^{x} + Ce^{-2x}$

---

<!-- Slide 7: Definição – Bernoulli -->
## Definição — Equação de Bernoulli

Sejam $I \subset \mathbb{R}$ intervalo aberto, $P, Q : I \to \mathbb{R}$ funções contínuas e $n \in \mathbb{R} \setminus{0,1}$.

Considere a EDO não linear  
$$
\frac{dy}{dx} + P(x) y = Q(x) y^n, \quad x \in I.
$$

Uma função solução $y: I \to \mathbb{R}$ é diferenciável e satisfaz a equação para todo $x \in I$.

---

**Transformação:** Definindo;
$$
v(x) := y(x)^{1-n}, \quad y(x) \neq 0,
$$  
então, pela regra da cadeia,  
$$
\frac{dv}{dx} = (1-n) y(x)^{-n} \frac{dy}{dx}.
$$

Substituindo na EDO original resulta em uma equação linear em $v$:  
$$
\frac{dv}{dx} + (1-n) P(x) v = (1-n) Q(x).
$$

---

**Teorema:** Sob continuidade de $P, Q$, para cada condição inicial $v(x_0) = v_0$, existe uma única solução $v \in C^1(I)$, permitindo recuperar $y$ desde que $y \neq 0$.

---

<!-- Slide 9: Exemplo 2 – Bernoulli -->
## Exemplo II
Dada a EDO abaixo, aplicaramos o método de resolução para equações de Bernoulli.
$$
\frac{dy}{dx} + y = y^2.
$$
Identificamos: 
$$
P(x)=1, \; Q(x)=1, \; n=2
$$

---

Calculamos: 
$$
v = y^{1-2} = y^{-1}
$$
Em seguida, derivamos: 
$$
\frac{dv}{dx} = - y^{-2} \frac{dy}{dx}
$$
Multiplicando original por $- y^{-2}$, logo temos que:
$$
\frac{dv}{dx} - v = -1
$$

---

Calculamos o fator integrante:
$$
\mu = e^{-\int 1\, dx} = e^{-x}
$$

Aplicamos o fator integrante e a função $v$ na derivada:
$$\frac{d}{dx}[e^{-x} v] = - e^{-x}$$

Isolamos a função $v$:
$$e^{-x} v = - e^{-x} + C$$

---

Substituimos $v$ na função $y$ e isolamos $y$:
$$v = -1 + C e^{x} \Longrightarrow y = \tfrac{1}{-1 + C e^{x}}$$

---

<!-- Slide 10: Exercícios – Parte 1 -->
## Exercícios

##### 1. Resolva as EDOS Lineares de 1ª Ordem:
a. $\frac{dy}{dx} + 3y = 6$

b. $\frac{dy}{dx} - \frac{2}{x} y = x^2, \quad x>0$

c. $\frac{dy}{dx} + \sin x\, y = \cos x$

d. $17y' - 1y = 2003$

e. $- 2y' + 4y = 20x$

---

##### 2. Resolva as Equações de Bernoulli:
a. $\frac{dy}{dx} + 2y = y^3$ 

b. $\frac{dy}{dx} + \frac{1}{x} y = x y^2, \quad x>0$

c. $\frac{dy}{dx} - y = e^x y^{-1}$

d.  $y(6x²y² − x + 1) + 2xy' = 0$

e. $y' −2 xy = xy²$

f. $y' = y + e ^{-3x}y^4$

---

<!-- Slide 12: Respostas Rápidas -->
## Respostas
1a. $y = 2 + C e^{-3x}$

1b. $y = x^3 + \tfrac{C}{x^2}$

1c. $y = e^{-\int \sin x\, dx} \left( \int e^{\int \sin x\, dx} \cos x\, dx + C \right)$

2a. $y = \tfrac{1}{1 - C e^{2x}}$

2b. $y = \tfrac{1}{\ln x + C}$

2c. $y^2 + C e^{2x} = e^{2x}$

---

<!-- Slide 14: Referências -->
## Referências  
- BOYCE, William E.; DIPRIMA, Richard C. Equações diferenciais elementares. 10. ed. Hoboken: John Wiley & Sons, 2012.
- OLIVEIRA, Rafael Lima. Equações diferenciais ordinárias: métodos de resolução e aplicações. Curitiba: Intersaberes, 2019. 184 p. ISBN 978-85-2270-056-1.
- UNIVERSIDADE ESTADUAL DE LONDRINA (UEL). Equações diferenciais ordinárias. Londrina: UEL, s.d. Disponível em: <http://www.uel.br/projetos/matessencial/superior/pdfs/edo.pdf>. Acesso em: 11 jun. 2025.

---

- UNIVERSIDADE FEDERAL DA BAHIA. Equações diferenciais ordinárias: Licenciatura Matemática UFBA. [S.l.]: UFBA, s.d. e-book. Disponível em: <https://educapes.capes.gov.br/retrieve/166324/eBook_Equacoes_Diferenciais-Licenciatura_Matematica_UFBA.pdf>. Acesso em: 11 jun. 2025.

**Lista de Exercícios BONUS:** 
1. https://docs.ufpr.br/~eidam/2012/2/CM121/CM121_Listas.pdf
2. https://sites.icmc.usp.br/frasson/ALED/listas/lista-edo-ordem1-naolin.pdf