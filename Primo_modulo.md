##Primo Modulo
**Stato:** Insieme di operazioni che puoi fare su un sistema. Può essere descritto anche la proprietà fisica di più sistemi preparati nello stesso modo, che creano una funzione d'onda.

**Misurazione:** Un'unico sistema non è misurabile, l'unico modo sarebbe attraverso la clonazione, che renderebbe possibile uno scambio di informazioni più veloce della luce attraverso il quantum entanglement.
Un sistema va misurato più volte, partendo dallo stesso stato iniziale, per avere una stima della probabilità di misurare un certo stato e ricostruire così lo stato iniziale. Questo metodo si chiama *tomografia quantistica*.

**Non clonabilità:** Una particella non è clonabile(a meno che il suo stato non sia ortogonale) perchè nel momento in cui si misura il suo stato collassa in uno stato 0 o 1, e quindi non è più possibile misurare il suo stato originale.

####Postulato 4: Sistemi Composti
Uno stato componente $\ket{\Psi}$ di un sistema composto contiene tutte le funzioni d'onda dei singoli sistemi se separabili.
$$\ket{\Psi} = \ket{\psi_1} \otimes \ket{\psi_2} \otimes \ket{\psi_3} \otimes \ket{\psi_4} \equiv \ket{\psi_1 \psi_2 \psi_3 \psi_4}$$
###3.0 Primitive della Quantum Information Processing
**Coerenza Quantistica:** Possibilità di avrere stati di sovrapposizione.

**Qubit:** Stato quantistico di un sistema quantistico a due livelli. Un qubit è un vettore di dimensione 2.
$$\ket{\psi} = \alpha \ket{0} + \beta \ket{1}$$
Dato dalla somma delle ampiezze di probabilità $\alpha$ e $\beta$. Soddisfano la condizione di normalizzazione $|\alpha|^2 + |\beta|^2 = 1$.

**Sfera di Bloch:** Rappresentazione geometrica di un qubit. Ogni punto sulla sfera rappresenta uno stato quantistico.
$$\ket{\psi} = \alpha \ket{0} + \beta \ket{1} = e^{i\gamma}(\cos(\theta/2)\ket{0} + e^{i\phi}\sin(\theta/2)\ket{1})$$    
Dove $\theta$ e $\phi$ sono le coordinate sferiche e $\gamma$ è la fase globale.
I corrispettivi intervalli di $\theta$, $\phi$ e $\gamma$ sono $[0,\pi]$, $[0,2\pi]$ e $[0,2\pi]$.
//TODO: Aggiungere immagine della sfera di Bloch
Si utilizzano 3 dimensioni per rappresentare uno stato quantistico, ma in realtà è un vettore di dimensione 2. Le prim due dimensione sono le ampiezze complesse di probabilità, mentre la terza è la fase locale.

**Fase globale:** Fase applicata uniformemente a tutto lo stato quantistico. Non ha effetti misurabili, perchè la probabilità di misurare un certo stato è data dal modulo quadro delle ampiezze di probabilità.

**Fase locale:** Fase applicata solo ad una parte dello stato quantistico. Puà influenzare la correlazione quantistica tra qubit, per esempio alterando le proprietà di entanglement.

**Informazione:** In un qubit può essere scritto anche tutto Wikipedia, ma non si può leggere perchè non si può clonare un qubit. Quindi l'informazione è la capacità di fare delle operazioni su un sistema. Un algoritmo deve sapere leggere senza effettuare una misurazione, altrimenti si perde l'informazione.
###3.2 2 Qubits
$$\ket{\psi} = \alpha_{00} \ket{00} + \alpha_{0} \ket{01} + \alpha_{10} \ket{10} + \alpha_{11} \ket{11}$$
Dove $\alpha_{00}$, $\alpha_{01}$, $\alpha_{10}$ e $\alpha_{11}$ sono le ampiezze di probabilità. Soddisfano la condizione di normalizzazione $|\alpha_{00}|^2 + |\alpha_{01}|^2 + |\alpha_{10}|^2 + |\alpha_{11}|^2 = 1$.

