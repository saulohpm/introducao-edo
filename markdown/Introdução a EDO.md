---
marp: true
theme: gaia
paginate: true
_class: lead
math: katex
---

# Introdução ao Estudo de Equações Diferenciais Ordinárias

**Curso:** Introdução a EDO (Aula 1)
**Professor:** Saulo Henrique

---

## Objetivos da Aula

- Compreender **o que é** uma Equação Diferencial Ordinária (EDO) e sua motivação
- Dominar a **notação** e a **terminologia** fundamental
- Classificar EDOs por **ordem**, **grau** e **linearidade**
- Entender o conceito de **solução** de uma EDO
- Reconhecer EDOs em **modelos matemáticos** reais

---

## 1. Por que estudar EDOs?

As EDOs aparecem naturalmente quando descrevemos **como quantidades variam**. Alguns exemplos:

- **Física:** velocidade de um objeto em queda com resistência do ar
- **Biologia:** crescimento populacional
- **Química:** taxa de reação de um composto
- **Engenharia:** circuitos elétricos, sistemas mecânicos
- **Economia:** modelos de crescimento de capital

---

> A essência de uma EDO é relacionar uma função com suas taxas de variação.

---

## 2. O que é uma EDO?

Uma **Equação Diferencial Ordinária (EDO)** é uma equação que envolve uma função desconhecida $y(x)$ e pelo menos uma de suas **derivadas** em relação à variável independente $x$.

