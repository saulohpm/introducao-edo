---
marp: true
theme: gaia
paginate: true
_class: lead
math: katex
---

# Introdução a Equações Diferenciais Ordinárias (EDO)

**Curso:** Introdução a EDO
**Professor:** Saulo Henrique

---

## Objetivos da Aula

- Entender o que é uma **EDO** e sua **notação**  
- Classificar EDOs por **ordem** e **linearidade**  
- Ver exemplos básicos de EDOs
- Aprender o método de **separação de variáveis**  
- Resolver EDOs separáveis passo a passo
- Propor e resolver **exercícios** de prática

---

## 1. O que é uma EDO?

- **Equação Diferencial Ordinária (EDO)** é uma relação que envolve uma função $y(x)$ e suas **derivadas** em relação a $x$.  
- Forma geral (equação implícita):
  $$
    F\bigl(x, y, y', y'', \dots, y^{(n)}\bigr) = 0
  $$

- Exemplo simples (equação explícita de primeira ordem):
  $$
    \frac{dy}{dx} = f(x,y).
  $$

---

## 2. Notação e Terminologia

1. **Solução de uma EDO:** função $y(x)$  que satisfaz a equação diferencial em algum intervalo de $x$.  
2. **Ordem da EDO:** maior ordem da derivada presente.  
   - Se aparece $y^{(n)}$, a equação é de **ordem $n$**.

3. **Grau da EDO:** potência em que a derivada de maior ordem aparece (apenas se a equação puder ser escrita sem raízes ou frações envolvendo derivadas).

---

4. **Função Autônoma:** se $f(x,y)$ não depende de $x$, ou seja, 
   $$
     \frac{dy}{dx} = f(y).
   $$

---

## 3. Exemplos de EDOs e Classificação

1. **EDO de 1ª ordem, linear homogênea:**
   $$
     \frac{dy}{dx} + p(x)\,y = 0.
   $$
2. **EDO de 1ª ordem, linear não homogênea:**
   $$
     \frac{dy}{dx} + p(x)\,y = q(x).
   $$
3. **EDO de 2ª ordem, linear homogênea:**
   $$
     y'' + a(x)\,y' + b(x)\,y = 0.
   $$

---

4. **EDO não linear (exemplo de Bernoulli):**
   $$
     \frac{dy}{dx} + p(x)\,y = q(x)\,y^n,\quad n \neq 0,1.
   $$
5. **EDO autônoma (separável em certos casos):**
   $$
     \frac{dy}{dx} = y(1-y).
   $$

---

## 4. Método de Separação de Variáveis

**Condição:** a EDO deve poder ser escrita na forma
$$
  \frac{dy}{dx} = g(x)\,h(y).
$$
– Aqui, $g(x)$ depende apenas de $x$ e $h(y)$ apenas de $y$.

---

### Passos Gerais

1. **Reescrever**:  
   $$
     \frac{dy}{dx} = g(x)\,h(y) 
     \quad\Longrightarrow\quad
     \frac{1}{h(y)}\,dy = g(x)\,dx.
   $$

2. **Integrar ambos os lados**:  
   $$
     \int \frac{1}{h(y)} \, dy \;=\; \int g(x) \, dx \;+\; C,
   $$

   onde $C$ é a **constante de integração**.
3. **Isolar** $y$ (se possível) para obter a solução explícita $y(x)$.

---

## 5. Exemplo Resolvido Passo a Passo

**Exemplo 1 (com PVI):**  
$$
  \frac{dy}{dx} = x\,y^2, 
  \quad y(0) = 1.
$$

1. **Identifique $g(x)$ e $h(y)$ (Opcional):**  
   $$
     g(x) = x, 
     \quad
     h(y) = y^2.
   $$
2. **Separe variáveis:**  
   $$
     \frac{1}{y^2} \, dy = x \, dx.
   $$

---
  
3. **Integre:**  
   $$
     \int \frac{1}{y^2} \, dy 
     = \int x \, dx 
     \;\Longrightarrow\;
     -\,\frac{1}{y} = \frac{x^2}{2} + C
     \;\Longrightarrow\;
     y = -\frac{2}{x² + C}.
   $$

Neste ponto, já encontramos a solução da EDO, isto é, um conjunto de funções que satisfazem a equação.
  
4. **Determine a constante $C$ usando a condição inicial** $y(0) = 1$:  
   $$
     y = -\frac{2}{x² + C}
     \quad\Longrightarrow\quad
     1 = -\frac{2}{0² + C}
     \quad\Longrightarrow\quad
     1 = -\frac{2}{C}
     \quad\Longrightarrow\quad
     C = -2.
   $$

---

5. **Obtenha solução geral e solução particular:**  
   $$
     y = -\frac{2}{x² + C}
     \quad\Longrightarrow\quad
     y = -\frac{2}{x² -2}
   $$

6. **Região de validade:**  
   $$
     x² -2 \neq 0 
     \;\Longrightarrow\;
     x \neq \pm\sqrt{2}.
   $$

Nota: Perceba que resolver uma EDO é encontrar uma função, a qual é um conjunto de funções que satisfazem a equação. Calcular o PVI (Problema de Valor Inicial) é encontrar uma função específica dentro dessa família de soluções.

---

## 6. Mais Exemplos de EDOs Separáveis

I) $\displaystyle \frac{dy}{dx} = \frac{3x^2}{2y}$  
   - Após Separação: $2\,y\,dy = 3x^2\,dx$.
   - Após Integração: $y^2 = x^3 + C$.