**Esempio:**
Misura del primo qubit con lo stato $\ket{0}$:
$$(\ket{0}_1 \bra{0} \otimes \mathbb{I_2})\ket{\psi} = \frac{\alpha_{00}\ket{00} + \alpha_{01}\ket{01}}{\sqrt{|\alpha_{00}|^2 + |\alpha_{01}|^2}}$$
Dove $\ket{0}_1 \bra{0}$ è l'operatore di proiezione sullo stato $\ket{0}$ del primo qubit e $\mathbb{I_2}$ è l'identità del secondo qubit.
Gli stati qualunque sia l'ampiezza di $\alpha_{00}$ e $\alpha_{01}$ non possono essere stati entangled perchè possono essere sempre scritti come il prodotto di due stati singoli.
$$
\ket{\psi} = \frac{1}{\sqrt{2}}\ket{0}(\ket{0} + \ket{1})
$$
Nel momento in cui ho una proiezione su uno stato non potrò mai avere uno stato entangled.

**Esempio:**
$\alpha_{00} = \frac{1}{\sqrt{2}} = \alpha_{11}$
$$\ket{\psi} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) \neq \ket{\psi_1} \otimes \ket{\psi_2}$$
Questa formula è importante perchè mostra che non è possibile scrivere uno stato composto come il prodotto di due stati singoli. Questo è un esempio di entanglement, poichè non è possibile scrivere uno stato composto come il prodotto di due stati singoli.
###3.3 Porte Logiche
Tutte le trasformazioni su un qubit possono essere descritte da una matrice unitaria 2x2. 
$$U^\dagger U = \mathbb{I}$$
**Porta NOT:** Cambia lo stato di un qubit.
$$\ket{0} \rightarrow \ket{1} \\\ket{1} \rightarrow \ket{0}$$
Più in generale:
$$\ket{\psi} = \alpha \ket{0} + \beta \ket{1} \rightarrow \ket{\psi'} = \alpha' \ket{1} + \beta' \ket{0}$$
Dove l'operatore NOT è rappresentato dalla matrice:
$$X = \sigma_x = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$$
**Porta Hadamard:** Crea uno stato di sovrapposizione.
$$\ket{0} \rightarrow \frac{1}{\sqrt{2}}(\ket{0} + \ket{1}) \equiv {\ket +} \\ \ket{1} \rightarrow \frac{1}{\sqrt{2}}(\ket{0} - \ket{1}) \equiv {\ket -}$$
Più in generale:
$$\ket{\psi} = \alpha \ket{0} + \beta \ket{1} \rightarrow \ket{\psi'} = \frac{1}{\sqrt{2}}(\alpha + \beta) \ket{0} + \frac{1}{\sqrt{2}}(\alpha - \beta) \ket{1}$$
Dove l'operatore Hadamard è rappresentato dalla matrice:
$$H = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$$
**Trasformazione unitaria:**
$$U = e^{i\alpha} \begin{pmatrix} e^{\frac{- i\beta}{2}} & 0 \\ 0 & e^{\frac{i\beta}{2}} \end{pmatrix} \begin{pmatrix} \cos(\frac{\gamma}{2}) & -\sin(\frac{\gamma}{2}) \\ \sin(\frac{\gamma}{2}) & \cos(\frac{\gamma}{2}) \end{pmatrix} \begin{pmatrix} e^{\frac{- i\delta}{2}} & 0 \\ 0 & e^{\frac{i\delta}{2}} \end{pmatrix}$$
Dove $\alpha$ è la fase globale(non interessante), la prima matrice cambia la fase relativa tra qubit 0 e 1 ed effettua una rotazione intorno a z, la seconda matrice effettua una rotazione sul piano ortogonale.
Una trasformaizone su singolo bit si chiama quindi *rotazione*.

**Porte a 2 qubit:**
La NAND è una porta logica a 2 bit chiamata universale perchè ci permette di scrivere tutte le altre porte.
In meccanica quantistica si utilizza la porta CNOT.
La porta CNOT effettua un controllo sul primo qubit e se è 1 effettua una NOT sul secondo qubit(che è il target), il not è descritto come $b \rightarrow a \oplus b$.
//TODO: Aggiungere immagine della porta CNOT
$$U_{CNOT} = \begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 0 & 1 \\ 0 & 0 & 1 & 0 \end{pmatrix}$$
$U_{CNOT}^\dagger U_{CNOT} = \mathbb{I}$

La porta CNOT(X) può essere anche descritta con una porta Hadamard, la matrice $\delta_z$ e un'altra porta Hadamard.
//TODO: Aggiungere immagine della porta CNOT con le porte Hadamard
$$\ket{0} \rightarrow \ket{1} \equiv \ket{0} \rightarrow \ket{+} \rightarrow \ket{-} \rightarrow \ket{1} \\ \ket{1} \rightarrow \ket{0} \equiv \ket{1} \rightarrow \ket{-} \rightarrow \ket{+} \rightarrow \ket{0}$$
### 3.5 Logica Classica con Qubit
**Porta Toffoli:** Porta logica a 3 bit che effettua una NAND sul terzo bit se i primi due sono 1, dove la NAND è descritta come $c \rightarrow c \oplus ab$.
//TODO: Aggiungere immagine della porta Toffoli
//TODO: Aggiungere tabella di verità della porta Toffoli
Si può rappresentare il NAND con la porta Toffoli
//TODO: Aggiungere immagine NAND con la porta toffoli
Lo stato di input è quindi reversibile perchè manteniamo a e b nell'output.

**Copy(FANOUT):** Non è possibile copiare un qubit, ma è possibile copiare un qubit classico.
//TODO: Aggiungere immagine della porta copy

**Esempio Copy di un qubit non ortogonale:**
//TODO: Aggiungere esempio di copy di un qubit non ortogonale

**Numeri Casuali:**
L'output è un bit classico con probabilità 0.5 di essere 0 o 1.
//TODO: Aggiungere immagine della porta random

### 3.6 Misura in un'altra base
Altra base: $\ket{+}, \ket{-} \leftrightarrow \bra{+} \ket{+}, \bra{-} \ket{-}$
Avere questa base è sinonimo di proiettare sugli stati $\ket{+}$ e $\ket{-}$.
Un esempio di stato generico è:
$$\ket{\psi} = \alpha \frac{1}{\sqrt{2}}(\ket{+} + \ket{-}) + \beta \frac{1}{\sqrt{2}}(\ket{+} - \ket{-}) = \frac{1}{\sqrt{2}}(\alpha + \beta)\ket{+} + \frac{1}{\sqrt{2}}(\alpha - \beta)\ket{-}$$
Dove $\ket{+}$ ha probabilità $\frac{1}{\sqrt{2}}|\alpha + \beta|^2$ e $\ket{-}$ ha probabilità $\frac{1}{\sqrt{2}}|\alpha - \beta|^2$.

### 3.7 Circuiti
Presentiamo la porta *SWAP* che scambia i due qubit.
//TODO: Aggiungere immagine della porta SWAP
La serie di computazioni che avvengono sono: 
$$\ket{a,b} \xrightarrow{1°CNOT} \ket{a,a \oplus b} \xrightarrow{2°CNOT} \ket{a \oplus (a \oplus b), a \oplus b} = \ket{b,a \oplus b} \xrightarrow{3°CNOT} \ket{b, b \oplus (a \oplus b)} = \ket{b,a}$$
Lo SWAP non viene fatto utilizzando cavi, poichè la maggior parte delle volte i computer quantistici sono superconduttori e quindi non hanno cavi. I qubit sono collegati tra loro da una rete di microonde. Dovremmo letteralmente tagliarli e incollarli per fare uno SWAP.
Altrimenti, dove sono fotoni, si può fare uno SWAP utilizzando lenti e specchi.

Notazione:
- i fili possono rappresentare lo scorrere del tempo(quindi un susseguirsi di operazioni sul qubit), qubit statoci.
- i fili possono rappresentare particelle che si propagano, qubit dinamici.
- lo stato iniziale dove non specificato è $\ket{0}$.
- operazioni non permesse: FANOUT(duplicazione di cavi), LOOP, FANIN(cavi che convergono).

**Copiatrice di qubit:**
//TODO: Aggiungere immagine della copiatrice di qubit
Ci verrebbe da utilizzare una CNOT come copratrice di qubit, mettendo in input come controllo il qubit da copiare $\ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ e come target un qubit $\ket{0} = 0\ket{0} + 0\ket{1}$.
Dove nella seconda parte del prodotto tensore, quando misuro la porzione che è 1, questo mi gira il qubit in uno stato $\ket{1}$, che mi da il $\beta\ket{11}$.
L'output è:
$$\ket{\psi} = \alpha\ket{00} + \beta\ket{11} \neq (\alpha\ket{0} + \beta\ket{1}) \otimes (\alpha\ket{0} + \beta\ket{1})$$
(Controllare se effettivamente qui ci vuole il prodotto tensore, e capire perchè la copia sarebbe quella)
Quindi non è possibile copiare un qubit.

**Stati di Bell:**
Sono 4 stati ortogonali che formano una base dello stato di Hilbert a 2 qubit.
//TODO: Aggiungere immagine degli stati di Bell
$$\ket{\Phi^+} = \ket{00} \xrightarrow{H} \frac{\ket{0} + \ket{1}}{\sqrt{2}} \ket{0} \xrightarrow{CNOT} \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) \\ \ket{\Psi^+} = \ket{01} \xrightarrow{H} \frac{\ket{0} - \ket{1}}{\sqrt{2}} \ket{0} \xrightarrow{CNOT} \frac{1}{\sqrt{2}}(\ket{01} + \ket{10}) \\ \ket{\Phi^-} = \ket{10} \xrightarrow{H} \frac{\ket{0} + \ket{1}}{\sqrt{2}} \ket{1} \xrightarrow{CNOT} \frac{1}{\sqrt{2}}(\ket{01} - \ket{10}) \\ \ket{\Psi^-} = \ket{11} \xrightarrow{H} \frac{\ket{0} - \ket{1}}{\sqrt{2}} \ket{1} \xrightarrow{CNOT} \frac{1}{\sqrt{2}}(\ket{00} - \ket{11})$$
(Controllare la fase relativa e globale)
In teoria negli stati $\ket{\Phi}$ la fase è globale, quindi non è misurabile, mentre negli stati $\ket{\Psi}$ la fase è locale, quindi è misurabile. (?)

###4.1 Complessità Quantistica
Dati N qubits ho una base di $2^N$ stati possibili tutti ortogonali tra loro.
$$\ket{\psi} = \sum_{x=0}^{2^N-1} \alpha_x \ket{x}$$
Dove la probabilità di misurare uno stato è $|\alpha_x|^2$.

###4.2 Algoritmo di Deutsch-Josza
Dimostriamo come un algoritmo quantistico può essere più efficiente di un algoritmo classico.

**Costante:** Una funzione è costante se restituisce sempre lo stesso valore per ogni input.
**Bilanciata:** Una funzione è bilanciata se restituisce lo stesso numero di 0 e 1 per ogni input.

**Domanda:** $f$ costante o bilanciata?
Definiamo l'operatore $U_f$:
$$U_f\ket{x}\ket{y} \rightarrow \ket{x}\ket{y \oplus f(x)}$$
Prendiamo $\ket{x}$ che può essere $\ket{0}$ o $\ket{1}$ e $\ket{y} = \frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$.
$$\ket{x}\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}) \xrightarrow{U_f} \ket{x}\frac{1}{\sqrt{2}}(\ket{f(x)} - \ket{1 \oplus f(x)}) = \ket{x}\frac{-1}{\sqrt{2}}^{f(x)}(\ket{0} - \ket{1})$$
Dove $f(x)$ è 0 o 1 e $\frac{-1}{\sqrt{2}}^{f(x)}$ è un fattore di fase globale se $0$ o $1$, relativa se sovrapposto.(?)
Nel caso dove $\ket{x} = \frac{\ket{0} - \ket{1}}{\sqrt{2}}$:
$$\frac{\ket{0} - \ket{1}}{\sqrt{2}}\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}) \xrightarrow{U_f} \frac{\ket{0} - \ket{1}}{\sqrt{2}}\frac{1}{\sqrt{2}}(\ket{f(0)} - \ket{1 \oplus f(0)}) = \frac{\ket{0}(-1)^{f(0)} + \ket{1}(-1)^{f(1)}(\ket{0} - \ket{1})}{2}$$
Ho fattorizzato la sovrapposizione.
Con $f(x)$ costante:
$$\ket{+}\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$$
Con $f(x)$ bilanciata:
$$\ket{-}\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$$
Quindi misurando $\ket{+}$ o $\ket{-}$ posso capire se $f(x)$ è costante o bilanciata.
Dando in pasto alla funzione una sovrapposizione di stati, posso capire se la funzione è costante o bilanciata facendo una sola misurazione.
L'output è quindi la fase relativa data dalla base ${+,-}$.