**Forma geral implícita:**
$$
F\!\bigl(x,\, y,\, y',\, y'',\, \dots,\, y^{(n)}\bigr) = 0
$$

---

**Forma explícita de primeira ordem** (a mais comum):
$$
\frac{dy}{dx} = f(x, y)
$$

> O termo "ordinária" distingue essas equações das **Equações Diferenciais Parciais (EDP)**, onde a função desconhecida depende de mais de uma variável.

---

## 3. Terminologia Fundamental

### 3.1 Ordem

A **ordem** de uma EDO é a **maior derivada** que aparece na equação.

| Equação | Ordem |
|---|---|
| $y' = 2x$ | 1ª |
| $y'' + 3y' - y = 0$ | 2ª |
| $y''' = \sin(x)$ | 3ª |

---

### 3.2 Grau

O **grau** de uma EDO é a **potência** em que a derivada de maior ordem aparece, desde que a equação seja **polinomial** nas derivadas (sem raízes nem frações envolvendo derivadas).

**Exemplos:**

- $y'' + y = 0$ → grau **1** (pois $y''$ aparece elevado à 1ª potência)
- $(y'')^3 + y = x$ → grau **3**
- $\sqrt{y''} + y = 0$ → grau **indefinido** (não é polinomial em $y''$)

---

### 3.3 Linearidade

Uma EDO de ordem $n$ é **linear** se puder ser escrita na forma:
$$
a_n(x)\,y^{(n)} + a_{n-1}(x)\,y^{(n-1)} + \cdots + a_1(x)\,y' + a_0(x)\,y = g(x)
$$

Exigências para linearidade:
1. $y$ e todas as suas derivadas aparecem apenas com **potência 1**
2. Não há **produtos** entre $y$ e suas derivadas
3. Os coeficientes $a_k(x)$ dependem apenas de $x$

Se qualquer dessas condições falha, a EDO é **não linear**.

---

### 3.4 Homogeneidade

Para EDOs lineares da forma $a_n(x)y^{(n)} + \cdots + a_0(x)y = g(x)$:

- **Homogênea:** $g(x) = 0$ para todo $x$
  $$y'' + 3y' - y = 0$$

- **Não homogênea:** $g(x) \neq 0$
  $$y'' + 3y' - y = e^x$$

---

### 3.5 EDO Autônoma

Uma EDO é **autônoma** quando a variável independente $x$ não aparece explicitamente:
$$
\frac{dy}{dx} = f(y)
$$

**Exemplo:** $\dfrac{dy}{dx} = y(1 - y)$

São especialmente importantes em modelos populacionais e físicos, pois o comportamento do sistema não depende do "instante de partida".

---

## 4. Exemplos e Classificação

**1. EDO de 1ª ordem, linear, homogênea:**
$$
\frac{dy}{dx} + p(x)\,y = 0
$$

**2. EDO de 1ª ordem, linear, não homogênea:**
$$
\frac{dy}{dx} + p(x)\,y = q(x)
$$

---

**3. EDO de 2ª ordem, linear, homogênea:**
$$
y'' + a(x)\,y' + b(x)\,y = 0
$$

**4. EDO não linear — Equação de Bernoulli:**
$$
\frac{dy}{dx} + p(x)\,y = q(x)\,y^n, \quad n \neq 0, 1
$$
*(não linear pois $y^n$ aparece com potência $n > 1$)*

---

**5. EDO autônoma não linear (modelo logístico):**
$$
\frac{dP}{dt} = r\,P\!\left(1 - \frac{P}{K}\right)
$$

**6. EDO não linear com derivada elevada ao quadrado:**
$$
(y')^2 + y = \sin x
$$

---

## 5. O que é uma Solução?

Uma **solução** de uma EDO em um intervalo $I$ é uma função $\phi(x)$, definida e derivável em $I$, tal que ao substituí-la na equação, a igualdade é satisfeita **identicamente** em $I$.

**Exemplo:** Verifique que $y = e^{2x}$ é solução de $y' - 2y = 0$.

- Calculamos: $y' = 2e^{2x}$
- Substituímos: $2e^{2x} - 2e^{2x} = 0$ ✓

---

### 5.1 Família de Soluções

Em geral, resolver uma EDO de ordem $n$ produz uma **família de soluções** com $n$ constantes arbitrárias $C_1, C_2, \ldots, C_n$:

$$
y' = 2x \;\Longrightarrow\; y = x^2 + C
$$

Cada valor de $C$ corresponde a uma curva diferente — chamamos esse conjunto de **solução geral**.

---

### 5.2 Problema de Valor Inicial (PVI)

Para selecionar **uma solução específica** dentro da família, impomos **condições iniciais**: valores de $y$ (e possivelmente de $y'$, $y''$, …) em um ponto $x_0$.

**Exemplo:**
$$
y' = 2x, \quad y(1) = 3
$$
- Solução geral: $y = x^2 + C$
- Usando $y(1) = 3$: $3 = 1 + C \Rightarrow C = 2$
- **Solução particular:** $y = x^2 + 2$

---

### 5.3 Solução Explícita e Implícita

- **Explícita:** $y$ está isolada: $y = x^2 + 2$
- **Implícita:** a solução é dada por uma relação $G(x, y) = 0$, sem que $y$ esteja isolada:
  $$
    x^2 + y^2 = 1
  $$

Nem sempre é possível ou conveniente isolar $y$ — soluções implícitas são perfeitamente válidas.

---

### 5.4 Existência e Unicidade (Intuição)

Uma pergunta natural: **toda EDO tem solução? E ela é única?**

O **Teorema de Picard–Lindelöf** garante que, sob condições de regularidade em $f(x,y)$, o PVI
$$
y' = f(x,y), \quad y(x_0) = y_0
$$
possui **solução única** em algum intervalo ao redor de $x_0$.

> Não provaremos o teorema, mas é importante saber que nem toda EDO tem solução, e nem toda solução é única.

---

## 6. EDOs em Modelos Matemáticos

**Crescimento exponencial (Malthus, 1798):**
$$
\frac{dP}{dt} = r\,P, \quad P(0) = P_0
$$
Solução: $P(t) = P_0\,e^{rt}$.

---

**Resfriamento de Newton:**
$$
\frac{dT}{dt} = -k\,(T - T_{\text{amb}})
$$

Descreve como a temperatura de um objeto se aproxima da temperatura ambiente.

---

**Decaimento radioativo:**
$$
\frac{dN}{dt} = -\lambda\,N
$$
$\lambda > 0$: constante de decaimento. Solução: $N(t) = N_0\,e^{-\lambda t}$.

---

**Circuito RC (resistor-capacitor):**
$$
R\,\frac{dq}{dt} + \frac{q}{C} = V(t)
$$
Relaciona a carga $q(t)$ no capacitor com a tensão aplicada $V(t)$.

> Perceba que **resolver** a EDO significa encontrar a função que descreve o fenômeno.

---

## 7. Exercícios de Fixação

1) Para cada EDO abaixo, identifique: ordem, grau (se definido), linear ou não linear, homogênea ou não (quando aplicável).

a) $y'' + 5y' - 6y = \cos x$

b) $\bigl(y'\bigr)^2 + y = x$

c) $y''' - y'' + y = 0$

d) $y' = y^2 - x$

