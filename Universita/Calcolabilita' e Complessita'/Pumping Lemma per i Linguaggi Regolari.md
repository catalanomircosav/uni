---
tags:
  - calcolabilità
---
___
Il **Pumping Lemma per i linguaggi regolari** e' uno strumento fondamentale per dimostrare che un linguaggio _non_ è regolare.

### <u>come provare che un linguaggio non è regolare?</u>
Per dimostrare che un linguaggio non è regolare, è necessario provare che non esiste nessuna Macchina a Stati Finiti Deterministica (DFA), Non Deterministica (NFA), o espressione regolare che possa accettarlo. Questa dimostrazione si basa su un principio più generale noto come **Pigeonhole Principle** (Principio dei cassetti o principio del buco della colomboia).

### Il Pigeonhole Principle

Il Pigeonhole Principle (formulato da Lejeune Dirichlet) afferma che se si mappano gli elementi di un insieme $A$ (colombi) in un insieme $B$ (posti della colombaia), e **se il numero di elementi in $A$ è maggiore del numero di elementi in $B$ ($|A|>|B|$), allora la funzione di mappatura non può essere iniettiva** (cioè, almeno due colombi devono condividere lo stesso posto). Più in generale, se $n$ oggetti sono distribuiti in $m$ insiemi, almeno un insieme contiene `⌈n/m⌉` oggetti, e i restanti insiemi contengono al più `⌊n/m⌋` oggetti.

Esempi del Pigeonhole Principle includono:

- La probabilità che due persone abbiano lo stesso compleanno è del 100% se ci sono 367 persone.
- A Londra, almeno due persone hanno lo stesso numero di capelli, dato che il numero massimo di capelli è di circa 1 milione, ma ci sono più di 1 milione di persone.

Il Pigeonhole Principle ha implicazioni anche nella **compressione dati**: nessun algoritmo di compressione _lossless_ (senza perdita di informazione) può comprimere efficientemente _tutti_ i dati. Se un algoritmo lossless rende alcuni input più piccoli, deve necessariamente rendere altri input più grandi. Questo perché, altrimenti, l'insieme di tutte le sequenze di input fino a una certa lunghezza `L` potrebbe essere mappato a un insieme più piccolo di tutte le sequenze di lunghezza inferiore a `L` senza collisioni, cosa che il Pigeonhole Principle esclude per la natura lossless della compressione.

### Il Pumping Lemma e il Pigeonhole Principle nei DFA
In un DFA, il Pigeonhole Principle è cruciale: **se un DFA ha, per esempio, 4 stati, per una stringa lunga almeno 4 caratteri, esiste almeno uno stato attraversato almeno due volte**. In generale, per una stringa $w = σ_1σ_2…σ_k$ con lunghezza `k` maggiore del numero di stati dell'automa, esiste sempre almeno uno stato attraversato almeno due volte. Questo "stato ripetuto" implica l'esistenza di un **loop** nel percorso del DFA per la stringa data.

### Il Teorema del Pumping Lemma per i Linguaggi Regolari

Il Pumping Lemma formalizza questa idea: Sia `L` un **linguaggio regolare infinito**. Allora esiste un intero `m` (spesso chiamato "lunghezza di pompaggio" o "lunghezza critica") tale che, per ogni stringa `w` in `L` con **`|w| > m`**, `w` può essere partizionata in `w = xyz` in modo che valgono le seguenti condizioni:

- **`|xy| <= m`**: La parte `xy` della stringa ha una lunghezza non superiore a `m`. Questo significa che il "loop" (la parte `y`) si verifica all'inizio della stringa, entro i primi `m` caratteri.
- **`|y| >= 1`**: La parte `y` (il loop) non è vuota; deve contenere almeno un carattere.
- **`xy^i z` è in `L` per ogni `i >= 0`**: Ripetendo la parte `y` `i` volte (incluso zero volte, ovvero `xz`), la stringa risultante è ancora accettata dal DFA e appartiene al linguaggio `L`.