**Algoritmo di Deutsch:**
Rappresentazione generale su $N$ qubit dell'algoritmo di Deutsch-Josza.
$$U_f\ket{x}\ket{0} \rightarrow \ket{x}\ket{f(x)}$$
Input: $[\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})]^{\otimes N} = \frac{1}{\sqrt{2^N}}\sum_{x=0}^{2^N-1}\ket{x}$
In pratica l'input l'ho dato in pasto a $N$ porte Hadamard.
Applico l'operatore $U_f$:
$$U_f: \rightarrow \frac{1}{\sqrt{2^N}}\sum_{x=0}^{2^N-1}\ket{x}\ket{f(x)}$$

###5.2 Errori Quantistici
Chiamiamo $\epsilon_\tau$ la probabilità di avere un errore in un tempo $\tau$ dove $\epsilon_\tau << 1$.
Guardiamo le probabilità su 3 qubit fisici che vanno a formano 1 qubit logico
Probabilità che ci siamo 0 bit-flip: $(1 - \epsilon_\tau)^3$.
Probabilità che ci sia 1 bit-flip: $3\epsilon_\tau(1 - \epsilon_\tau)^2$.
Probabilità che ci siano 2 bit-flip: $3\epsilon_\tau^2(1 - \epsilon_\tau)$.
Probabilità che ci siano 3 bit-flip: $\epsilon_\tau^3$.
Applico il voto di maggioranza, quindi nelle prime due casistiche non ho errori, mentre nelle ultime due ho un errore.
Probabilità dopo la correzione: $(1 - \epsilon_\tau)^3 + 3\epsilon_\tau(1 - \epsilon_\tau)^2 = 1 - 3\epsilon_\tau^2 + 2\epsilon_\tau^3$.
Probabilità  che un bit rimanga corretto senza correzione: $1 - \epsilon_\tau^3 < 1 - 3\epsilon_\tau^2 + 2\epsilon_\tau^3$.
Da qui capiamo che ha senso fare la correzione
(Controllare la parte seguente che non ci avevo capito molto)

