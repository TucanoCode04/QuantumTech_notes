## Teletrasporto Quantistico
Quando si parla di teletrasporto qunatistico si parla di trasferimento dello stato quantistico di un qubit $q_1$ ad un altro qubit $q_3$.

Parliamo di qubit sotto forma di fotoni. L'utilizzo el fotone facilita l'esecuzione di operazioni unitarie su di essi(polarizzazione, proiezione, ecc...). Sono resistenti alle interferenze esterne e possono viaggiare a velocità della luce. 
Mantengono, infatti, la coerenza della loro sovrapposizione di stati per tempi lunghi, questo però li rende meno adatti per la computazione quantistica poichè interagiscono poco.
Il campo elettrico di un'onda elettromagnetica è descritto da:
$$\vec{E}(\vec{r}, t) = E_0 \vec{\epsilon} e^{i(kz - \omega t)} + c.c. \\
= E_0 [\hat{x} \cos \theta e^{i(kz - \omega t)} + \hat{y} \sin \theta e^{i(kz - \omega t + \phi)}] + c.c. \\ = E_0 e^{i(kz - \omega t)} [\hat{x} \cos \theta + \hat{y} \sin \theta e^{i\phi}] + c.c.$$
Dove:
- $\vec{\epsilon}$ è il campo elettrico di un'onda elettromagnetica
- $\vec{r}$ è la posizione
- $t$ è il tempo
- $E_0$ è l'ampiezza del campo elettrico, cioè il massimo valore che può assumere il campo elettrico(è proporzionale all'intensità dell'onda elettromagnetica e quindi alla sua energia, influenza le interazioni dell'onda con la materia)
- $\vec{\epsilon}$ è il vettore di polarizzazione, che descrive la direzione e il verso del campo elettrico
- $k$ è il numero d'onda, cioè quante oscillazioni avvengono per unità di spazio. $k$ è il relazione con la lunghezza d'onda $k = \frac{2\pi}{\lambda}$ e con la frequenza angolare $\omega = vk$ dove $v$ è la velocità(nel vuoto $v = c$)
- $z$ è la direzione di propagazione dell'onda, cioè la direzione in cui l'onda si muove, diversa dalla direzione di oscillazione(che se trasversale è perpendicolare a $z$, se longitudinale è parallela a $z$)
- $\omega$ è la frequenza angolare $\omega = 2\pi f = \frac{2\pi}{T}$, ossia il numero di oscillazioni al secondo in radianti
Abbiamo che:
- $\vec{\epsilon} \perp k\hat{z}$ cioè il campo elettrico è perpendicolare alla direzione di propagazione dell'onda
- se $\theta \neq 0$ le fasi del campo elettrico sono sfasate, questo provoca differenti tipi di polarizzazione
- $\epsilon$ è un vettore complesso di polarizzazione, cioè $\epsilon = \hat{x} \cos \theta + \hat{y} \sin \theta e^{i\phi}$, in uno spazio bidimensionale con base $\{\hat{x}, \hat{y}\} = \{\ket{0},\ket{1}\}$ nello spazio di Hilbert. Quindi $\ket{\vec{\epsilon}} = \cos \theta \ket{0} + \sin \theta e^{i\phi} \ket{1}$
- quindi un campo elettrico che si propaga lungo $z$ può essere descritto con due campi elettrici che si propagano lungo $x$ e $y$ con una fase relativa $\phi$ e una polarizzazione $\theta$, dove se $\theta \rightarrow \theta + \pi$ cambia i segno del vettore di polarizzazione $\vec{\epsilon} = -\vec{\epsilon}$, ma è irrilevante il segno poichè è fase globale quindi teniamo $\theta \in [0, \pi]$
- in meccanica quantistica sostituiamo $E_0$

### Misurazione della polarizzazione
**Polarizzatore:** assorbe fotoni con polarizzazione ortogonale a quella del polarizzatore, lascia passare fotoni con polarizzazione parallela a quella del polarizzatore. Per esempio: assorbe fotoni con polarizzazione $\hat{x}$ e lascia passare fotoni con polarizzazione $\hat{y}$.
Viene utilizzato per misure proiettive dello stato di polarizzazione di un fotone.

Il polarizzatore è un proiettore, per esempio il $\Pi_y$ è il proiettore \ket{1}\bra{1}.
$$\Pi_y \vec{\epsilon} = \ket{1}\braket{1 | \vec{\epsilon}} = \sin \theta e^{i\phi} \ket{1}$$
Questo proiettore non è unitario, non mantiene la norma, dato che perdo metà dell'informazione(la parte di \ket{0}).
La probabilità di attraversare il polarizzatore è data da:
$$P(\Pi_y) =| \braket{\vec{\epsilon} | \Pi_y | \vec{\epsilon}}|^2$$
Secondo la regola di Born(cercare meglio), la probabilità di misurare un certo stato è data dal modulo quadro del prodotto scalare tra lo stato e il proiettore del sistema.

Insieme al polarizzatore si utilizza un rivelatore che fa clic se il fotone passa attraverso il polarizzatore trasformando il fotone in un segnale elettrico(ricercalo).

Misure proiettive = polarizzatore + rivelatore

### Teletrasporto quantistico