---

II) $\displaystyle \frac{dy}{dx} = e^{-x}\,\sin y$
   - Após Separação: $\dfrac{1}{\sin y}\,dy = e^{-x}\,dx$.  
   - Após Integração: $\displaystyle \ln\!\bigl|\tan\bigl(\tfrac{y}{2}\bigr)\bigr| = -\,e^{-x} + C$.

Desafio: Se possível, tente isolar $y$ neste item II.

---

## 7. Exercícios Propostos

1. **Verifique se as EDOs abaixo são separáveis, caso sejam, resolva. Em seguida calcule seus respectivos PVIs**:  

   a) $\displaystyle \frac{dy}{dx} = \frac{x}{1 + y^2}, \quad y(0)=0.$

   b) $\displaystyle \frac{dy}{dx} = (2x + 1)(3y^2), \quad y(0)=1.$

---

2. **Encontre a solução geral** (sem condição inicial):  
   a) $\displaystyle \frac{dy}{dx} = \frac{y}{x},\quad x > 0.$

   b) $\displaystyle \frac{dy}{dx} = \frac{x^2}{y^3}$

3. **Um modelo de taxa de decaimento radioativo em função do tempo é dada por:**

   $$\displaystyle \frac{dN}{dt} = -\lambda\,N$$

   a) Resolva essa EDO.
   b) Explique o significado físico da constante $\lambda$ e seu sinal.

---

4. **Essa é um modelo para equação logística** (autônoma não linear):  
   $$
     \frac{dP}{dt} = r\,P\Bigl(1 - \frac{P}{K}\Bigr)
   $$  
   a) Mostre que é separável. 
   b) Resolva em termos de $P(t)$.

5. **Desafio extra**:  
   Considere $\displaystyle \frac{dy}{dx} = \frac{x^2 + 1}{y^2 + y}.$  
   a) Verifique se é separável.
   b) Resolva implicitamente a EDO.

---

## 8. Resolução de Alguns Exercícios (Dica de Roteiro)

1. **Exercício 1a**:  
   $$
     \frac{dy}{dx} = \frac{x}{1 + y^2} 
     \;\Longrightarrow\; 
     (1 + y^2)\,dy = x\,dx 
     \;\Longrightarrow\; 
     \int (1 + y^2)\,dy = \int x\,dx 
   $$

   $$
     y + \frac{y^3}{3} = \frac{x^2}{2} + C 
   $$

   Usando $y(0)=0$, temos que $0 + 0 = 0 + C \;\Rightarrow\; C=0.$  

---

   $$
     y + \frac{y^3}{3} = \frac{x^2}{2}.
   $$  
   (Solução implícita, pois é difícil isolar $y$ explicitamente.)

2. **Exercício 2a**:  
   $$
     \frac{dy}{dx} = \frac{y}{x}
     \;\Longrightarrow\;
     \frac{1}{y}\,dy = \frac{1}{x}\,dx 
     \;\Longrightarrow\;
     \ln|y| = \ln|x| + C
     \;\Longrightarrow\;
     y = Cx.
   $$

3. **Exercício 3a**:  
   $$
     \frac{dN}{dt} = -\lambda N 
     \;\Longrightarrow\; 
     \frac{1}{N}\,dN = -\lambda\,dt 
     \;\Longrightarrow\; 
     \ln|N| = -\lambda t + C 
     \;\Longrightarrow\; 
     N(t) = Ce^{-\lambda t}.
   $$

*(As demais resoluções seguem lógica parecida.)*

---

## 9. Referências

- OLIVEIRA, Rafael Lima. Equações diferenciais ordinárias: métodos de resolução e aplicações. Curitiba: Intersaberes, 2019. 184 p. ISBN 978-85-2270-056-1.
- UNIVERSIDADE ESTADUAL DE LONDRINA (UEL). Equações diferenciais ordinárias. Londrina: UEL, s.d. Disponível em: <http://www.uel.br/projetos/matessencial/superior/pdfs/edo.pdf>. Acesso em: 11 jun. 2025.

---

- UNIVERSIDADE FEDERAL DA BAHIA. Equações diferenciais ordinárias: Licenciatura Matemática UFBA. [S.l.]: UFBA, s.d. e-book. Disponível em: <https://educapes.capes.gov.br/retrieve/166324/eBook_Equacoes_Diferenciais-Licenciatura_Matematica_UFBA.pdf>. Acesso em: 11 jun. 2025.

**Lista de Exercícios BONUS:** 
1. https://docs.ufpr.br/~eidam/2012/2/CM121/CM121_Listas.pdf
2. https://sites.icmc.usp.br/frasson/ALED/listas/lista-edo-ordem1-naolin.pdf