###5.3 Circuito per la correzione
**Problemi principali:**
- no cloning per creare i 3 qubit fisic per quello logico
- misura disturba, non posso misurare quale qubit è flippato
- come applico la maggioranza
- piccoli errori tipo evoluzioni temporali dello stato
- flip di fase, per esempio flip da $\ket{+}$ a $\ket{-}$

**Esempio:**
//TODO: inserire porta
Input: $\alpha\ket{0} + \beta\ket{1}, \ket{0}, \ket{0}$
Output: $\alpha\ket{000} + \beta\ket{111}$
Così ho la codifica di 1 qubit logico su 3 qubit fisici
$$\alpha\ket{000} + \beta\ket{111} \rightarrow (1-\epsilon_\tau)^3 \\ \alpha\ket{100} + \beta\ket{011} \rightarrow \epsilon(1-\epsilon_\tau)^2 \\ \alpha\ket{010} + \beta\ket{101} \rightarrow \epsilon(1-\epsilon_\tau)^2 \\ \alpha\ket{001} + \beta\ket{110} \rightarrow \epsilon(1-\epsilon_\tau)^2 \\ \alpha\ket{110} + \beta\ket{001} \rightarrow \epsilon(1-\epsilon_\tau)^2 \\ \alpha\ket{101} + \beta\ket{010} \rightarrow \epsilon(1-\epsilon_\tau)^2 \\ \alpha\ket{011} + \beta\ket{100} \rightarrow \epsilon(1-\epsilon_\tau)^2 \\ \alpha\ket{111} + \beta\ket{000} \rightarrow \epsilon_\tau^3$$
(ricontrolla che sina queste le probabilità)