#### Dimostrazione del Pumping Lemma (schizzo)

1. Se `L` è regolare, esiste un DFA che lo accetta.
2. Si pone `m = |Q|`, dove `|Q|` è il numero di stati nel DFA.
3. Si considera una stringa `w = σ1σ2…σk` tale che `|w| > m`. Per il Pigeonhole Principle, esiste almeno uno stato che viene attraversato almeno due volte durante l'elaborazione di `w`. Si prende il _primo_ stato che viene ripetuto.
4. La stringa `w` viene partizionata in `x`, `y`, `z` come segue:
    - `x`: la parte della stringa che porta al primo stato ripetuto.
    - `y`: la parte della stringa che va dallo stato ripetuto a se stesso, formando un loop.
    - `z`: la parte rimanente della stringa.
5. Le condizioni del Pumping Lemma derivano da questa partizione:
    - **`|xy| <= m`**: Nessuno stato è ripetuto all'interno di `xy`, eccetto lo stato che chiude il loop di `y`. Questo è perché il loop è scelto come il _primo_ loop che si incontra, e avviene entro i primi `m` transizioni (poiché il numero di stati è `m`).
    - **`|y| >= 1`**: Poiché `y` rappresenta un loop tra stati, non può essere vuoto.
    - **`xy^i z` è in `L`**: Attraversando il loop `y` `i` volte (o zero volte, o più volte), si ritorna allo stesso stato, e da lì si segue il percorso `z` per raggiungere uno stato finale. La dimostrazione procede per induzione su `i`.

### Usare il Pumping Lemma per Provare che un Linguaggio non è Regolare

La strategia per dimostrare che un linguaggio infinito `L` non è regolare è un processo di **dimostrazione per assurdo**:

1. **Si assume che `L` sia regolare**.
2. **Allora, deve valere il Pumping Lemma per `L`**. Questo implica che esiste una lunghezza critica `m`.
3. **Si sceglie una stringa `w` specifica in `L`** che sia sufficientemente lunga (`|w|>m`) per soddisfare le condizioni del Pumping Lemma. Questa stringa `w` è cruciale per la dimostrazione.
4. **Si mostra che, per qualche `i`, la stringa `w' = xy^i z` (ottenuta pompando `w`) _non_ è in `L`**, il che porta a una contraddizione con il Pumping Lemma.
5. **Si conclude che l'assunzione iniziale (che `L` fosse regolare) è falsa**, e quindi `L` non è regolare.

#### Esempio: `L = {a^n b^n, n positive}` non è regolare

1. **Assumiamo per assurdo che `L` sia regolare.**
2. Per il Pumping Lemma, esiste un intero `m`.
3. **Scegliamo una stringa `w`** tale che `|w| > m`. La scelta migliore è **`w = a^m b^m`**. Questa stringa è in `L`.
4. Per il Pumping Lemma, `w` deve essere partizionata in `xyz` tale che `|xy| <= m` e `|y| >= 1`.
5. Poiché `|xy| <= m` e `w = a^m b^m`, la parte `xy` deve essere completamente contenuta nella prima parte della stringa, che consiste solo di 'a'. Pertanto, **`y` deve essere una stringa composta solo da 'a's** (ad esempio, `y = a^k` per qualche `k >= 1`).
6. Consideriamo la stringa **`w' = xy^2 z`**. Pompando `y` una volta in più, il numero di 'a's aumenta, ma il numero di 'b's rimane lo stesso. La stringa risultante sarà della forma `a^(m+k) b^m`.
7. Questa stringa `a^(m+k) b^m` **non è in `L`** perché il numero di 'a's e 'b's non è uguale (dato che `k >= 1`, `m+k != m`).
8. Questo contraddice il Pumping Lemma, che afferma che `xy^i z` deve essere in `L` per ogni `i`.
9. Quindi, la nostra assunzione iniziale era falsa, e **`L = {a^n b^n}` non è un linguaggio regolare**.