---

2) Verifique se as funções dadas são soluções das respectivas EDOs.

a) $y = 3e^{-x}$ é solução de $y' + y = 0$?

b) $y = \sin(2x)$ é solução de $y'' + 4y = 0$?

c) $y = x\ln x$ é solução de $x^2 y'' - xy' + y = 0$?

---

3) Resolva o que cada item pede.

a) Ache a solução geral de $y' = 3x^2$.

b) Determine a constante usando $y(0) = 5$.

c) Verifique sua resposta substituindo na EDO.

---

4) Considere o modelo de resfriamento de Newton:
$$
\frac{dT}{dt} = -k\,(T - 20), \quad k > 0
$$
onde $T$ é a temperatura (em °C) e $t$ é o tempo (em minutos), sendo 20°C a temperatura ambiente.

a) Que tipo de EDO é essa (ordem, linearidade)?  
b) Interprete fisicamente o sinal negativo no lado direito.  
c) Se a temperatura inicial é $T(0) = 80°C$, qual seria o comportamento esperado de $T(t)$ quando $t \to \infty$?

---

## 8. Roteiro de Resoluções

**Exercício 1:**

| EDO | Ordem | Grau | Tipo |
|---|---|---|---|
| a) $y'' + 5y' - 6y = \cos x$ | 2ª | 1 | Linear, NH |
| b) $(y')^2 + y = x$ | 1ª | 2 | Não linear |
| c) $y''' - y'' + y = 0$ | 3ª | 1 | Linear, H |
| d) $y' = y^2 - x$ | 1ª | 1 | Não linear |

---

**Exercício 2a:** $y = 3e^{-x}$, EDO: $y' + y = 0$

$y' = -3e^{-x} \;\Longrightarrow\; y' + y = -3e^{-x} + 3e^{-x} = 0$ ✓

**Exercício 2b:** $y = \sin(2x)$, EDO: $y'' + 4y = 0$

$y' = 2\cos(2x),\; y'' = -4\sin(2x)$

$y'' + 4y = -4\sin(2x) + 4\sin(2x) = 0$ ✓

---

**Exercício 3:**

a) $y' = 3x^2 \;\Longrightarrow\; y = x^3 + C$ (solução geral)

b) $y(0) = 5 \;\Longrightarrow\; 5 = 0 + C \;\Longrightarrow\; C = 5$

Solução particular: $y = x^3 + 5$

c) Verificação: $y' = 3x^2$ ✓

---

## 9. Conexão com a Próxima Aula

Agora que conhecemos os conceitos fundamentais das EDOs, estamos prontos para **resolver** equações de primeira ordem.

**Aula 02 — Capítulo 2:** EDOs de Primeira Ordem
- Método de **separação de variáveis**
- Equações **lineares de 1ª ordem** e o fator integrante
- Equações de **Bernoulli**
- Aplicações: modelos de crescimento, decaimento, misturas

---

## 10. Referências

- OLIVEIRA, Rafael Lima. *Equações diferenciais ordinárias: métodos de resolução e aplicações.* Curitiba: Intersaberes, 2019.
- UNIVERSIDADE ESTADUAL DE LONDRINA (UEL). *Equações diferenciais ordinárias.* Disponível em: <http://www.uel.br/projetos/matessencial/superior/pdfs/edo.pdf>.
- UNIVERSIDADE FEDERAL DA BAHIA. *Equações diferenciais ordinárias: Licenciatura Matemática UFBA.* Disponível em: <https://educapes.capes.gov.br/retrieve/166324/eBook_Equacoes_Diferenciais-Licenciatura_Matematica_UFBA.pdf>.