---
tags:
  - calcolabilita
---
___
## <u>automa deterministico</u>
Un **automa finito deterministico** e' una quintupla $(Q, \Sigma, \delta, q_0, F)$, dove:
1. $Q$ e' un insieme finito chiamato **insieme degli stati**,
2. $\Sigma$ e' un insieme finito chiamato **alfabeto di simboli**,
3. $\delta : Q\times\Sigma\to Q$ e' la **funzione di transizione**,
4. $q_0 \in Q$ e' lo **stato iniziale**,
5. $F \subseteq Q$ e' l'**insieme degli stati finali** o **accettanti**.
___
## <u>automa non deterministico</u>
Un **automa finito non deterministico** e' una quintupla $(Q, \Sigma, \delta, q_0, F)$, dove:
1. $Q$ e' un insieme finito chiamato **insieme degli stati**,
2. $\Sigma$ e' un insieme finito chiamato **alfabeto di simboli**,
3. $\delta : Q\times(\Sigma\cup\{\lambda\})\to Q$ e' la **funzione di transizione**,
4. $q_0 \in Q$ e' lo **stato iniziale**,
5. $F \subseteq Q$ e' l'**insieme degli stati finali** o **accettanti**.

#### <u>cause di non determinismo</u>
In un **NFA** ci sono due cause di non determinismo:
- piu' transizioni partono da uno stato con la stessa etichetta
- transizioni vuote
___
## <u>differenze tra DFA e NFA</u>
La differenza tra un **DFA** e un **NFA** e' che, dato un simbolo dell'alfabeto in input:

- In un **DFA**, **esiste al massimo una transizione** per ogni coppia $(q,a)$, dove $q\in Q$ e $a \in \Sigma$. Cioè, **la funzione di transizione è deterministica**: ogni stato ha **una sola uscita** per ogni simbolo dell'alfabeto. In altre parole, per ogni stato e simbolo, il prossimo stato è **unico e ben definito**.

- In un **NFA**, invece, la funzione di transizione può associare **più di uno stato** (o **nessuno**) a una coppia $(q,a)$, e può anche prevedere **transizioni vuote** (chiamate **transizioni lambda** o **$\lambda$-transizioni**), che permettono all'automa di passare da uno stato all'altro **senza leggere alcun simbolo di input**. Quindi, **da uno stato possono partire più transizioni per lo stesso simbolo**, e anche per $\lambda$.

> NOTA BENE:
> nonostante le differenze nel funzionamento, **DFA e NFA riconoscono esattamente la stessa classe di linguaggi**, ovvero i **linguaggi regolari**.
____
## <u>teorema: equivalenza della classe di linguaggi DFA e NFA</u>
**ipotesi**: Per ogni NFA esiste sempre un DFA equivalente che riconosce lo stesso linguaggio.
**dimostrazione**:
Sia $N = (Q, \Sigma, \delta, q_0, F$) un **NFA** che riconosce un qualsiasi linguaggio **A**;

___
## <u>linguaggi regolari</u>
Un linguaggio e' definito **regolare** quando e' riconosciuto da un automa finito, che sia *deterministico* o *non deterministico*.
___