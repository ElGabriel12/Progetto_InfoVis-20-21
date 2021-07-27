# Progetto_InfoVis_20-21
----------------------------
Visualizzazione grafo K-pop
----------------------------
L’obbiettivo principale è stato quello di sodisfare possibili task utente. Ciò tramite due metodi di visualizzazione che permettessero all’utente stesso di visualizzare, nel primo, tutti gli elementi del grafo di tipo person, male, female e group sotto il proprio nodo di tipo label di appartenenza. Nel secondo invece,provando a dare una spiegazione del perché due nodi di tipo “label”sono connessi e quindi se si tratta di una connessione dovuta alla semplice collaborazione tra label, oppure se la connessione è dovuta al fatto che due label“rappresentano” contemporaneamente un nodo del grafo di tipoperson, male, female e group. 

L’idea, quindi, era quella di visualizzare il grafo a partire dai nodi di tipo “label” (campo type = label del file nodes.json) mostrandone i vari collegamenti tra di loro. Nella prima simulazione si vedono infatti tutti i collegamenti tra nodi “label”. Non vengono invece visualizzati quei nodi sempre di tipo “label” che non hanno collegamenti con altri nodi di qualsiasi tipo (group, person, male, female). 

----------------------------
Realizzazione
----------------------------

Per realizzare l’idea abbiamo utilizzato il metodo FORCE DIRECTED per la rappresentazione di grafi ottenendo una visualizzazione a forma di circonferenza. Esso si basa su due forze, una attrattiva e una repulsiva entrambe utilizzate. 

----------------------------
Interazione con il grafo
----------------------------

Dalla prima simulazione è possibile effettuare una serie di interazioni:

1) È stato implementato un menu a tendina che permette la ricerca di un nodo all’interno del grafo. Infatti,scegliendo un nome presente nell’elenco il nodo corrispondente a quel nome cambierà colore (arancione) aumentanoinoltre il suo raggio. Tale scelta è stata fatta per garantire una migliore rappresentazione, evitando la scrittura di testo direttamente nel grafo.

2) Passando con il mouse su un nodo o arco è stata implementata la funzione che permette la visualizzazione di 
nome, type, id nel caso di nodo, oppure il tipo della sorgente e della destinazione nel caso di arco. Aumenta inoltre, per una migliore visualizzazione lo spessore dell’arco o il raggio del nodo sopra il quale si passa con il mouse.

3) Cliccando su un nodo appariranno, in una seconda simulazione basata sempre su Force Directed, i nodi di tipo group, person, male, female collegati al nodo cliccato, più il nodo stesso. Anche in questa simulazione sono implementate le funzioni del punto 1 (dove nel menua tendina sono presenti solo i nodi di tipo group, male, female, person) e 2 ma in questo caso, al passaggio del mouse sopra un eventuale nodo questo cambia l’attributo “stroke” in rosso se non si può interagire con esso, in verde se si può interagire con esso. Inoltre, solo se il colore dello stroke è verde il raggio del nodo cambia dimensione. Una volta cliccato il nodo con cui si può eventualmente interagire si viene reindirizzati alla rappresentazione iniziale dei nodi di tipo “label” nella quale però verrà evidenziato, con colore diverso (arancione) e raggio del cerchio aumentato, l’ultimo nodo che è stato visualizzato. Tale scelta è stata implementata per migliorare la navigazione, e per lasciare una traccia dell’ultima azione effettuata per poterla eventualmente replicare.

4) Cliccando su un arco tra due nodi invece, compare, in un’ulteriore simulazione, una visualizzazione che permette di riconoscere il tipo di collegamento che lega due nodi di tipo “label”. In questa simulazione sono implementate solamente le funzioni del punto 2 dove in questo caso, al passaggio del mouse sopra un eventuale arco, esso cambia colore in verde solo quando è possibile interagirci, altrimenti rimane invariato. Una volta cliccato l’arco con cui si può eventualmente interagire si viene reindirizzati alla rappresentazione iniziale dei nodi di tipo “label” nella quale però verrà evidenziato, con colore diverso (rosso) e spessore dell’arco aumentato, l’ultimo arco che è stato visualizzato. Tale scelta è stata implementata per migliorare la navigazione, e per lasciare una traccia dell’ultima azione effettuata per poterla eventualmente replicare.

--------------------------
Codifica Colori
--------------------------

La codifica dei colori utilizza diverse scale di colore fornite da d3.js ed è la seguente:

•Arco grigio e nodi verdi per la rappresentazione iniziale delle etichette.

•Arco rosa e nodo rosa se il collegamento coinvolge un nodo di tipo “female”. 

•Arco blu e nodo blu se il collegamento coinvolge un nodo di tipo “male”. 

•Arco grigio e nodo grigio se il collegamento coinvolge un nodo di tipo “person”. 

•Arco grigio e nodo rosso se il collegamento coinvolge un nodo di tipo “group”.

--------------------------
Esempio di Riproducibilità
--------------------------
1) Selezionare nel menu a tendina in basso a sinistra il nome del nodo di tipo label "LOEN Entertainment". Il nodo cambiera colore e diametro.
2) Cliccando sul nodo è possibile vedere una rappresentazione dei nodi ad esso collegati. Tornando alla rappresentazione iniziale (cliccando sul nodo di tipo "label", l'unico nella rappresentazione) il nodo rimarra con "illuminato" per indicarci che veniamo da li.
3) Selezionare nel menu a tendina in basso a sinistra il nome del nodo di tipo label "Music&New". Il nodo cambiera colore e diametro.
4) Ripetere il passo 3 nel caso specifico del nodo "Music&New"
5) Cliccare infine sull'arco che collega i due nodi. Comparirà una rappresentazione che mostra le relazioni che legano i due nodi di tipo "label"
--------------------------
Note
--------------------------
I Dataset iniziali sono stati trasformati dal formato CSV al formato JSON e infine unificati in un unico file, per essere gestiti in modo più semplice.
