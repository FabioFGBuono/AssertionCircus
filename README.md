# 🎪 ***Il Circo Delle Asserzioni Fantastiche***
![Assert al Dente](https://img.shields.io/badge/Assert_al_Dente-🍝-f7f7f7)
![Assert Ninja](https://img.shields.io/badge/Assert_Ninja-🥷-purple)
[![Circus Certified](https://img.shields.io/badge/circus-certified-yellow)](ca://s?q=circus_certified)
[![Probabilistic Stability](https://img.shields.io/badge/probability-unstable-purple)](ca://s?q=probabilistic_stability)


***"Specifica formale per chi non ha tempo e fenomeni nascosti di compilazione***

Lo sapevate che le assert hanno effetti collaterali anche quando spariscono? Probabilmente no, questo e altro vi attende, **_"venghino signori venghino"_** il circo delle asserzioni fantastiche vi attende.

----
[![License: CC BY-NC-ND + Translation OK](https://img.shields.io/badge/license-CC_BY--NC--ND_%2B_translation--ok-blueviolet)](https://creativecommons.org/licenses/by-nc-nd/4.0/)



**Attenzione: Questo testo è in fase di stesura e questa è solo una bozza, molti argomenti sono da finire e ricollocare. E' già abbastanza sensato da essere letto ma non aspettatevi una cosa perfetta**

## Introduzione

Bungiorno a voi viandanti, lasciate che mi sistemi il cappello, quello largo e un po' storto che ha visto più tempeste di quanto un compilatore possa sopportare, e che mi metta al centro della polverosa pista, sotto questo tendone che cigola come un vecchio server sotto stress, perché è arrivato il momento di accogliere chi sta per leggere queste pagine, e farlo con la voce roca e teatrale di un presentatore del West che ha passato la vita a introdurre numeri che nessuno avrebbe mai dovuto provare, numeri che sfidano la logica, il buon senso e a volte pure la fisica e perfino la decenza, proprio come fanno le **assert** quando decidono di comportarsi da protagoniste.

Signore e signori, accomodatevi pure sulle panche traballanti, non fate caso ai chiodi sporgenti né al fatto che la segatura sul pavimento sembra muoversi da sola, perché ciò che state per vedere non è uno spettacolo qualunque, e non è nemmeno uno di quei numeri eleganti e ben provati che si vedono nei circhi civilizzati, no no, noi qui siamo nel selvaggio West del software, dove le assert entrano in scena come pistoleri nervosi, sparano condizioni che credono infallibili e poi, quando qualcuno le toglie, continuano a far tremare l'aria come se fossero ancora lì, come se la loro ombra fosse più pesante della loro presenza, e voi penserete che sia un trucco, un'illusione, un gioco di prestigio, ma vi assicuro che non c'è niente di più reale di un effetto collaterale che sopravvive alla sua stessa rimozione. Prendete quindi posto, e mentre vi sistemate il cappotto e cercate di capire se il vento che sentite è reale o solo un algoritmo probabilistico che ha perso la bussola, lasciate che vi presenti il secondo numero della serata. Quello in cui un povero algoritmo, entra in scena con la dignità di un cavallo da tiro con la speranza di fare il suo lavoro senza incidenti, ma dietro di lui, in penombra, c'è un'assert vestita da illusionist che gli sussurra qualcosa all'orecchio, qualcosa che cambia la sua distribuzione come un colpo di vento cambia la traiettoria di un cappello, e l'algoritmo inciampa e sbanda e così produce risultati che sembrano usciti da un saloon dopo tre whisky di troppo, e voi ridete, certo che ridete, perché è buffo, ma sotto sotto sentite che c'è qualcosa di inquietantemente sbagliato, come quando un cavallo decide di salire sul palco e nessuno ricorda di averlo addestrato.

E non crediate che il peggio sia passato, perché nel nostro circo il peggio arriva sempre quando meno te lo aspetti, come quando entra in scena il clown dei sistemi critici, quello con il naso rosso e la responsabilità di un reattore nucleare, quello che dovrebbe essere prudente come un vecchio sceriffo e invece inciampa, ride, apre una scatola e ne tira fuori un'assert che non dovrebbe nemmeno esistere in quel contesto, e voi trattenete il fiato, e io pure, perché questo numero non è comico e fa paura, e proprio per questo il clown sorride ancora di più, perché nel nostro circo la paura è parte del biglietto, e chi entra deve sapere che qui le assert non sono mai innocue, nemmeno quando sembrano addormentate. E così, mentre il vento del deserto soffia tra le assi del tendone e la luce tremolante delle lampade a olio illumina la pista, io vi dico che questo libro non è un manuale, non è una guida, non è un sermone e non è neanche un libro in realtà, ma è un viaggio dentro un mondo in cui le assert sono personaggi dispettosi che attraversano il software come cavalli selvaggi attraversano la prateria, lasciando impronte che nessuno riesce a cancellare, e voi siete qui per osservarle con la consapevolezza che nel circo delle asserzioni fantastiche nulla è davvero sotto controllo, e che per questo vale la pena restare fino all'ultimo numero.

## Semantica in pratica 

E ora che siete comodi, iniziamo a spiegare che un assert è un controllo interno che verifica una condizione che il programmatore considera sempre vera in un determinato punto del programma. Se la condizione è soddisfatta, l'esecuzione procede normalmente, se invece la condizione è falsa, il runtime segnala il problema con meccanismi specifici del linguaggio. In pratica significa che stiamo scrivendo, dentro il codice, una condizione che serve a verificare che il codice stesso si comporti come avevamo immaginato quando, e soprattutto se, lo abbiamo progettato... Se volessimo dirlo in modo colto, potremmo dire che le assert permettono di individuare errori logici nel punto in cui si manifestano, riducendo la distanza tra la causa del problema e il suo effetto. Si scrivono più o meno così: `assert(condizione)`. Una condizione come `assert(x > 0)` fornisce al runtime un criterio per verificare se ciò che abbiamo progettato è stato rispettato. Quando un'assert fallisce, il problema è quasi sempre dovuto a un errore nella logica del codice. Inoltre, l'uso delle assert facilita anche l'adozione di strumenti di specifica formale, perché molte proprietà espresse in linguaggi specifici sono concettualmente equivalenti alle condizioni che si scrivono nelle assert, solo con un livello di rigore maggiore.

Quindi, a prima vista, sembrerebbe che le assert vadano bene ovunque, come il sale, ma non è così e non devono essere utilizzate per gestire condizioni derivanti dall'ambiente esterno o dall'input dell'utente. Servono esclusivamente a verificare proprietà interne del programma e non devono essere usate neanche per la sicurezza, perché molti linguaggi le disattivano in modalità ottimizzata. Infine va chiarito che le assert non sostituiscono i test perché questi verificano scenari completi dall'esterno, mentre le assert verificano proprietà locali durante l'esecuzione del codice reale. Quando un'assert fallisce, ciò che accade dopo è linguaggio/modello dipendente, e quindi non è possibile dare un criterio generale su come progettare il codice intorno alle assert, ma la teoria ci viene incontro e, per iniziare a farci le ossa, possiamo guardare a qualche caso concreto.

Iniziamo con Python, qui `assert cond, msg` viene trasformata dal compilatore in un controllo su `__debug__`, una costante booleana che vale `True` normalmente e `False` quando l'interprete è avviato con `-O`. In modalità ottimizzata, il bytecode dell'assert non viene generato e il costo a runtime è nullo. Se l'assert fallisce viene sollevata un'eccezione `AssertionError`, che può essere catturata come qualsiasi altra eccezione, anche se farlo è considerato un antipattern.

In C/C++ invece la macro `assert` definita in `<assert.h>` viene espansa dal preprocessore e, se `NDEBUG` è definito, la macro viene sostituita da un'istruzione vuota; altrimenti, se la condizione è falsa, viene chiamata `__assert_fail`, che stampa un messaggio diagnostico su `stderr` e invoca `abort()`, terminando il processo con `SIGABRT`. In modalità ottimizzata, il codice dell'assert viene completamente rimosso prima della compilazione.

```c
#ifdef NDEBUG
#define assert(cond) ((void)0)
#else
#define assert(cond)  \
    ((cond) ? (void)0 : __assert_fail(#cond, __FILE__, __LINE__, __func__))
#endif
```

Se guardiamo a Java, la keyword `assert` è disabilitata per default e deve essere attivata esplicitamente con il flag `-ea`. Se un'assert fallisce, viene lanciato un `AssertionError`, che è una sottoclasse di `Error` e non di `Exception`, scelta progettuale che scoraggia la cattura. La JVM ottimizza le assert disabilitate eliminando il ramo di controllo corrispondente. JavaScript invece non ha una keyword dedicata e i vari ambienti forniscono meccanismi diversi, come `console.assert()` nei browser o il modulo `assert` in Node.js. Non esiste un meccanismo standard per rimuovere le assert in produzione, quindi il loro comportamento dipende dall'ambiente. Il suo cugino TypeScript, a differenza di JS, introduce le *assertion functions*: queste hanno effetto solo sul type checker e non sul runtime, dove invece vale il comportamento JavaScript.

Poi c'è Rust, qui le macro `assert!`, `assert_eq!` e `assert_ne!` restano attive anche in release, mentre le macro `debug_assert!` e varianti vengono invece rimosse in compilazione quando si usa il profilo di release. Un fallimento provoca un `panic!`, che per default esegue l'unwind dello stack e configurando `panic = "abort"` nel `Cargo.toml`, il processo termina senza unwind.

Infine, in Go non esiste una keyword `assert` e per ottenere un comportamento analogo si usano controlli espliciti e `panic()` per segnalare condizioni impossibili. Un `panic` esegue i `defer` e termina la goroutine corrente e, se non viene recuperato, termina l'intero processo.

## Il contratto come vocabolario minimo

Per affrontare meglio questo testo dobbiamo avere un vocabolario base di termini comuni, le parole da tenere a mente sono **precondizione**, **postcondizione**, **invariante**, **guardia**, **funzione di terminazione**. Ognuna corrisponde a un'assert, e tenerle distinte ti farà scrivere meglio sia le assert sia il codice intorno alle assert. Una funzione è un contratto fra due parti, chi la chiama e chi la implementa. Chi chiama promette qualcosa in ingresso, le precondizioni e chi implementa promette qualcosa in uscita, le postcondizioni. Mentre la funzione lavora, certe proprietà, le invarianti, restano vere a ogni momento. Dentro ogni ciclo c'è una guardia che decide se proseguire, e una funzione di terminazione che garantisce che il ciclo prima o poi cessa di esistere o almeno ci dovrebbe essere e certe volte ancora c'è ma non garantisce nulla.

Ora vediamo come questi termini si mappano in un vocabolario più pratico, ma prima notiamo che questa terminologia che stai per imparare ha un'origine e un padre nobile, Bertrand Meyer, un informatico francese che nei primi anni ottanta creò un linguaggio chiamato **Eiffel** (non per niente era francese) e una metodologia che battezzò *Design by Contract*. Il libro fondativo a riguardo si chiama, *Object-Oriented Software Construction* (1988), e fissa il vocabolario per come lo usiamo oggi:

- **require** per la precondizione,
- **ensure** per la postcondizione,
- **invariant** per l'invariante di classe,
- **variant** per la funzione di terminazione,
- **check** per le assert spot.

In Eiffel queste parole sono costrutti del linguaggio, mica commenti. Una classe scritta come si deve recita una cosa di questo tipo,

```eiffel
class ACCOUNT
feature
    saldo: INTEGER

    preleva (importo: INTEGER) is
        require
            importo_positivo: importo > 0
            saldo_sufficiente: importo <= saldo
        do
            saldo := saldo - importo
        ensure
            saldo_aggiornato: saldo = old saldo - importo
        end

invariant
    saldo_non_negativo: saldo >= 0
end
```

L'idea di Meyer era che il contratto fosse parte integrante della firma di un metodo, verificabile a runtime e oggetto di controlli statici parziali, e pure ereditabile. Una sottoclasse che rinforza una precondizione viola il principio di sostituzione di Liskov che citando wikipedia afferma che ogni sottoclasse deve poter sostituire la sua superclasse senza alterare la correttezza del programma. In altre parole, se un codice funziona con un oggetto di tipo T, deve continuare a funzionare anche se gli passi un oggetto di tipo S, dove S è un sottotipo di T. E una sottoclasse che indebolisce una postcondizione lo viola pure, e Eiffel sa rifiutare la cosa al compilatore.

Indebolire una postcondizione viola LSP perché la postcondizione descrive ciò che il metodo garantisce dopo l'esecuzione, se la superclasse T garantisce un insieme di risultati R, e la sottoclasse S garantisce solo un sottoinsieme Q, con Q ⊂ R, allora un client che si aspetta la garanzia di T potrebbe ricevere un risultato che non soddisfa le sue aspettative. Per questo Meyer stabilisce che le postcondizioni possono solo essere rafforzate nelle sottoclassi.

Eiffel è l'unico linguaggio mainstream che usa davvero il Design by Contract come parte del sistema di tipi. E infatti rifiuta una sottoclasse che rafforza una precondizione, che indebolisce una postcondizione e propaga invarianti e contratti lungo la gerarchia. E infatti verifica i contratti anche a runtime.

> "L'ereditarietà deve essere un meccanismo di specializzazione, non di restrizione".

Oggi, per esempio, JML (Java Modeling Language) ha portato i contratti su Java con `@requires`, `@ensures`, `@invariant`, Spec# di Microsoft Research ha tentato la stessa cosa su C#. Code Contracts in .NET ha avuto qualche anno di gloria e poi è stato deprecato. Dafny, sviluppato sempre in Microsoft Research, ha alzato l'asticella alla verifica statica. Frama-C porta i contratti in ANSI/ISO C con il linguaggio ACSL. SPARK, dialetto di Ada, fa verifica formale industriale. Python ha avuto vari tentativi di libreria (icontract, dpcontracts). Clojure ha `:pre` e `:post`. E Racket ha `define/contract` di scuola PLT, con runtime check raffinati e blame assignment. Le assert che usi ogni giorno sono la versione *low-budget* dei contratti di Meyer, hanno lo stesso vocabolario e stessa semantica, ma non supporto del linguaggio, e nessuna verifica formale a contorno.

## Precondizione

Ma stiamo correndo troppo, andiamo a vedere meglio i singoli termini del nostro vocabolario.

> Un precondizione è Ciò che deve essere vero perché abbia senso chiamare la funzione.

Una precondizione è una dichiarazione formale che specifica quali condizioni devono essere soddisfatte prima dell'invocazione di una funzione affinché la sua esecuzione sia logicamente definita e semanticamente corretta. Cioè ci dice cosa deve accadere al mondo nel momento prima che faciamo qualcosa, come in cucina, non puoi condire la pasta se prima non l'hai cotta, e l'essere già cotta è la precondizione, ma volendo puoi mettere anche il sugo sulla parta cruda solo che così il piatto non funziona, quindi una precondizione stabilisce quali valori di input e quali stati del programma costituiscono un dominio valido per l'operazione che la funzione intende svolgere, chiarendo che qualsiasi violazione di tali condizioni rappresenta un errore imputabile al chiamante, il quale ha utilizzato la funzione in un contesto che non rientra nelle ipotesi operative previste dall'implementatore. Le precondizioni quindi non descrivono ciò che la funzione *farà*, ma ciò che deve essere già vero affinché la funzione possa iniziare a lavorare in modo sensato.

```
funzione radice_quadrata(x):
    PRECONDIZIONE: x >= 0
    assert x >= 0
    ...
```

Invocare `radice_quadrata(-9)` mettere il sugo sulla pasta cruda ma avere la pasta cotta prima di condirla è un requisito fondamentale del contratto, poiché la funzione non ha mai dichiarato di essere in grado di gestire numeri negativi, e l'assert iniziale serve proprio a rilevare questo problema. E le precondizioni sono proprio quello che fa un'assert messa all'inizio della funzione e quindi applicata ai parametri o allo stato globale che la funzione assume valido.


## Il frigorifero che insegnò le precondizioni

Negli anni '70, nel laboratorio Xerox PARC, dove nascevano concetti rivoluzionari come l'interfaccia grafica e il mouse, c'era un frigorifero condiviso da tutti i ricercatori. Un giorno iniziarono a verificarsi misteriosi “furti di yogurt”, qualcuno apriva il frigo, prendeva un vasetto, lo richiudeva... e il giorno dopo il vasetto era sparito. Per settimane nessuno riuscì a capire chi fosse il colpevole. Finché un ricercatore, esasperato, decise di installare un sensore che registrava ogni apertura e chiusura, con un timestamp. Una primitiva precodizione per cui "la porta deve essere chiusa per poter registrare un'apertura".

Ma il sensore non registrava nulla come se il frigo non venisse mai aperto.

Dopo giorni di debugging, scoprirono che il sensore era stato montato sulla porta sbagliata, infatti il frigorifero aveva due ante, e tutti aprivano sempre l'altra. La precondizione £la porta monitorata è quella che viene aperta£ non era soddisfatta, il sistema funzionava perfettamente ma nel mondo sbagliato. Da allora, nel laboratorio, quando qualcuno progettava una funzione senza pensare alle precondizioni, gli altri gli dicevano ridendo "Stai mettendo il sensore sulla porta sbagliata del frigo". Non so se questa sia vera o una storia inventata da un vecchio amico che me l'ha riportata ma di fatto rende l'idea.

## Postcondizione

Prima di parlare di ciò che una funzione richiede per poter iniziare a lavorare, è altrettanto importante chiarire ciò che essa garantisce una volta terminata. Se le precondizioni definiscono il punto di partenza, le postcondizioni rappresentano l'impegno formale che la funzione assume nei confronti del chiamante. Sono la promessa sul risultato finale e sullo stato del mondo dopo l'esecuzione, la dichiarazione di ciò che sarà vero quando la funzione avrà finito di fare il suo lavoro, sempre che le condizioni iniziali fossero quelle giuste.

> Ciò che l'implementatore promette al chiamante sarà vero al ritorno della funzione.

Una postcondizione quindi invece è una dichiarazione che specifica quali proprietà devono essere vere al termine dell'esecuzione della funzione, ma solo a condizione che la precondizione precedente sia stata rispettata. Come dire che la pasta prima di essere servita deve essere cotta e condita, questo è l'impegno del ristoratore nei confronti del cliente e definisce quali caratteristiche deve possedere il risultato e quale stato deve essere garantito al momento del ritorno. Se la postcondizione viene violata la funzione non ha mantenuto la promessa dichiarata e contiene un errore logico interno, indipendente dal comportamento del cliente, pardon del chiamante.

```
funzione radice_quadrata(x):
    PRECONDIZIONE: x >= 0
    POSTCONDIZIONE: il risultato r soddisfa r*r ≈ x e r >= 0
    ...
    assert r >= 0 && abs(r*r - x) < epsilon
    ritorna r
```

Se la precondizione è rispettata ma la postcondizione fallisce, la responsabilità è del codice, poiché la funzione non ha prodotto un risultato coerente con la specifica dichiarata.

## Invariante

> Una proprietà che resta vera in ogni momento in cui ha senso osservarla.

Un invariante è una proprietà che deve rimanere valida in tutti i punti rilevanti dell'esecuzione di una struttura dati o di un algoritmo, come il fatto che la cucina e le mani del cuoco devono sempre essere pulite quando cucina, queste sono un elemento essenziale per ragionare sulla correttezza, se le mani sono sporche i clienti tornano a casa con una intossicazione alimentare. Gli invarianti permettono di descrivere lo stato corretto di un oggetto o di un ciclo, e rappresentano uno strumento fondamentale per dimostrare che un algoritmo procede in modo coerente verso il risultato desiderato.

### Invariante di rappresentazione (o di classe)

L'invariante di rappresentazione definisce le proprietà che devono essere vere per ogni istanza di una struttura dati in tutti gli stati osservabili dall'esterno. Questa descrive le condizioni che caratterizzano una rappresentazione valida dell'oggetto e che devono essere mantenute da tutti i metodi pubblici e privati che manipolano tale oggetto. Per capirci, se prendiamo una lista linkata che mantiene un campo `length` allora il nostro invariante richiederà che `length` coincida con il numero effettivo di nodi raggiungibili dalla testa.

```
classe Stack:
    INVARIANTE: 0 <= size <= capacity
    INVARIANTE: buffer punta a un'allocazione valida di lunghezza capacity
```

### Invariante di ciclo

L'invariante di ciclo è una proprietà che deve essere vera prima dell'ingresso nel ciclo, dopo ogni iterazione e all'uscita. E' la specifica di cosa il ciclo sta mantenendo progressivamente e costituisce la base per dimostrare la correttezza dell'algoritmo iterativo poiché permette di verificare che ogni passo dell'algoritmo preservi una condizione che, una volta combinata con la terminazione, garantisce il risultato finale.

```
funzione somma(arr, n):
    i = 0
    s = 0
    mentre i < n:
        INVARIANTE: s == somma di arr[0..i-1] && 0 <= i <= n
        s = s + arr[i]
        i = i + 1
    // all'uscita i == n, quindi s == somma di arr[0..n-1]
    ritorna s
```

---

## Guardia

> La condizione che decide se proseguire un ciclo o entrare in un ramo.

La guardia è... While True... ecco True è una guardia sempre vera e detto in modo più da accademia, è la condizione che determina se un ciclo deve continuare o se un ramo condizionale deve essere eseguito. Quindi rappresenta il meccanismo che controlla il flusso di esecuzione del programma. E' importante distinguere la guardia dall'invariante, poiché la guardia stabilisce *quando* il codice deve essere eseguito, mentre l'invariante stabilisce *quali proprietà devono essere mantenute* indipendentemente dal flusso. Confondere i due concetti può portare a errori difficili da individuare, come terminazioni premature o assert ridondanti che verificano condizioni già garantite dalla guardia.

```
mentre inizio <= fine:   // GUARDIA
    INVARIANTE: 0 <= inizio && fine < len(arr)
    ...
```


## Funzione di terminazione

> Una quantità che dimininuisce in senso stretto a ogni iterazione, e che ha un limite inferiore, a garantire che il ciclo arriva alla fine in un tempo finito.

La funzione di terminazione è una misura che diminuisce strettamente a ogni iterazione e che possiede un limite inferiore, garantendo così che il ciclo o la ricorsione termineranno in un numero finito di passi. Per la ricerca binaria, ad esempio, la funzione di terminazione è `fine - inizio + 1`, cioè il numero di elementi residui, per un ciclo `for i = 0 to n`, è `n - i`; per una ricorsione, è la dimensione del sottoproblema. A volte la funzione di terminazione viene verificata tramite un'assert, salvando il valore precedente e controllando che quello nuovo sia strettamente minore. Più spesso è annotata come commento, per documentare il ragionamento e facilitare la comprensione del codice.

```
prev_misura = fine - inizio
... corpo dell'iterazione ...
assert (fine - inizio) < prev_misura
```


# Le regole di allocazione "topologica"

Un'assert è appropriata quando verifica una condizione la cui violazione produrrebbe un errore difficile da individuare attraverso il normale debugging, perché la deviazione dal comportamento atteso potrebbe propagarsi in modo silenzioso e manifestarsi solo molto più avanti nell'esecuzione. In questi casi, l'assert fornisce un punto di osservazione privilegiato che permette di rilevare immediatamente la deviazione. Al contrario, quando la condizione è ovvia o già garantita dal linguaggio, dal tipo o dalla struttura del codice, l'assert introduce rumore senza apportare valore.

Ma non serve verificare proprietà che il linguaggio o il sistema di tipi garantiscono già, per capirci scrivere `assert(x == a + b)` subito dopo `x = a + b` significa controllare un'operazione elementare che il compilatore implementa correttamente. Ad esempio in Rust, un parametro `&str` è sempre un riferimento valido a una stringa UTF‑8 e in Java, un parametro annotato `@NonNull` è già coperto dagli strumenti di analisi. Ripetere questi controlli a runtime non migliora la robustezza del codice. E anche nelle funzioni private chiamate da pochi punti controllati, le assert possono essere superflue.

## Dove mettercele?

Elenchiamo quattro posti dove generalmente ma non in generale (è diverso anche se sembra la stessa cosa) conviene metterle:

1) **Confini tra moduli**: mettile dove passa codice non controllato dalla tua base (API interne, plugin, librerie esterne).

2) **Rami impossibili**: Switch esaustivi, default che non dovrebbero mai attivarsi, casi residui dopo aver coperto tutte le alternative. Qui costrutti come `assert(false)`, `unreachable!()` o `throw new AssertionError("ramo impossibile")` rendono immediatamente visibile un errore logico.

3) **Postcondizioni non ovvie**: Quando il risultato deve rispettare una proprietà importante non evidente dalla firma della funzione, un'assert prima del `return` documenta e verifica l'assunzione.

4) **Invarianti complessi su strutture dati**: Strutture come alberi bilanciati, code prioritarie, grafi con vincoli o union‑find con compressione del cammino traggono beneficio da controlli interni. Un metodo `check_rep()` invocato nei punti critici può evitare lunghi debug.

5) **Punti di ragionamento delicato**: Ricerca binaria, manipolazioni bit‑wise, aritmetica modulare, gestione di indici al limite, parsing carattere per carattere, e in generale in algoritmi con indici, bit‑tricks, parsing, ecc. l'assert accelera il debug. In questi casi un'assert ben posizionata riduce drasticamente il tempo di diagnosi.

E counque per una funzione di venti o trenta righe con logica reale e non banale, da una a quattro assert, se il codice è criptico, va bene ma se il numero cresce troppo, è probabile che si stiano verificando ovvietà. Ricordate che ogni assert dovrebbe essere accompagnata da un commento breve che spiega perché la condizione è importante oppure dovrebbe essere autoesplicativa.


## La regola in una riga

> Asserisci ciò che richiederebbe una spiegazione articolata in una code review.  
> Se la risposta sarebbe immediata e ovvia, l'assert non serve.


## Un contratto per questo documento

Per evitare che ogni capitolo debba introdurre esempi nuovi utilizzeremo tre funzioni di riferimento che verranno riprese in tutti i linguaggi e che verranno progressivamente arricchite man mano che la discussione si sposterà da un livello astratto a un livello più concreto.

### Esempio A, `media`

```
funzione media(numeri):
    assert len(numeri) > 0       // precondizione

    somma = 0
    per ogni n in numeri:
        somma = somma + n

    risultato = somma / len(numeri)

    assert risultato >= min(numeri) && risultato <= max(numeri)
                                  // postcondizione

    ritorna risultato
```

La funzione calcola la media aritmetica e verifica che il valore ottenuto sia compreso tra il minimo e il massimo degli elementi, proprietà che deriva direttamente dalla definizione di media e che costituisce un controllo utile per rilevare errori di implementazione.

### Esempio B, `ricerca_binaria`

```
funzione ricerca_binaria(arr, target):
    assert è_ordinato(arr)        // precondizione costosa, debug-only

    inizio = 0
    fine = len(arr) - 1
    mentre inizio <= fine:
        assert 0 <= inizio && fine < len(arr)
                                   // invariante di ciclo

        medio = inizio + (fine - inizio) / 2
        se arr[medio] == target: ritorna medio
        altrimenti se arr[medio] < target: inizio = medio + 1
        altrimenti: fine = medio - 1

    ritorna -1
```

Questo secondo esempio introduce un algoritmo più articolato, che richiede un invariante di ciclo per garantire che gli indici rimangano sempre all'interno dei limiti dell'array e che la ricerca proceda in modo corretto. La precondizione che richiede l'ordinamento dell'array è costosa e quindi tipicamente attivata solo in modalità di debug, ma è fondamentale per assicurare che l'algoritmo sia applicato nel dominio corretto.


### Esempio C, `trasferisci`

```
funzione trasferisci(conto_a, conto_b, importo):
    assert importo > 0
    assert conto_a.saldo >= importo

    totale_prima = conto_a.saldo + conto_b.saldo

    conto_a.saldo = conto_a.saldo - importo
    conto_b.saldo = conto_b.saldo + importo

    assert conto_a.saldo + conto_b.saldo == totale_prima
                                  // conservazione del denaro
```

Qui invece si introduce un caso in cui la proprietà da verificare non riguarda solo il valore di ritorno, ma una relazione tra lo stato iniziale e lo stato finale del sistema. La conservazione del totale è una proprietà fondamentale nei sistemi finanziari e rappresenta un caso tipico in cui un'assert permette di rilevare immediatamente errori di implementazione che potrebbero altrimenti manifestarsi solo in condizioni rare o difficili da riprodurre.

Ora che abbiamo stabilito un vocabolario comune e e il nostro contratto di riferimento, possiamo osservare come gli stessi concetti si traducano nei diversi linguaggi, iniziando da Python, che offre un modello di assert semplice ma con alcune caratteristiche peculiari che influenzano il modo in cui devono essere utilizzate.

**Nota: Non ho ancora terminato di scrivere questo testo è il contratto appena definito non è rispettato in tutto il testo**


## Python  

Abbiamo già accennato che l'istruzione `assert` permette di esprimere una condizione che deve essere verificata a runtime, e che in caso di violazione genera un'eccezione di tipo `AssertionError`. La sintassi `assert cond, "messaggio"` è concisa, ma è importante comprendere che l'interprete rimuove completamente tutte le assert quando viene eseguito con il flag `-O`, il quale attiva la modalità ottimizzata. Quindi qualsiasi logica essenziale non deve mai essere collocata all'interno di un'assert, poiché verrebbe eliminata dal bytecode, compromettendo la correttezza del programma.

```python
# Esempio A: media
def media(numeri):
    assert len(numeri) > 0, "lista vuota"

    risultato = sum(numeri) / len(numeri)

    assert min(numeri) <= risultato <= max(numeri), \
        f"media {risultato} fuori dal range [{min(numeri)}, {max(numeri)}]"

    return risultato
```

L'esempio mostra come una precondizione semplice e una postcondizione matematica possano essere espresse in modo diretto, mantenendo leggibilità e coerenza con la semantica del linguaggio.


```python
# Esempio B: ricerca binaria
def ricerca_binaria(arr, target, debug=False):
    if debug:
        assert all(arr[i] <= arr[i+1] for i in range(len(arr)-1)), \
            "array fuori ordine"

    inizio, fine = 0, len(arr) - 1
    while inizio <= fine:
        assert 0 <= inizio and fine < len(arr)
        medio = inizio + (fine - inizio) // 2
        if arr[medio] == target:
            return medio
        elif arr[medio] < target:
            inizio = medio + 1
        else:
            fine = medio - 1
    return -1
```

Qui l'assert viene utilizzata per verificare un invariante di ciclo che garantisce la correttezza degli indici, mentre la precondizione costosa viene attivata solo in modalità di debug, evitando di danneggiare le prestazioni in produzione.


```python
# Esempio C: trasferimento
def trasferisci(conto_a, conto_b, importo):
    assert importo > 0
    assert conto_a.saldo >= importo

    totale_prima = conto_a.saldo + conto_b.saldo
    conto_a.saldo -= importo
    conto_b.saldo += importo

    assert conto_a.saldo + conto_b.saldo == totale_prima
```

Quello sopra mostra come un'assert possa essere utilizzata per verificare una proprietà di conservazione che coinvolge più variabili e che rappresenta un requisito fondamentale per la correttezza del sistema.

### Pythonismi utili  

In Python è spesso utile racchiudere assert costose all'interno di un blocco `if __debug__:` poiché questa variabile booleana è impostata automaticamente dall'interprete e permette di includere o escludere interi blocchi di codice in base alla modalità di esecuzione. Questo approccio consente di mantenere controlli approfonditi durante lo sviluppo senza introdurre costi inutili in produzione.

```python
if __debug__:
    assert proprietà_costosa(struttura)
```

Per quanto riguarda la validazione dell'input proveniente dall'esterno del programma, è preferibile utilizzare eccezioni esplicite come `ValueError`, sempre per lo stesso motico che le assert non devono essere utilizzate per gestire errori che dipendono dall'ambiente o dall'utente. Un errore comune consiste nell'utilizzare parentesi in modo improprio, generando una tupla che risulta sempre vera e che quindi rende l'assert inefficace:

```python
assert (x > 0, "x deve essere positivo")   # tupla sempre vera
assert x > 0, "x deve essere positivo"     # forma giusta
```

### Un buffer circolare  

Ora vediamo una coda circolare a capacità fissa, che richiede un invariante di rappresentazione articolata e una funzione di verifica interna. Questo caso permette di osservare come le assert possano essere utilizzate per garantire la coerenza interna della struttura dati in tutti i punti critici della sua manipolazione.

```python
class BufferCircolare:
    """
    Coda FIFO a capacità fissa.
    Invariante di rappresentazione:
        - 0 <= self._size <= self._cap
        - 0 <= self._head < self._cap
        - 0 <= self._tail < self._cap
        - se _size == 0, self._head == self._tail
        - se _size == _cap, self._head == self._tail
        - len(self._buf) == self._cap
    """

    def __init__(self, capacità):
        if capacità <= 0:
            raise ValueError("capacità deve essere positiva")
        self._cap = capacità
        self._buf = [None] * capacità
        self._head = 0
        self._tail = 0
        self._size = 0
        self._check_rep()

    def _check_rep(self):
        # Chiamata di servizio interna, costa O(1).
        # Usiamo assert perché un fallimento qui è un bug del modulo.
        assert 0 <= self._size <= self._cap
        assert 0 <= self._head < self._cap
        assert 0 <= self._tail < self._cap
        assert len(self._buf) == self._cap
        if self._size == 0 or self._size == self._cap:
            assert self._head == self._tail

    def push(self, x):
        if self._size == self._cap:
            raise OverflowError("buffer pieno")
        self._buf[self._tail] = x
        self._tail = (self._tail + 1) % self._cap
        self._size += 1
        self._check_rep()

    def pop(self):
        if self._size == 0:
            raise IndexError("buffer vuoto")
        x = self._buf[self._head]
        self._buf[self._head] = None
        self._head = (self._head + 1) % self._cap
        self._size -= 1
        self._check_rep()
        return x

    def __len__(self):
        return self._size
```

In questo esempio la distinzione tra gli errori che devono essere gestiti dal chiamante, come il tentativo di estrarre da un buffer vuoto o di inserire in un buffer pieno, e le proprietà interne che devono essere garantite dal modulo stesso, come la coerenza degli indici e delle dimensioni. Le assert vengono utilizzate esclusivamente per verificare le proprietà interne, mentre gli errori di utilizzo vengono segnalati tramite eccezioni esplicite.


## Assert e concorrenza in Python  

Poiché Python non offre un'unica semantica concorrente uniforme, ma combina tre paradigmi distinti, thread protetti dal Global Interpreter Lock (GIL), processi separati tramite il modulo `multiprocessing` e coroutine cooperative tramite `asyncio`, che presentano proprietà molto diverse e che impongono vincoli specifici sul modo in cui le assert devono essere utilizzate per rilevare condizioni di errore che emergono solo in presenza di interleaving non deterministici.


## Il GIL

Il Global Interpreter Lock garantisce che in ogni istante solo un thread possa eseguire istruzioni Python, ma non garantisce che operazioni apparentemente atomiche a livello sintattico lo siano anche a livello semantico. In particolare l'istruzione `self._n += 1` viene tradotta in una sequenza di bytecode distinti, tipicamente un `LOAD_FAST`, un `LOAD_CONST`, un'operazione aritmetica e uno `STORE_ATTR`, e il GIL può essere rilasciato tra una di queste istruzioni e la successiva, rendendo possibile un'interferenza tra thread che porta a condizioni di race difficili da individuare se non si analizza il bytecode generato.

```python
import threading
import dis

class Contatore:
    def __init__(self):
        self._n = 0
        self._lock = threading.Lock()

    def incrementa_sbagliato(self):
        self._n += 1   # tre bytecode, race possibile

    def incrementa_giusto(self):
        with self._lock:
            self._n += 1

# dis.dis(Contatore.incrementa_sbagliato)
# mostra LOAD_FAST, LOAD_CONST, BINARY_OP, STORE_ATTR
# punti di rilascio del GIL stanno fra questi
```

Di conseguenza, qualsiasi assert che intenda verificare l'assenza di condizioni di race deve essere collocata all'interno della sezione critica protetta dal lock, poiché solo in quel contesto è possibile garantire che la proprietà verificata rifletta uno stato coerente della struttura dati condivisa.

```python
class Coda:
    def push(self, x):
        with self._lock:
            assert self._size < self._cap, "push su coda piena, race?"
            self._buf[self._tail] = x
            self._tail = (self._tail + 1) % self._cap
            self._size += 1
            self._check_rep()
```


## Thread daemon e assert

Un aspetto trascurato riguarda il fatto che un'eccezione sollevata in un thread non-main non viene propagata automaticamente al thread principale, e quindi un'`AssertionError` può terminare un thread lasciando il programma in uno stato inconsistente senza che il chiamante ne sia consapevole. Per evitare questa situazione, è necessario configurare esplicitamente `threading.excepthook` in modo da intercettare tutte le eccezioni non gestite nei thread e applicare una politica di fail-fast quando l'errore riguarda una violazione di un'assert interna.

```python
import threading
import sys
import logging

def thread_excepthook(args):
    logging.error(
        "thread crashed: name=%s exc=%s",
        args.thread.name, args.exc_value
    )
    if isinstance(args.exc_value, AssertionError):
        sys.exit(70)   # fail-fast su assert in thread

threading.excepthook = thread_excepthook
```

Nelle versioni precedenti alla 3.8 era necessario giocare (sotoclassare se così possiamo dire) `Thread` e sovrascrivere `run`, ma l'introduzione di `excepthook` ha reso questo meccanismo molto più coerente.

## Multiprocessing e shared memory

Quando si utilizza il modulo `multiprocessing`, i processi non condividono lo stesso spazio di memoria, ma possono condividere segmenti specifici tramite `multiprocessing.shared_memory` o valori atomici tramite `multiprocessing.Value`. In questi casi le assert che verificano proprietà sullo stato condiviso devono essere protette da un lock del modulo `multiprocessing`, poiché i lock del modulo `threading` non garantiscono mutua esclusione tra processi distinti. Questo è particolarmente importante quando più processi modificano lo stesso valore condiviso, poiché l'assenza di sincronizzazione può portare a condizioni di race difficili da rilevare senza assert mirate.

```python
from multiprocessing import Process, Value, Lock

def worker(contatore, lock):
    for _ in range(1000):
        with lock:
            assert contatore.value >= 0
            contatore.value += 1

contatore = Value('i', 0)
lock = Lock()
processi = [Process(target=worker, args=(contatore, lock)) for _ in range(4)]
```

In questo caos l'assert svolge un ruolo importante nel verificare che il valore condiviso non assuma stati intermedi non validi, e il lock garantisce che la verifica e l'aggiornamento avvengano come un'unica operazione atomica dal punto di vista logico.

Ci sarebbe anche la questione del Free-threaded Python (PEP 703), in pratica con l'introduzione della build sperimentale di Python senza GIL dalla versione 3.13, il modello di concorrenza cambia poiché l'atomicità a livello di bytecode non è più garantita e qualsiasi operazione che manipola uno stato condiviso deve essere protetta da meccanismi espliciti di sincronizzazione. In questo contesto, codice che in CPython tradizionale non manifestava race può improvvisamente esporre condizioni di interleaving non previste, e le assert quindi diventano uno strumento molto utile per individuare tali problemi durante la migrazione verso ambienti free-threaded.

## Linguaggio C  

Abbiamo già detto come C tratta le assert tramite il preprocessore, quindi dovrebbe essere chiaro che il compilatore non fornisce alcuna protezione contro l'inserimento di effetti collaterali all'interno dell'assert, quindi il programmatore deve essere consapevole che qualsiasi espressione valutata all'interno di un'assert può essere rimossa integralmente dal binario finale senza alcun avviso.

```c
#include <assert.h>
#include <stddef.h>
#include <stdbool.h>

double media(const double *numeri, size_t n) {
    assert(numeri != NULL);
    assert(n > 0);

    double somma = 0.0;
    double minimo = numeri[0], massimo = numeri[0];
    for (size_t i = 0; i < n; i++) {
        somma += numeri[i];
        if (numeri[i] < minimo) minimo = numeri[i];
        if (numeri[i] > massimo) massimo = numeri[i];
    }
    double risultato = somma / (double)n;
    assert(risultato >= minimo - 1e-9 && risultato <= massimo + 1e-9);
    return risultato;
}

static bool ordinato(const int *arr, size_t n) {
    for (size_t i = 1; i < n; i++)
        if (arr[i-1] > arr[i]) return false;
    return true;
}

int ricerca_binaria(const int *arr, size_t n, int target) {
    assert(arr != NULL);
    #ifdef DEBUG_HEAVY
        assert(ordinato(arr, n));
    #endif
    if (n == 0) return -1;
    size_t inizio = 0, fine = n - 1;
    while (inizio <= fine) {
        assert(inizio < n && fine < n);
        size_t medio = inizio + (fine - inizio) / 2;
        if (arr[medio] == target) return (int)medio;
        else if (arr[medio] < target) inizio = medio + 1;
        else {
            if (medio == 0) break;   // size_t va trattato con cura
            fine = medio - 1;
        }
    }
    return -1;
}

typedef struct { long saldo; } Conto;

void trasferisci(Conto *a, Conto *b, long importo) {
    assert(a != NULL && b != NULL);
    assert(a != b);
    assert(importo > 0);
    assert(a->saldo >= importo);

    long totale_prima = a->saldo + b->saldo;
    a->saldo -= importo;
    b->saldo += importo;
    assert(a->saldo + b->saldo == totale_prima);
}
```


## C‑ismi utili  

Il linguaggio C offre anche `static_assert`, introdotto in C11, che consente di eseguire verifiche a tempo di compilazione e che risulta utile per controllare proprietà dei tipi, dimensioni delle strutture o vincoli che devono essere garantiti indipendentemente dall'esecuzione del programma. Poiché `static_assert` viene valutato dal compilatore, esso non introduce alcun costo a runtime e costituisce uno strumento essenziale per documentare e verificare assunzioni strutturali.

```c
static_assert(sizeof(int) >= 4, "richiediamo int da almeno 32 bit");
```

Quando è necessario verificare condizioni che devono rimanere attive anche in presenza di `-DNDEBUG`, ad esempio in componenti di sicurezza o in moduli che gestiscono input critici, è opportuno definire una macro personalizzata come `VERIFY(cond)` che non venga rimossa dal preprocessore e che mantenga un comportamento coerente in tutte le configurazioni di compilazione. Un errore classico consiste nel confondere l'operatore di assegnazione con quello di confronto, come in `assert(x = 5)`, che non solo altera lo stato del programma ma produce un'assert che risulta sempre vera, mascherando completamente l'errore. Un altro errore frequente consiste nell'inserire chiamate a funzioni con effetti collaterali all'interno di un'assert, come `assert(consume_buffer(buf))`, che sotto `-DNDEBUG` viene rimossa, eliminando anche l'effetto utile della funzione.

## Una hash map a indirizzamento aperto  

La struttura dati seguente una funzione di servizio `check_rep` permette di verificare la coerenza interna della rappresentazione. Questo tipo di struttura, basata sull'indirizzamento aperto, richiede che diverse proprietà siano mantenute insieme poiché la correttezza dell'algoritmo di probing dipende da vincoli che non sono evidenti e che possono essere facilmente violati da modifiche superficiali.

```c
#include <assert.h>
#include <stdint.h>
#include <stdlib.h>
#include <string.h>

typedef struct {
    int chiave;
    int valore;
    enum { VUOTO, OCCUPATO, TOMBA } stato;
} Slot;

typedef struct {
    Slot *slots;
    size_t cap;     // potenza di due
    size_t occupati;
    size_t tombe;
} HashMap;

static size_t hash(int k, size_t cap) {
    /* mix banale a scopo didattico */
    uint32_t x = (uint32_t)k;
    x = (x ^ 0x9e3779b9u) * 2654435761u;
    return (size_t)x & (cap - 1);
}

/* Invarianti:
 *   - cap potenza di due
 *   - occupati + tombe <= cap
 *   - ogni slot OCCUPATO è raggiungibile dal probe
 *     che parte da hash(chiave, cap)
 *   - gli slot OCCUPATO hanno chiavi tutte distinte
 */

static void check_rep(const HashMap *m) {
#ifndef NDEBUG
    assert(m != NULL);
    assert(m->slots != NULL);
    assert((m->cap & (m->cap - 1)) == 0);   // potenza di due
    size_t conta_occ = 0, conta_tomb = 0;
    for (size_t i = 0; i < m->cap; i++) {
        if (m->slots[i].stato == OCCUPATO) conta_occ++;
        else if (m->slots[i].stato == TOMBA) conta_tomb++;
    }
    assert(conta_occ == m->occupati);
    assert(conta_tomb == m->tombe);
    assert(m->occupati + m->tombe <= m->cap);
#else
    (void)m;
#endif
}

void hm_init(HashMap *m, size_t cap_iniziale) {
    assert((cap_iniziale & (cap_iniziale - 1)) == 0);
    m->slots = calloc(cap_iniziale, sizeof(Slot));
    m->cap = cap_iniziale;
    m->occupati = 0;
    m->tombe = 0;
    check_rep(m);
}

void hm_put(HashMap *m, int k, int v) {
    check_rep(m);
    assert(m->occupati + m->tombe < m->cap);   // chiamare resize prima

    size_t i = hash(k, m->cap);
    while (m->slots[i].stato == OCCUPATO && m->slots[i].chiave != k)
        i = (i + 1) & (m->cap - 1);

    if (m->slots[i].stato != OCCUPATO) m->occupati++;
    if (m->slots[i].stato == TOMBA) m->tombe--;

    m->slots[i].chiave = k;
    m->slots[i].valore = v;
    m->slots[i].stato = OCCUPATO;
    check_rep(m);
}
```

Le assert che verificano che `cap` sia una potenza di due sono fondamentali, poiché l'intero meccanismo di probing si basa sull'aritmetica modulo `cap`, e qualsiasi modifica alla politica di crescita della tabella che violi questa proprietà comprometterebbe la correttezza dell'algoritmo in modo difficile da diagnosticare senza controlli espliciti.


## Assert e concorrenza in C  

Il linguaggio C non offre alcuna protezione automatica contro data race, memory reorder o interleaving non deterministici quindi qualsiasi assert che verifichi proprietà su uno stato condiviso deve essere collocata all'interno della sezione critica protetta dal lock, poiché solo in quel contesto è possibile garantire che la proprietà osservata rifletta uno stato coerente e non un'istantanea parziale ottenuta durante un'interferenza tra thread.

```c
#include <pthread.h>
#include <assert.h>

typedef struct {
    pthread_mutex_t lock;
    int saldo;
    int versione;
} Conto;

void preleva(Conto *c, int importo) {
    pthread_mutex_lock(&c->lock);
    assert(c->saldo >= 0);            // invariante dentro il lock
    assert(importo > 0);              // su variabile locale, fuori dal lock va lo stesso
    if (c->saldo >= importo) {
        c->saldo -= importo;
        c->versione++;
    }
    assert(c->saldo >= 0);            // postcondizione, sempre dentro il lock
    pthread_mutex_unlock(&c->lock);
}
```


## Signal safety di `assert`

La funzione `__assert_fail` invoca `fprintf` e successivamente `abort()`, ma `fprintf` non è async‑signal‑safe, il che significa che chiamarla all'interno di un signal handler costituisce undefined behavior. Un'assert che fallisce all'interno di un handler di segnali come `SIGALRM`, `SIGINT` o `SIGCHLD` può causare deadlock sui lock interni della libreria standard o lasciare la libreria in uno stato inconsistente. Per questo motivo, gli handler devono essere ridotti a operazioni minimali come scrivere su un file descriptor o impostare un flag atomico.

```c
#include <signal.h>
#include <stdatomic.h>

static volatile sig_atomic_t shutdown_requested = 0;

void handler_sigint(int sig) {
    // niente assert qui dentro
    shutdown_requested = 1;
}
```


## Thread Sanitizer (TSan)

Compilando con `-fsanitize=thread`, GCC e Clang inseriscono strumentazione che rileva data race tra accessi non sincronizzati alla memoria condivisa. TSan è in grado di individuare race che sfuggono completamente alle assert, poiché le race non sono rilevabili tramite controlli deterministici, e la combinazione di assert interne e TSan in continuous integration rappresenta una delle strategie più efficaci per individuare bug concorrenti in C.

```bash
gcc -fsanitize=thread -g -O1 programma.c -o programma
./programma   # TSan stampa race trovate con stack trace di entrambi i thread
```


## Memory ordering e atomic

A partire da C11, il linguaggio C ha deciso di fare un salto evolutivo e introdurre `<stdatomic.h>`, una sorta di kit di sopravvivenza per programmatori che vogliono manipolare variabili condivise senza trasformare il proprio software in un thriller psicologico. Con questo nuovo arsenale arrivano i tipi atomici come **atomic_int** e un'intera famiglia di funzioni, `atomic_load`, `atomic_store`, `atomic_fetch_add` e le immancabili `atomic_compare_exchange_strong` e `weak`, che sembrano nomi di Pokémon ma in realtà servono a evitare che due thread si pestino i piedi.

Così quando si scrivono assert su variabili atomiche, non basta leggerle alla buona come si farebbe con una variabile normale. No, no, il C11 pretende che tu usi **atomic_load_explicit**, specificando anche il *memory ordering* appropriato, perché leggere un valore atomico senza ordering è un po' come aprire il frigorifero di notte, potresti trovare quello che ti aspetti... oppure no.

E il memory ordering? Beh, quello è il livello di paranoia che vuoi applicare alla tua lettura, `memory_order_relaxed` è la versione **"vivo pericolosamente"**, mentre `memory_order_seq_cst` è il **non mi fido di nessuno, nemmeno di me stesso**.


```c
#include <stdatomic.h>

atomic_int contatore = 0;

void incrementa(void) {
    int v = atomic_load_explicit(&contatore, memory_order_relaxed);
    assert(v >= 0);   // legge un valore atomicamente consistente
    atomic_fetch_add_explicit(&contatore, 1, memory_order_relaxed);
}
```

In questo frammento, la funzione `incrementa` si comporta come un cameriere che prima controlla che il contatore non sia finito sotto zero (cosa che sarebbe sospetta quanto trovare un unicorno in garage), poi aggiunge uno al valore, sempre in modo atomico. Tutto questo senza imporre alcun vincolo di sincronizzazione pesante, perché `memory_order_relaxed` è perfetto quando ti interessa solo che l'operazione sia atomica, non l'ordine globale degli eventi.



## `abort()` e i thread fratelli

Quando un thread invoca `abort()` a seguito di un'assert fallita, il segnale `SIGABRT` viene inviato all'intero processo, causando la terminazione immediata di tutti i thread, indipendentemente dal loro stato. Se uno dei thread deteneva un lock su una risorsa esternam come un file, un socket o un lock cross‑process, tale lock può rimanere in uno stato inconsistente. Per questo motivo, nei sistemi long‑running è consigliabile utilizzare un wrapper personalizzato che registri l'errore, esegua eventuali operazioni di cleanup e solo successivamente invochi `abort()`.

```c
#define assert_clean(c) do {                              \
    if (!(c)) {                                           \
        fprintf(stderr, "assert failed: %s\n", #c);       \
        cleanup_globale();                                \
        abort();                                          \
    }                                                     \
} while (0)
```


## Assert e concorrenza in JavaScript  

Il modello di concorrenza di JavaScript presenta una combinazione peculiare di semplicità e complessità, poiché il linguaggio adotta un paradigma basato su un event loop single‑threaded per la maggior parte dei casi d'uso, ma allo stesso tempo mette a disposizione meccanismi come Web Worker, Worker Threads e `SharedArrayBuffer` che introducono forme di parallelismo reale e che richiedono un'attenzione molto più rigorosa quando si utilizzano assert per verificare proprietà su dati condivisi. Per comprendere come e quando le assert possano essere utilizzate in modo affidabile, è necessario distinguere con precisione tra i diversi contesti di esecuzione e tra le garanzie di atomicità e isolamento che ciascuno di essi fornisce.


## Single‑threaded event loop  

Nel modello di esecuzione tradizionale di JavaScript, quello che gira nel browser, in Node.js e in qualunque ambiente che rispetti l'architettura dell'event loop, tutto il codice viene eseguito su un singolo thread. Quindi due istruzioni JavaScript non possono *mai* correre fianco a fianco sullo stesso stato e quindi niente race condition nel senso classico del termine. Di conseguenza, qualsiasi `assert` che controlla proprietà su variabili locali o sullo stato condiviso del main thread è, in pratica, identica a un'assert in un programma completamente sincrono. Non c'è alcun interleaving concorrente e se qualcosa va storto, la colpa non è di un thread dispettoso che ha modificato lo stato mentre non guardavi, ma semplicemente della logica sequenziale del tuo codice.

```javascript
let saldo = 100;

function preleva(x) {
    assert(saldo >= x, `saldo insufficiente, saldo=${saldo} x=${x}`);
    saldo -= x;
    assert(saldo >= 0);
}
```

Nessuno può intervenire tra la prima assert e la sottrazione, quindi se `saldo >= x` è vero, lo sarà ancora un microsecondo dopo. Ma, perché c'è sempre un "ma", il modello asincrono introduce dei punti di yield, momenti in cui il thread principale dice: "Ok, ora tocca a qualcun altro". Questi punti sono generati da costrutti come `setTimeout`, `setImmediate` o `process.nextTick`. Ma ciò che era vero immediatamente prima dell'operazione asincrona potrebbe non esserlo più quando il task riprende. Quindi JavaScript ti protegge dalle race condition classiche, ma non dalle sorprese dell'asincronia. 

## Web Worker e SharedArrayBuffer  

Quando si entra nel mondo dei Web Worker nel browser o dei Worker Threads in Node.js, il modello di esecuzione cambia poiché ogni worker esegue codice JavaScript in parallelo su un proprio contesto V8 con una heap separata. In questo scenario, la comunicazione tra worker avviene tipicamente tramite `postMessage`, che effettua una copia strutturata dei dati, e quindi non esistono race condition sui dati trasferiti, poiché ogni worker opera su una copia indipendente. La situazione cambia completamente quando si utilizza `SharedArrayBuffer`, poiché questa struttura permette di condividere memoria binaria tra più thread JavaScript, introducendo race condition reali che devono essere gestite tramite le primitive atomiche fornite da `Atomics`. In questo contesto, qualsiasi assert che verifichi proprietà su dati condivisi deve essere basata esclusivamente su valori letti tramite `Atomics.load`, poiché leggere direttamente dalla vista tipizzata (`Int32Array`, `Uint8Array`, ecc.) senza utilizzare le operazioni atomiche può produrre risultati incoerenti o non sincronizzati.

```javascript
// nel main thread
const sab = new SharedArrayBuffer(1024);
const view = new Int32Array(sab);
worker.postMessage({ sab });

// dentro il worker
const view = new Int32Array(eventoIniziale.data.sab);

function incrementa() {
    const v = Atomics.load(view, 0);
    assert(v >= 0, `valore atomico negativo, v=${v}`);
    Atomics.add(view, 0, 1);
}
```

L'assert è valida solo perché il valore viene letto tramite `Atomics.load`, che garantisce una semantica di sincronizzazione definita dal modello di memoria di ECMAScript, mentre qualsiasi lettura diretta tramite `view[0]` sarebbe priva di garanzie.


## Node.js Worker Threads  

Nel contesto di Node.js, il modulo `worker_threads` implementa un modello molto simile a quello dei Web Worker del browser, con la differenza che offre meccanismi aggiuntivi come `MessageChannel` e `parentPort` per facilitare la comunicazione tra thread. Anche in questo caso, ogni worker possiede un proprio contesto V8 e una propria heap, e quindi qualsiasi assert che verifichi proprietà su variabili globali deve essere consapevole del fatto che le globali del worker non coincidono con quelle del main thread. Un errore comune consiste nell'assumere che una variabile globale definita nel main thread sia accessibile con lo stesso valore all'interno del worker, mentre in realtà ciascun worker possiede una copia indipendente dell'ambiente globale.

```javascript
const { Worker, isMainThread, parentPort } = require('node:worker_threads');

if (isMainThread) {
    const w = new Worker(__filename);
    w.on('error', (e) => {
        console.error('worker crashed:', e);
        process.exit(1);
    });
} else {
    // qui assert su globali != globali del main
    parentPort.on('message', (msg) => {
        assert(typeof msg.id === 'string', 'msg.id mancante');
        // ...
    });
}
```

Questo esempio è corretto perché verifica una proprietà del messaggio ricevuto tramite `parentPort`, che è l'unico canale di comunicazione affidabile tra worker e main thread. Qualsiasi assert che tenti di verificare proprietà su variabili globali condivise sarebbe invece priva di significato, poiché tali variabili non sono realmente condivise.


## **Deno e Bun**  



Le piattaforme **Deno** e **Bun** sembrano simili a Node.js ma hanno personalità molto diverse, come avere tre cugini che fanno lo stesso lavoro ma con stili completamente differenti. Il primo è metodico e prudente (**Deno**), uno è iperattivo e velocissimo (**Bun**), e uno è il veterano che ha visto di tutto (**Node.js**). E queste differenze influenzano in modo concreto il modo in cui le assert devono essere utilizzate in presenza di concorrenza, perché ciascun runtime introduce variazioni nel modello di isolamento, nei meccanismi di comunicazione tra worker e nelle garanzie di sicurezza offerte al codice applicativo. Deno, ad esempio, è il cugino che ti chiede il documento anche per entrare in cucina, implementa un sistema di permessi rigoroso che separa in modo netto le capacità del main thread da quelle dei worker, imponendo controlli granulari su ogni cosa. Così ogni assert che verifica proprietà su risorse esterne deve essere consapevole del fatto che tali risorse potrebbero non essere accessibili in un determinato contesto di esecuzione. Bun, al contrario, è il cugino che corre ovunque, parla veloce e fa tutto in metà del tempo. Grazie a un runtime scritto in Zig e a un modello di esecuzione ottimizzato, privilegia prestazioni molto elevate. Ma quando si parla di concorrenza, Bun mantiene un comportamento sostanzialmente compatibile con Node.js.

In entrambi i casi, le regole fondamentali discusse per Node.js, in particolare quelle relative a **SharedArrayBuffer**, alle primitive **Atomics** e alla separazione delle heap tra worker rimangono valide e costituiscono la base per l'uso corretto delle assert in contesti concorrenti. Se un worker modifica una cella di memoria condivisa, le tue assert devono tener conto del fatto che quella cella potrebbe cambiare tra un'operazione e l'altra. Se due worker comunicano tramite messaggi, devi ricordare che ciò che è vero prima dell'invio potrebbe non esserlo più quando il messaggio arriva.


# **Assert e concorrenza in TypeScript**  

Poiché TypeScript non modifica il modello di esecuzione di JavaScript ma aggiunge un sistema di tipi statico che viene completamente eliminato in fase di compilazione, l'uso delle assert in contesti concorrenti deve essere interpretato come una combinazione di garanzie statiche fornite dal compilatore e garanzie dinamiche fornite dal runtime. In particolare, i tipi `Promise<T>`, `Readonly<T>` e i parametri annotati come `readonly` rappresentano forme di assert statiche che il compilatore verifica in modo deterministico, impedendo modifiche non autorizzate a strutture dati che devono essere trattate come immutabili e riducendo quindi la possibilità di introdurre race condition logiche all'interno del codice applicativo. Questo significa che, quando si lavora con strutture immutabili o con parametri dichiarati `readonly`, il compilatore garantisce che nessuna parte del programma possa alterare tali valori, e quindi le assert dinamiche diventano superflue per questo tipo di proprietà.

```typescript
function processaImmutabile(dati: readonly number[]): number {
    // TS impedisce dati.push(), dati[0] = x eccetera
    // nessuna race possibile su dati
    return dati.reduce((a, b) => a + b, 0);
}
```

Dopo aver visto la funzione `processaImmutabile`, possiamo immaginare TypeScript come uno chef severo che controlla ogni ingrediente prima che tu possa anche solo avvicinarti ai fornelli. Quando lavori con strutture immutabili o parametri dichiarati `readonly`, il compilatore invece si comporta come un maître che impone che questi ingredienti non si tocchino e non si taglino. Li puoi solo osservare e usarli così come sono. E se provi a fare anche solo un `push()`, ti guardano come se avessi chiesto di mettere il formaggio sulle linghune con le volgole in un ristorante.

E quindi non serve controllare ogni volta che nessuno ci abbia infilato dentro un peperoncino a tradimento perché semplicemente non può succedere. Il compilatore è il tuo sous‑chef di fiducia che ti fa stare tranquillo rendendo gli ingredienti immutabili. Le cose cambiano quando entriamo nel mondo della memoria condivisa tra worker tramite `SharedArrayBuffer`. Qui la cucina diventa improvvisamente un ristorante con più cuochi che lavorano contemporaneamente sulla stessa pentola. TypeScript, per evitare che qualcuno rovesci il brodo o aggiunga zucchero al posto del sale, fornisce strumenti come `Int32Array`, `BigInt64Array` e il modulo `Atomics`, tutti rigorosamente tipizzati. Qui anche le *assertion functions* di TypeScript diventano utili come etichette ben scritte sui barattoli della dispensa. Quando restringono un tipo tramite narrowing, stanno dicendo agli altri cuochi che questo ingrediente è sicuramente fresco e non rischiano di intossicare i clienti. E se il valore verificato da un'assert deve essere trasferito tra worker tramite `postMessage`, TypeScript si assicura che arrivi dall'altra parte con l'etichetta ancora attaccata, purché sia un ingrediente che può essere trasportato secondo le regole dello structured clone. Quindi TypeScript di certo non cucina al posto tuo, ma ti impedisce di avvelenare accidentalmente i clienti.


## Rust

Rust fornisce tre macro principali per le assert, `assert!`, `debug_assert!` e le varianti `assert_eq!` e `assert_ne!`, e la distinzione tra assert sempre attive e assert attive solo in debug rappresenta una delle scelte progettuali più raffinate del linguaggio, poiché costringe il programmatore a riflettere in modo esplicito sul costo computazionale della verifica e sulla necessità di mantenerla o meno nel binario di produzione. La macro `assert!` rimane attiva anche in build `--release` e deve essere utilizzata per verificare proprietà che devono essere garantite in ogni configurazione, mentre `debug_assert!` viene eliminata dal compilatore in modalità release e risulta quindi ideale per verifiche costose o invarianti che servono principalmente durante lo sviluppo. Le macro `assert_eq!` e `assert_ne!` forniscono messaggi diagnostici più ricchi, poiché mostrano i valori confrontati, facilitando l'individuazione dell'errore.

```rust
fn media(numeri: &[f64]) -> f64 {
    assert!(!numeri.is_empty(), "lista vuota");
    let somma: f64 = numeri.iter().sum();
    let risultato = somma / numeri.len() as f64;
    let min = numeri.iter().cloned().fold(f64::INFINITY, f64::min);
    let max = numeri.iter().cloned().fold(f64::NEG_INFINITY, f64::max);
    debug_assert!(risultato >= min - 1e-9 && risultato <= max + 1e-9);
    risultato
}

fn ordinato<T: Ord>(arr: &[T]) -> bool {
    arr.windows(2).all(|w| w[0] <= w[1])
}

fn ricerca_binaria(arr: &[i32], target: i32) -> Option<usize> {
    debug_assert!(ordinato(arr), "array fuori ordine");
    if arr.is_empty() { return None; }
    let (mut inizio, mut fine) = (0usize, arr.len() - 1);
    loop {
        debug_assert!(inizio < arr.len() && fine < arr.len());
        let medio = inizio + (fine - inizio) / 2;
        match arr[medio].cmp(&target) {
            std::cmp::Ordering::Equal => return Some(medio),
            std::cmp::Ordering::Less => {
                if medio == arr.len() - 1 { return None; }
                inizio = medio + 1;
            }
            std::cmp::Ordering::Greater => {
                if medio == 0 { return None; }
                fine = medio - 1;
            }
        }
        if inizio > fine { return None; }
    }
}

struct Conto { saldo: i64 }

fn trasferisci(a: &mut Conto, b: &mut Conto, importo: i64) {
    assert!(importo > 0);
    assert!(a.saldo >= importo);
    let totale_prima = a.saldo + b.saldo;
    a.saldo -= importo;
    b.saldo += importo;
    debug_assert_eq!(a.saldo + b.saldo, totale_prima);
}
```

Il capitolo su Rust e Java adrebbe esteso e verrà fatto in una prossima versione del testo.


# Antipattern e dove trovarli

Riconoscere un antipattern significa sviluppare la capacità di individuare quelle strutture che, pur sembrando corrette possono introdurre i più disarati difetti, sono così tanti che è praticamente impossibile citarli tutti, servirebbe un libro di 500 pagine solo per loro, ma qualcosa la possiamo citare se ci limitiamo al nostro contesto.


## **Antipattern 1: side‑effect smuggling**  

Il primo antipattern consiste nell'inserire all'interno di un'assert un'espressione che produce effetti collaterali, come una scrittura su disco, un invio di dati in rete, un aggiornamento di uno stato globale o un'operazione che modifica una struttura dati. Questo comportamento è estremamente pericoloso perché l'assert può essere rimossa dal compilatore o dal runtime in base alle opzioni di ottimizzazione, e quindi l'effetto collaterale può scomparire completamente dal programma preavviso.

```python
assert salva_su_db(record), "salvataggio fallito"
```

```c
assert(inizializza_modulo() == 0);
```

```java
assert lista.add(elemento);   // add muta la lista
```

Quando il programma viene eseguito con `-O`, `-DNDEBUG` o senza `-ea`, l'intera espressione viene eliminata, e quindi l'operazione che si intendeva eseguire non viene più effettuata. Questo può portare a comportamenti incoerenti tra ambiente di sviluppo e ambiente di produzione, rendendo estremamente difficile individuare la causa del problema. La soluzione consiste nel separare in modo rigoroso l'effetto collaterale dalla verifica logica, garantendo che l'operazione venga sempre eseguita e che l'assert si limiti a verificare il risultato.

```python
ok = salva_su_db(record)
assert ok, "salvataggio fallito"
```

Questo pattern garantisce che l'effetto collaterale rimanga nel binario anche quando le assert vengono disattivate.

## 🥄 Il bug del “caffè fantasma”  

Negli anni '90, in un piccolo team che lavorava su un gestionale aziendale, c'era uno sviluppatore che aveva l'abitudine di infilare dentro le `assert` operazioni che "tanto devono sempre essere vere". Una di queste operazioni era una chiamata a una funzione che registrava su un file di log ogni volta che un ordine veniva processato. Una cosa innocua... apparentemente. La funzione si chiamava `scriviLogOrdine()`, e lo sviluppatore la usava così:

```c
assert(scriviLogOrdine(id) == 0);
```

Finché un giorno, in produzione, iniziarono a sparire misteriosamente delle righe dal registro degli ordini. Alcuni ordini risultavano processati, ma non c'era traccia del log. Il reparto amministrativo era convinto che il software stesse saltando delle operazioni. Il reparto tecnico era convinto che il reparto amministrativo non sapesse leggere i log. Il reparto amministrativo era convinto che il reparto tecnico non sapesse programmare. E il caffè era finito...

Dopo giorni di indagini qualcuno notò che il programma era stato compilato con `-DNDEBUG` per migliorare le prestazioni. E quindi tutte le `assert` erano state eliminate. Compresa quella che conteneva la chiamata a `scriviLogOrdine()`. Quindi gli ordini venivano processati correttamente... ma il log non veniva più scritto. Era come preparare un caffè perfetto e poi dimenticare di servirlo al cliente. Da allora, nel team, quando qualcuno proponeva di mettere un effetto collaterale dentro un'assert, gli altri rispondevano ridendo "Attento, o finiamo di nuovo con il caffè fantasma".


## **Antipattern 2: assert come security check**  

Il secondo antipattern consiste nell'utilizzare un'assert per verificare condizioni di sicurezza, come autenticazione, autorizzazione, limiti su input provenienti dall'utente o validazione di dati esterni. Questo comportamento è gravemente errato perché le assert possono essere disattivate in produzione, e quindi qualsiasi controllo di sicurezza implementato tramite assert può essere completamente bypassato semplicemente modificando le opzioni di esecuzione del programma.

```python
def trasferisci_fondi(utente, importo):
    assert utente.is_authenticated()
    assert utente.saldo >= importo
    esegui_trasferimento(utente, importo)
```

In un ambiente in cui le assert sono disattivate, un attaccante può invocare la funzione senza essere autenticato e trasferire fondi senza alcuna restrizione, trasformando un semplice flag di ottimizzazione in una vulnerabilità critica. La soluzione consiste nell'utilizzare controlli espliciti che rimangono sempre attivi, indipendentemente dalle opzioni di compilazione o runtime.

```python
def trasferisci_fondi(utente, importo):
    if not utente.is_authenticated():
        raise PermissionError("utente da autenticare")
    if utente.saldo < importo:
        raise ValueError("saldo insufficiente")
    esegui_trasferimento(utente, importo)
```

Le assert devono essere utilizzate esclusivamente per verificare proprietà interne del programma, non per controllare input esterni o condizioni di sicurezza.


# **Antipattern 3: assert come gestione errori**  

Il terzo antipattern consiste nell'utilizzare un'assert per gestire condizioni che derivano dal mondo esterno, come file mancanti, connessioni di rete interrotte, risorse non disponibili o input non validi. Queste condizioni non rappresentano errori del programmatore, ma stati del mondo che devono essere gestiti in modo esplicito tramite eccezioni o valori di ritorno strutturati.

```python
def leggi_config(path):
    f = apri(path)
    assert f is not None, "file mancante"
    ...
```

In ambiente di sviluppo, l'assert provoca un crash immediato, mentre in produzione, con le assert disattivate, il programma prosegue e tenta di dereferenziare `None`, producendo errori difficili da diagnosticare. La soluzione consiste nel distinguere in modo rigoroso tra *bug* e *stato del mondo*, utilizzando eccezioni per gestire condizioni esterne e assert per verificare invarianti interni.

```python
def leggi_config(path):
    try:
        f = apri(path)
    except FileNotFoundError:
        raise ConfigError(f"config assente in {path}")
    ...
```

In realtà questo antipattern può anche andare bene se gestito con le pinze ad esempio dove si è certi che il binario non verrà eseguito con ottimizzazioni. Quindi non è che sono sbagliati per forza, è che se sei sicuro e consapevole puoi anche usare qualcosa di sbagliato ma deve esserci un motivo e devi esserne consapevole.

## **Bug o stato del mondo?**  

Per decidere se utilizzare un'assert o un controllo esplicito possiamo porci una domanda: **esiste una ragione realistica per cui questa condizione potrebbe fallire a causa di fattori esterni al mio codice?**. Se la risposta è no allora abbiamo un invariante interno che deve essere verificato tramite assert. Per capire quanto questa distinzione sia importante basti guardare cosa succede quando gli sviluppatori sbagliano domanda. Nel mondo reale, infatti, i bug più imbarazzanti nascono proprio dal confondere un *invariante* con lo *stato del mondo*, e viceversa. E gli esempi sono così assurdi che sembrano barzellette, ma purtroppo non lo sono.

Ad esempio si narra che un team avesse scritto `assert(server.isReachable())` convinto che "tanto il server è sempre online". Poi scoprirono che l'infrastruttura faceva un riavvio notturno alle 03:00 con il risultato di avere un crash programmato come un cucù svizzero. Un'altro scenario possibile potrebbe essere un'assert verifica che l'orologio di sistema non sia mai "nel futuro". Ma che succede se sul server dove gira il codice un sysadmin cambia l'ora del server per sbaglio? Il bug qui è nel codice ma nel caffè che il sysadmin non aveva evidentemente ancora bevuto.

Quindi una condizione può fallire perché il mondo è imprevedibile, rete che cade, file che spariscono, servizi che si riavviano, utenti che fanno cose strane, sysadmin che toccano pulsanti sbagliati, e allora non è un invariante e non va messa in un'assert. Se invece una condizione può fallire solo perché hai sbagliato tu allora è un bug e l'assert è lo strumento.


## Antipattern 4: over-asserting

Questo è il problema di tappezzare il codice di assert ovvie fino a ottenere l'impressione di un guardiano paranoide che chiede i documenti a ogni passo.

```python
def somma(a: int, b: int) -> int:
    assert isinstance(a, int)
    assert isinstance(b, int)
    risultato = a + b
    assert isinstance(risultato, int)
    assert risultato == a + b
    return risultato
```

Qui succede che il lettore fatica a vedere la logica vera sotto la coltre di assert e a forza di assert banali si sviluppa l'abitudine a ignorarle, e il giorno in cui una salta davvero magari non c'è ne accorgiamo.


## Antipattern 5: under-asserting

L'opposto del precedente, algoritmi delicati senza neanche un'assert, nella speranza che le cose vadano per il verso giusto e nella certezza che andranno per il verso storto.

```c
void heapify(int *arr, int n, int i) {
    int largest = i;
    int l = 2*i + 1;
    int r = 2*i + 2;
    if (l < n && arr[l] > arr[largest]) largest = l;
    if (r < n && arr[r] > arr[largest]) largest = r;
    if (largest != i) {
        int t = arr[i]; arr[i] = arr[largest]; arr[largest] = t;
        heapify(arr, n, largest);
    }
}
```

Quando emergerà il bug (e in codice del genere prima o poi capita), te ne accorgerai sessanta chiamate dopo l'origine...

## Antipattern 6: assert costose sempre attive

Guardate il frammento di codice python che segue:

```python
def inserisci(lista, x):
    lista.append(x)
    assert lista == sorted(lista)   # O(n log n) a ogni call
```

In dev la cosa va ma in produzione con assert attive?  Con assert spente il controllo svanisce e con esso il senso. E allora che si fa? Si usa il meccanismo di debug-only del linguaggio, `debug_assert!` in Rust, `#ifdef DEBUG_HEAVY` in C, `if __debug__:` in Python, e profili dedicati ai test in Java. Per le assert davvero pesanti, servirebbe considerare di trasformarle in property-based test che stanno fuori dal path di produzione.

## Antipattern 7, crash-shaming

Che consite nell'abusare di `assert(false)` o `unreachable!()` per rami che in realtà possono accadere in circostanze legittime.

```rust
match comando {
    Comando::Start => start(),
    Comando::Stop => stop(),
    _ => unreachable!(),
}
```

Il giorno in cui qualcuno aggiunge `Comando::Pause` all'enum, quell'`unreachable!()` esplode in produzione su un caso lecito.

## Antipattern 8: side effect su mock e stub durante i test

Le librerie di mocking offrono metodi tipo `was_called()`, `call_count`, `assert_called_with(...)` che sembrano innocenti e che invece in molte implementazioni modificano lo stato interno del mock. Asserire su quei metodi dentro un'assert che poi viene rimossa in release porta a test che passano per caso, oppure a test successivi che vedono lo stato del mock corrotto.

```python
from unittest.mock import MagicMock

def test_qualcosa():
    mock = MagicMock()
    sistema_sotto_test.usa(mock)
    assert mock.metodo.assert_called_with("foo")  # bug nascosto
```

Non c'è trucco e non c'è inganno, il bug nascosto non è uno, non sono due, ma son ben tre signore e signori....,`assert_called_with` solleva `AssertionError` se fallisce, quindi il risultato dell'espressione `mock.metodo.assert_called_with("foo")` è `None` (la funzione manca di un return value sensato), e `assert None` salta sempre. Inoltre `assert_called_with` di pytest-mock e altre implementazioni resetta lo stato del mock, oppure registra l'asserzione in modo che le chiamate successive vedano una storia diversa. E il colpo di grazia è che con `python -O` quell'assert sparisce e il test passa sempre, indipendentemente dal comportamento del codice.

```python
# bug a tre livelli
assert mock.metodo.assert_called_with("foo")
# sotto -O sparisce tutto
# senza -O, "assert None" salta sempre
# il mock viene comunque modificato
```

E come si fa? Si chiama il metodo del mock fuori dall'`assert`, e usa l'API del framework di test (`pytest.fixture`, `unittest.TestCase.assertEqual`), che mai vengono cancellate da flag di compilazione.

```python
def test_qualcosa():
    mock = MagicMock()
    sistema_sotto_test.usa(mock)
    mock.metodo.assert_called_with("foo")   # raise diretto, niente assert intorno
```

Stessa regola in Java con Mockito (`verify(mock).metodo(...)` fuori da `assert`), in JavaScript con jest (`expect(mock).toHaveBeenCalledWith(...)` fuori da `console.assert`), in Rust con `mockall` (le aspettative del mock vivono nel `Drop`, fuori da `assert!`).

## Antipattern 9: uguaglianza su float senza tolleranza

L'ho già toccato altrove ma è il bug più frequente nelle prime settimane di chi prova le assert.

```python
def calcola_prezzo(base, sconto):
    risultato = base * (1.0 - sconto)
    assert risultato == round(risultato, 2)   # salta su molti input
    return risultato
```

In IEEE 754, `base * (1.0 - sconto)` produce un valore con rumore di rappresentazione, e l'uguaglianza esatta con la versione arrotondata salta in modo che pare casuale. La frustrazione qui è massima, il codice sembra giusto a occhio e l'assert salta solo su certi input, e la riproduzione richiede di salvare gli input esatti. La cura? Tolleranza esplicita, sempre. La forma giusta dipende dalla scala dei numeri in gioco.

```python
import math

# valori vicini a uno, tolleranza assoluta
assert math.isclose(a, b, abs_tol=1e-9)

# valori di scala variabile, tolleranza relativa
assert math.isclose(a, b, rel_tol=1e-9)

# combinata, raccomandata da Python e dalla maggior parte delle librerie
assert math.isclose(a, b, rel_tol=1e-9, abs_tol=1e-12)
```

Stessa logica in Rust con `approx::assert_relative_eq!`, in C con un macro custom basato su `fabs(a - b) < epsilon * fmax(fabs(a), fabs(b))`, in JavaScript con `Math.abs(a - b) < epsilon` su valori normalizzati. Il caso più tricky riguarda il confronto con zero. `math.isclose(x, 0)` con sola tolleranza relativa non funziona (qualsiasi numero è infinitamente lontano da zero in scala relativa), e va sempre accompagnato da una tolleranza assoluta.

```python
# bug sottile
assert math.isclose(grad_loss, 0, rel_tol=1e-9)   # salta sempre se grad_loss != 0

# cura
assert math.isclose(grad_loss, 0, abs_tol=1e-6)
```

# **Antipattern 10: assert con effetto rimosso in release**  

Uno degli antipattern più difficili da individuare, soprattutto nei linguaggi che prevedono la rimozione condizionale delle assert in fase di compilazione o ottimizzazione, consiste nell'inserire all'interno di un'assert un'espressione che produce effetti collaterali indispensabili al corretto funzionamento del programma. Questo problema si manifesta in modo particolarmente evidente in C, dove la macro `assert` viene completamente eliminata quando è definito `NDEBUG`, e in Rust, dove la macro `debug_assert!` viene rimossa nelle build di release. In entrambi i casi, qualsiasi effetto collaterale contenuto nell'assert scompare, lasciando il programma in uno stato incoerente o non inizializzato, e producendo bug che emergono solo in produzione, spesso in condizioni difficili da riprodurre.

```c
// in C, bug classico
int risultato;
assert((risultato = init_sistema()) == OK);
// in release con NDEBUG, init_sistema() manca di essere chiamata
// risultato è non-inizializzato, comportamento undefined
```

```rust
// in Rust, stesso schema
debug_assert!(verifica_e_aggiorna_cache(&mut cache));
// in release, verifica_e_aggiorna_cache manca di essere chiamata
// la cache resta vuota
```

In questi esempi in debug tutto funziona correttamente, mentre in release il programma si comporta in modo completamente diverso, spesso con sintomi che non suggeriscono immediatamente la causa del problema. Questo antipattern è talmente pericoloso che linee guida rigorose come **MISRA‑C**, utilizzate nell'industria automotive e aerospaziale, vietano esplicitamente l'inserimento di effetti collaterali all'interno di un'assert, proprio perché la rimozione condizionale dell'assert può alterare il comportamento del programma in modo imprevedibile. Lo stesso principio, pur non formalizzato in uno standard equivalente, vale in pieno anche per Rust, dove l'uso improprio di `debug_assert!` può introdurre differenze semantiche tra build di debug e build di release. La soluzione consiste nel separare l'effetto collaterale dalla verifica logica, garantendo che l'operazione venga sempre eseguita e che l'assert si limiti a verificare una condizione derivata da uno stato già stabilito.

```c
int risultato = init_sistema();
assert(risultato == OK);
```

```rust
let aggiornato = verifica_e_aggiorna_cache(&mut cache);
debug_assert!(aggiornato);
```

Questa separazione garantisce che il comportamento del programma rimanga coerente tra build di debug e build di release.


## **Effetti collaterali indiretti**  

Esiste una variante dello stesso antipattern che si manifesta quando la funzione chiamata all'interno dell'assert modifica una struttura esterna o uno stato globale, anche se il valore di ritorno non viene utilizzato direttamente. In questo caso, la rimozione dell'assert elimina completamente l'aggiornamento, lasciando il programma in uno stato incoerente.

```rust
// la chiamata a counter.increment() conta come effetto laterale
debug_assert!(counter.increment() > 0);
// in release la chiamata sparisce, il counter resta a zero
// e tutto il codice a valle che si aspettava il counter aggiornato si rompe
```

Questo tipo di errore sembra semanticamente corretto a una prima lettura, e solo un'analisi approfondita del comportamento in release rivela che l'assert stava svolgendo un ruolo che non avrebbe mai dovuto avere.


## **La regola pratica che salva sempre**  

Una regola semplice ma estremamente potente permette di evitare questo antipattern in modo sistematico:


**se la rimozione dell'assert modifica il comportamento del programma, allora il programma contiene un bug latente che esploderà inevitabilmente in release**. 

Le assert devono essere trattate come verifiche opzionali, non come parti integranti della logica applicativa, e qualsiasi violazione di questo principio deve essere considerata un errore grave. Se ignorate questa regola sarà come costruire un ponte usando un'impalcatura come parte strutturale. Finché l'impalcatura c'è, tutto sembra stabile. Poi arriva la release, l'impalcatura (cioè le assert) viene rimossa e il ponte collassa con la grazia di un frigorifero che cade da un terzo piano.

Quindi tenetelo a mente, le assert non sono un meccanismo di controllo del flusso, non sono un modo elegante per fare una cosa e verificare che sia andata bene e non sono un sostituto dell'error handling. Le assert sono un faro che illumina gli invarianti interni e ti dicono quando hai violato le tue stesse regole. Se spegnere il faro cambia la rotta della nave, allora hai scambiato un timone per un faro. E il timone non va mai messo in un'assert. E se scambiare un timone per un faro ti sembra impossibile dovresti vedere quello che la gente scrive nel codice di progetti veri... E ora arriviamo alla parte più importante secondo me.

# **Le assert hanno effetti collaterali anche quando spariscono**  

La presenza di un'assert nel sorgente _modifica il comportamento del compilatore e del runtime anche quando l'assert viene disattivata_!!! Questa modifica coinvolge l'intero processo di ottimizzazione, poiché il compilatore costruisce il grafo di controllo e applica trasformazioni basate sulla struttura del codice sorgente, e la presenza o assenza dell'assert influenza il layout della memoria, la disposizione delle istruzioni, la pressione sui registri, il comportamento del branch predictor e il timing complessivo dell'esecuzione. Di conseguenza, un programma compilato con assert attive e lo stesso programma compilato con assert disattivate possono presentare differenze osservabili, anche quando l'assert non contiene effetti collaterali diretti. Un caso noto nella comunità del kernel Linux ha evidenziato questo fenomeno. Nel dicembre 2003, durante una discussione su un crash legato alla gestione di un thread group leader in stato zombi, Linus Torvalds osservò che l'introduzione di assert aggressive aveva portato più volte a modifiche del codice circostante per evitare il fallimento dell'assert, anche quando l'assert stessa si era rivelata basata su un'ipotesi errata. Anni dopo, in occasione del rilascio di Linux 4.8, Torvalds ribadì che un'assert fallita in un componente critico del kernel può produrre effetti peggiori di un arresto controllato, poiché può portare a corruzione dei dati. Il punto è che la presenza di un assert altera davvero il comportamento del compilatore e la sua rimozione modifica la struttura del programma in modo non trasparente.


## **Dentro un'assert**  

La regola raramente esplicitata nei corsi introduttivi, è che **un'assert deve contenere esclusivamente espressioni prive di effetti collaterali**, cioè espressioni che leggono lo stato senza modificarlo, che non allocano memoria, che non aprono file, che non invocano operazioni di rete, che non consultano il clock, che non generano numeri casuali, che non acquisiscono lock, che non aggiornano contatori e che non alterano alcuna struttura dati. **Qualsiasi violazione di questa regola introduce una divergenza semantica tra build di debug e build di release**, poiché la rimozione dell'assert elimina anche la chiamata di funzione o l'espressione che produce l'effetto collaterale.

Il motivo è legato al modo in cui le assert vengono rimosse in C, in questo linguaggio la macro `assert` si espande in `((void)0)` quando è definito `NDEBUG`, e il preprocessore elimina completamente il codice prima della fase di compilazione. In Python il flag `-O` impedisce la generazione del bytecode dell'assert. In Java l'assenza del flag `-ea` fa sì che la JVM elimini l'intero ramo dell'assert. Invece per Rust la macro `debug_assert!` viene rimossa dall'ottimizzatore in modalità release. In tutti questi casi se l'assert contiene una chiamata di funzione, la chiamata viene eliminata insieme all'assert, e con essa scompaiono i suoi effetti.

```c
// l'allocazione dentro l'assert
int *p;
assert(p = malloc(sizeof(int) * 100));
*p = 42;   // segfault in release, p non è mai stato allocato
```

```python
def init():
    contatore = {"valore": 0}
    assert incrementa_contatore(contatore), "incremento fallito"
    return contatore["valore"]   # zero in release, uno in debug
```

```rust
// counter.increment() ritorna true se l'incremento è andato
debug_assert!(counter.increment());
// in release counter.increment() mai viene chiamato
// e il codice a valle vede counter ancora a zero
```

In presenza di un'assert, il programma può eseguire due letture in debug e una sola in release, producendo divergenze che possono manifestarsi solo in casi diffiili da trovare. E se c'è concorrenza diventa asssurdo, un'assert che acquisisce un lock in debug ma non in release modifica il comportamento temporale del programma, altera l'ordine delle operazioni osservate dagli altri thread e può far emergere race condition che non si manifestano in debug. Esiste un'unica eccezione e consite nelle funzioni che sono *idempotenti e prive di effetti collaterali*, come `vector::size()`, `string::length()` o `array.length` in JavaScript. Queste funzioni possono essere utilizzate in un'assert senza introdurre differenze semantiche tra debug e release, anche se il costo a runtime può variare a seconda che il compilatore le inlining o meno.

In pratica basta chiersi **se questa espressione non venisse mai eseguita, il comportamento del programma rimarrebbe invariato?**  Se la risposta è sì, l'espressione è idonea a essere inserita in un'assert. Se la risposta è no, l'effetto collaterale deve essere estratto e reso esplicito, lasciando nell'assert solo la verifica di uno stato già determinato.


# **Trasformazioni strutturali indotte da assert**

Quando un'assert contiene una condizione come `assert(p != NULL)` e il codice successivo dereferenzia `p`, il compilatore in modalità release può assumere che `p` sia non nullo, poiché la condizione asserita rappresenta, dal punto di vista del compilatore, una garanzia fornita dal programmatore. Questa assunzione consente al compilatore di eliminare controlli ridondanti, semplificare il grafo di controllo e applicare ottimizzazioni aggressive basate sull'ipotesi che la condizione sia sempre vera.

John Regehr ha analizzato questo comportamento in un articolo del 2014, osservando che la frase "il comportamento è indefinito quando l'assert fallisce" implica che il compilatore può trattare la condizione dell'assert come un'invariante. L'affermazione "comportamento indefinito quando `p` è false" equivale, dal punto di vista del compilatore, a "`p` può essere assunto true", e quindi il compilatore può ottimizzare il programma sotto questa assunzione. Questo può produrre un miglioramento delle prestazioni, poiché il compilatore elimina controlli considerati superflui, ma può anche generare codice che si basa su ipotesi non più verificate quando l'assert viene rimossa in release.

In un episodio riportato da Regehr nel 2010, il kernel Linux eseguiva un dereferenziamento prima di un controllo di null pointer. GCC, compilando con `-O2`, deduceva che il dereferenziamento implicava `p != NULL`, e quindi eliminava il controllo successivo come dead code. Se `dev == NULL`, l'accesso `dev->priv` produce comportamento indefinito e il compilatore non ha obblighi particolari, se `dev != NULL`, il controllo è ridondante e può essere eliminato. In entrambi i casi, il compilatore conclude che il controllo è inutile e lo rimuove, introducendo una potenziale vulnerabilità. Per mitigare questo comportamento, il kernel ha introdotto il flag `-fno-delete-null-pointer-checks`, che impedisce al compilatore di eliminare controlli di null pointer basati su deduzioni di questo tipo.

Un'altra interazione rilevante tra assert e ottimizzazione riguarda l'uso di `__builtin_unreachable()` in GCC e Clang, che indica al compilatore che un determinato punto del codice non deve essere raggiunto. Il pattern:

```c
if (!cond) __builtin_unreachable();
```

equivale a un'assert che il compilatore considera vincolante. Se la condizione è falsa a runtime, il programma entra in comportamento indefinito. Lo standard C++ P0627R0 del 2017 osserva che marcare un punto come "irraggiungibile" è una funzionalità utile per l'ottimizzazione, e che l'ottimizzazione basata sull'assunzione che un ramo sia irraggiungibile rientra nella definizione di comportamento indefinito se il ramo viene effettivamente raggiunto. Il kernel Linux utilizza `__builtin_unreachable()` nella macro `unreachable()` sin da GCC 4.5, ottenendo una riduzione del binario di circa 4000 byte rispetto al precedente `for(;;);`, come riportato nel patchset di David Daney del 2009.

Inoltre, l'effetto delle assert sulle ottimizzazioni è realmente misurabile, e questo significa che non si tratta affatto di una fissazione da appassionati di compilatori o di una battuta da nerd che ci raccontiamo per fare i fighi. La semplice presenza di un'assert può influenzare il comportamento dell'ottimizzatore, modificando decisioni che riguardano aspetti fondamentali come la struttura del codice generato, l'uso dei registri o la disposizione delle istruzioni.vPer esempio, la *vettorizzazione di un ciclo può essere attivata o disattivata in base alla presenza di un'assert che impone un vincolo sulla lunghezza dell'array. Se l'assert fornisce al compilatore un'informazione aggiuntiva che rende il ciclo più prevedibile, il compilatore può decidere di vectorizzarlo. Se invece l'assert viene rimossa, quella garanzia scompare e l'ottimizzatore può concludere che la vectorizzazione non è più sicura o conveniente. Allo stesso modo, anche l'inlining di una funzione può cambiare radicalmente, un'assert inserita nel corpo della funzione ne aumenta la dimensione stimata, e questo può spingere il compilatore a non inline‑arla più, oppure a inline‑arla solo in alcuni punti. La presenza dell'assert altera il modello dei costi che guida l'ottimizzatore, e quindi influenza direttamente la struttura del codice generato. Un discorso analogo lo troviamo quando un'assert può mantenere in vita una variabile per un intervallo più lungo, costringendo il compilatore a riservarle un registro aggiuntivo o a spostare altre variabili nello stack. Senza l'assert, quella variabile potrebbe essere eliminata prima, liberando risorse e modificando l'intero layout del codice. Anche l'unrolling dei cicli, se non sapete cos'è andate a studiarlo che è interessante, dipende da soglie di costo molto precise, e l'inserimento di un'assert all'interno del ciclo altera il costo stimato. Anche se l'assert verrà rimossa in release, il compilatore ha comunque preso decisioni basate sulla sua presenza durante la fase di ottimizzazione, e queste decisioni rimangono nel binario finale. Il risultato p che lo stesso programma compilato con e senza assert produce due binari diversi, con differenze nelle istruzioni generate, nell'ordine delle operazioni, nell'uso dei registri e nella struttura dei branch. L'affermazione secondo cui "le assert in release vengono rimosse e non cambia nulla" è quindi precisa come un elefante entra preciso in una fiat 500, perché ciò che rimane dopo la rimozione è comunque un programma che è stato influenzato dalla loro presenza durante l'intero processo di ottimizzazione.

# **Effetti sulle architetture di esecuzione**

E questo non lo sa nessuno, l'aggiunta di un'assert modifica la dimensione della sezione `.text` del binario, spostando le istruzioni successive e alterando l'allineamento delle funzioni rispetto alle linee della instruction cache. Questo cambiamento può influenzare il numero di cache miss, la latenza di fetch delle istruzioni e il comportamento del branch predictor.  Daniel Lemire ha mostrato che i predittori moderni, come TAGE, sono sensibili al pattern degli indirizzi delle branch. Le stesse caratteristiche che consentono a TAGE di predire sequenze lunghe di branch correlate rendono difficile "resettare" il suo stato, poiché non è sufficiente eseguire un numero elevato di branch a indirizzi diversi. Alcune branch non accedono alle tabelle di history più lunga. L'aggiunta o la rimozione di un'assert modifica gli indirizzi di tutte le branch successive, e il predittore interpreta il programma come una sequenza completamente nuova. Per un certo numero di iterazioni, il programma può risultare più lento, fino a quando il predittore non apprende il nuovo pattern.

L'allineamento dello stack rappresenta un'altra superficie sensibile infatti una funzione che dichiara una variabile locale all'interno di un'assert alloca uno slot nello stack frame in debug, mentre in release quello slot non viene allocato. Questo produce indirizzi diversi per le variabili locali e può modificare il comportamento di codice che dipende implicitamente dalla disposizione dello stack. In casi estremi, un overflow dello stack che in debug sovrascrive una variabile innocua può in release sovrascrivere il return address.

E perfino il lifetime degli oggetti può essere influenzato dalla presenza di un'assert, per esempio in Rust, il borrow checker determina il lifetime statico dei riferimenti, e un'espressione come `debug_assert!(x.qualcosa())` mantiene il riferimento a `x` attivo fino al punto dell'assert. In release, l'assert viene rimossa e il lifetime di `x` si accorcia. Questo può modificare il punto in cui avviene un `drop`, o il comportamento del non-lexical lifetimes (NLL), producendo differenze tra debug e release.

# **Divergenze tra debug e release**

Ormai sappiamo che un programma compilato con le assert attive possiede una semantica, mentre lo stesso programma compilato con le assert disattivate ne possiede un'altra completamente diversa. La differenza rappresenta un abisso semantico che si apre sotto i piedi del programmatore non appena passa dalla build di debug alla build di release. L'esempio più noto riguarda l'undefined behavior in C e C++. Una funzione che dereferenzia un puntatore dopo averne verificato la "non‑nullità" tramite un'assert si comporta in modo impeccabile in debug. Il programmatore osserva un comportamento coerente, prevedibile e rassicurante. In release, però, se il puntatore risulta null in un percorso raro, il dereferenziamento produce comportamento indefinito. Il compilatore avendo ottimizzato il codice sotto l'assunzione che il puntatore fosse non nullo, elimina controlli successivi, rimuove rami considerati impossibili e genera codice che non corrisponde più alla logica apparente del sorgente. Il programmatore osserva crash, corruzione dei dati e comportamenti assurdi che non si verificano mai in debug. La discrepanza appare inspiegabile perché il sorgente sembra indicare un comportamento, mentre il binario ne implementa un altro. Il compilatore ha applicato ottimizzazioni basate su assunzioni che non vengono più verificate, e il risultato finale assomiglia a un prestigiatore che continua a tagliare la donna a metà anche quando la donna non è più nella scatola. Un'assert che incrementa un contatore in debug produce un numero di incrementi diverso rispetto alla build di release, e questo altera il comportamento di qualsiasi codice che dipende da quel contatore. Un test che utilizza un PRNG produce risultati diversi tra debug e release perché l'ordine delle chiamate al generatore cambia. Un'assert che legge il clock modifica il timing e fa scattare un timeout in debug che non si verifica in release. Un programma che in release è deterministico diventa non deterministico in debug, e un programma che in debug è deterministico diventa non deterministico in release. Le differenze nel numero di chiamate a funzioni non pure e le differenze nel comportamento temporale creano due universi paralleli che condividono il sorgente ma non condividono la realtà. Una pipeline CI che esegue solo build di debug fornisce quindi una copertura incompleta sfatando un mito molto diffuso... La pipeline ignora differenze semantiche che emergono solo in release e certifica un comportamento che non esiste nel binario finale. Così la pipeline finisce per approvare un universo che non verrà mai distribuito e diventa un oracolo che predice il futuro sbagliato con assoluta sicurezza.

# **Bug Heisenberg**

Il fenomeno noto come *Bug Heisenberg* descrive una categoria di difetti in cui la presenza di un'assert modifica la struttura del programma in modo tale che la sua rimozione produce un comportamento diverso, non perché l'assert esegua un controllo logico rilevante, ma perché la sua esistenza altera la visibilità del codice, la durata delle variabili, la raggiungibilità dei percorsi di esecuzione e l'applicazione delle ottimizzazioni. Questo tipo di difetto è particolarmente insidioso perché la differenza tra debug e release non deriva da un errore nel sorgente, ma da trasformazioni applicate dal compilatore sulla base della presenza dell'assert, e la rimozione dell'assert elimina condizioni che influenzavano la generazione del codice, producendo un comportamento che non corrisponde più alle aspettative del programmatore.

Un esempio in C++ mostra come un'assert possa forzare l'istanziazione di una funzione che, in assenza dell'assert, verrebbe eliminata come codice non utilizzato:

```cpp
class Cache {
    std::vector<int> entries;
public:
    void add(int x) {
        entries.push_back(x);
    }
    bool invariant_ok() const {
        return std::is_sorted(entries.begin(), entries.end());
    }
};

void uso(Cache& c) {
    c.add(42);
    assert(c.invariant_ok());   // forza l'istanziazione di invariant_ok
    // ...
}
```

In modalità debug, il compilatore genera il corpo di `invariant_ok` perché la funzione viene referenziata. In modalità release, l'assert viene rimossa e la funzione non risulta più utilizzata, e quindi il compilatore la elimina come codice non necessario. Questo comportamento è coerente con le regole di eliminazione del codice non referenziato, ma può produrre effetti inattesi quando l'assert era l'unico punto che determinava la presenza di una funzione o di un'istanza di template, e la sua rimozione altera la struttura del programma in modo non evidente. Il fenomeno opposto si verifica quando un'assert impedisce al compilatore di eliminare un effetto collaterale che, in assenza dell'assert, verrebbe considerato privo di rilevanza semantica e quindi rimosso tramite dead store elimination. Il seguente esempio mostra il problema in C

```c
static int contatore_chiamate = 0;

int calcola(int x) {
    contatore_chiamate++;
    assert(contatore_chiamate > 0);   // overflow check
    return x * 2;
}
```

In release invece l'assert viene rimossa e il compilatore osserva che `contatore_chiamate` viene incrementato ma non viene letto nello stesso file, e quindi può eliminare l'incremento come scrittura priva di effetti osservabili. GCC con LTO applica questa ottimizzazione. Se un altro modulo legge `contatore_chiamate` per metriche, la build di debug produce un valore diverso rispetto alla build di release, generando una divergenza semantica che non deriva da un errore logico nel sorgente, ma da una differenza nella visibilità dell'effetto collaterale. Inoltre un'assert che verifica la consistenza tra due variabili condivise può invocare una funzione che acquisisce e rilascia un lock, introducendo un punto di sincronizzazione implicito. In modalità release, l'assert viene rimossa e il lock non viene più acquisito. Questo modifica il comportamento temporale del programma, altera l'ordine delle operazioni osservate dagli altri thread e può far emergere una race condition che non si manifesta in debug. Il risultato è qualcosa che appare solo in produzione poiché la build di debug maschera la race tramite un ordine di esecuzione diverso.

Quindi **la presenza di un'assert può mantenere attivi percorsi di esecuzione, effetti collaterali o riferimenti che, in assenza dell'assert, il compilatore considera irrilevanti e quindi elimina**, e la rimozione dell'assert produce un programma con una struttura diversa, nonostante il sorgente sembri invariato. Questo tipo di difetto richiede un'analisi attenta delle ottimizzazioni applicate dal compilatore e delle condizioni che determinano la visibilità del codice, poiché la differenza tra debug e release non deriva da un errore logico, ma da trasformazioni applicate sulla base delle informazioni fornite dall'assert.


# **Sicurezza, linking, comportamento globale**

L'impatto delle assert sulla sicurezza non viene molto discusso me è critico poiché la rimozione dell'assert in modalità release può eliminare controlli che il programmatore riteneva attivi, generando vulnerabilità che non dipendono da errori logici. PEnsiamo al controllo di autorizzazione implementato tramite un'assert, come nel caso `assert(utente.è_admin())`, che in modalità debug interrompe l'esecuzione quando l'utente non possiede i privilegi necessari, mentre in modalità release elimina completamente sia la verifica sia la chiamata a `è_admin()`. Questo comportamento produce una vulnerabilità doppia, poiché il controllo di autorizzazione non viene più eseguito e gli eventuali effetti collaterali della funzione, come operazioni di logging o aggiornamenti di metriche, vengono eliminati senza alcuna segnalazione. L'effetto delle assert si estende anche al comportamento del linking nei linguaggi che utilizzano sistemi di build con ottimizzazioni condizionali. In Rust, l'uso del flag di configurazione `debug-assertions = true` può attivare o disattivare crate che esistono esclusivamente per fornire funzioni di verifica, e la loro presenza o assenza modifica la struttura del grafo delle dipendenze e la composizione del binario finale. In OCaml, la flag `-noassert` modifica il modulo `Assert` utilizzato durante il linking, producendo un eseguibile con una superficie di codice diversa rispetto alla build di debug ottenendo binari con dimensione diversa, così la disposizione dei moduli e la visibilità delle funzioni, generando comportamenti diversi tra debug e release anche senza modifiche al codice sorgente. Le differenze introdotte dalle assert arrivano perfino a influenzare i compilatori JIT, nella HotSpot JVM, una funzione compilata con assert attive (flag `-ea`) può avere un grafo di chiamata più grande rispetto alla stessa funzione compilata senza assert, e questo può modificare il livello di ottimizzazione applicato dalla JIT. Una funzione che senza assert sarebbe stata promossa al livello C2 può rimanere al livello C1 quando la presenza dell'assert aumenta la dimensione del corpo oltre la soglia prevista per l'ottimizzazione massima. Inoltre, un'assert che fallisce può attivare un fenomeno noto come *deopt cascade*, in cui la JIT decide di deottimizzare la funzione e tornare all'interprete mandando all'aria le ottimizzazioni.


## **Morale della favola**

Le assert devono essere considerate codice a tutti gli effetti e come tali influenzano il comportamento del compilatore, del linker, del runtime e della CPU, del tuo cane e perfino della tua pressione arteriosa anche se solo indirettamente tramite il numero di caffè che ti portano a consumare. La loro presenza modifica il modo in cui vengono applicate le ottimizzazioni, a volte le rende incomprensibili, altre volte altera la struttura del codice generato, senza avvisarti modifica la disposizione della memoria, influisce sul comportamento della cache, cambia la predizione dei branch e pure delle cene, altera la durata delle variabili, modifica il linking dei moduli e influisce sui livelli di ottimizzazione applicati dai compilatori JIT, insomma è un casino! La regola operativa più importante consiste nel garantire che un'assert contenga esclusivamente espressioni prive di effetti collaterali, in modo che la rimozione dell'assert modifichi soltanto la struttura del codice e non la semantica del programma. Una seconda regola operativa consiste nel testare sempre il programma in modalità release, utilizzando una pipeline CI che esegua il binario con `NDEBUG`, `-O`, `--release` o `-ea` disattivato, poiché esistono difetti che emergono esclusivamente in release e che non possono essere rilevati tramite test eseguiti in modalità debug. E infine ricordate di evitare l'uso delle assert come meccanismo di controllo di sicurezza, sostituendole con verifiche esplicite che rimangano attive in ogni configurazione di build.

## **Algoritmi sensibili al contesto**

C'è poi un gruppo di fenomeni che non viene trattata nei manuali introduttivi e che riguarda l'impatto delle assert su algoritmi che dipendono da proprietà estremamente delicate del comportamento del compilatore, della CPU o del modello probabilistico utilizzato. In questi casi, l'aggiunta di un'assert, anche quando non viene mai eseguita e anche quando viene rimossa completamente in modalità release, modifica il contesto di generazione del codice in modo sufficiente a produrre un risultato diverso, non perché l'assert alteri la logica dell'algoritmo, ma perché altera condizioni strutturali che l'algoritmo assume stabili. Questo fenomeno si manifesta in due ambiti distinti, sia negli algoritmi branchless basati su manipolazioni di bit e ordine delle istruzioni, che negli algoritmi randomizzati che dipendono da uno spazio di probabilità stabile.

# **Bit-hack branchless**

Gli algoritmi branchless basati su manipolazioni di bit rappresentano un caso in cui il comportamento del compilatore determina la correttezza e le prestazioni dell'algoritmo. Un esempio classico è la versione branchless di `min` e `max`, che utilizza operazioni aritmetiche e bitwise per evitare branch condizionali:

```c
int min_branchless(int a, int b) {
    int diff = a - b;
    int mask = diff >> 31;           // 0 se diff >= 0, -1 (0xFFFFFFFF) se diff < 0
    return b + (diff & mask);
}
```

Questo codice, compilato in modalità release, produce un percorso di esecuzione privo di branch, poiché la CPU esegue tutte le operazioni in modo lineare. La correttezza e le prestazioni dell'algoritmo dipendono da fattori come la latenza dello shift aritmetico, la disponibilità dei registri, la fusione delle micro-operazioni, l'ordine delle istruzioni generato dal compilatore e la decisione del compilatore di mantenere `diff` in un registro o di spillarlo nello stack. L'equilibrio che consente al bit-hack di funzionare correttamente è quindi sensibile a variazioni nel codegen.

L'aggiunta di un'assert nel sorgente modifica questo equilibrio:

```c
int min_branchless(int a, int b) {
    assert(a != INT_MIN);  // assert su a, non sul risultato della funzione
    int diff = a - b;
    int mask = diff >> 31;
    return b + (diff & mask);
}
```

In modalità release, l'assert viene rimossa, ma la sua presenza nel sorgente modifica il comportamento del compilatore durante l'analisi del flusso di controllo. Il compilatore può decidere di non mantenere `a` in un registro, poiché in modalità debug deve essere disponibile per la valutazione dell'assert. Questo può portare a uno spill nello stack, che modifica la latenza della sottrazione. Lo shift aritmetico su `diff`, che in precedenza poteva essere fuso con la sottrazione in una singola micro-operazione, può essere separato. La pressione sui registri cambia, e il compilatore può decidere di non inlinare una funzione helper che in precedenza veniva inlinata. L'ordine delle istruzioni nel binario cambia, e la predizione di branch su un'istruzione non correlata può essere influenzata dal nuovo layout della cache line.

Il risultato può essere che l'algoritmo non è più branchless, poiché il compilatore introduce un branch per gestire un caso che prima era trattato tramite bit-hack o che l'algoritmo rimane branchless ma produce un risultato errato, poiché il compilatore interpreta la logica del bit-hack come un pattern ottimizzabile e applica una trasformazione non prevista o ancora che l'algoritmo rimane corretto ma subisce un degrado significativo delle prestazioni, poiché il nuovo codegen introduce latenza aggiuntiva o riduce l'efficacia della pipeline.

Un caso documentato riguarda un report su StackOverflow in cui l'aggiunta di una `static_assert(sizeof(T) == 4)` modifica il percorso di compilazione di una classe non correlata. Il motivo è che l'analizzatore del compilatore C++ procede in più passate, e l'aggiunta della static_assert modifica l'ordine di parsing, portando a una scelta diversa nella specializzazione di un template. Nella fase di generazione del codice, il template viene specializzato in modo diverso, e il codegen di una funzione non correlata cambia, producendo un risultato diverso. Un altro caso vero riguarda una race condition nel sottosistema perf events del kernel Linux. La vulnerabilità dipende da una finestra temporale di pochi cicli di clock tra due operazioni. La presenza o assenza di meccanismi di debug come `CONFIG_DEBUG_PAGEALLOC`, `init_on_alloc`, page poisoning o KASAN modifica il timing, sposta gli indirizzi di memoria, cambia il layout del kernel text e altera la latenza di accesso a strutture dati condivise. Quando i meccanismi di debug sono attivi, il timing cambia e la finestra temporale non esiste più, rendendo l'exploit non praticabile. Quando i meccanismi di debug sono disattivati, il codice è più denso e più veloce, la finestra temporale si apre e l'exploit diventa praticabile. Questi esempi mostrano che la presenza di un'assert può modificare il comportamento del compilatore e della CPU in modo sufficiente a rendere sfruttabile o non sfruttabile una vulnerabilità, anche quando l'assert non viene mai eseguita.



# **Assert a caso e algoritmi che impazziscono**

Gli algoritmi randomizzati dipendono in modo diretto dalla stabilità dello spazio di probabilità che li governa, poiché la loro correttezza attesa, la loro complessità media e la forma delle strutture dati prodotte derivano dall'ipotesi che il generatore di numeri pseudocasuali venga interrogato in un ordine deterministico rispetto al flusso di esecuzione. Un treap di Aragon e Seidel, una skip list di Pugh, un quicksort randomizzato di Hoare, un randomized BST di Martínez e Roura o un algoritmo di Karger e Stein per il min‑cut assumono che il PRNG venga consultato in un punto preciso del codice, con un timing coerente e con un allineamento della memoria che non varia tra esecuzioni equivalenti. La presenza di un'assert, anche quando non interroga direttamente il PRNG, può modificare questo equilibrio, poiché altera il numero di cicli di clock necessari per raggiungere il punto in cui il PRNG viene consultato, modifica l'allineamento della memoria, cambia il comportamento del prefetch della CPU e altera la correlazione tra gli accessi alla memoria e lo stato interno del generatore.

Un treap compilato con un'assert che verifica un invariante della rotazione produce una sequenza di interrogazioni del PRNG diversa rispetto alla build senza assert, poiché il timing relativo tra le operazioni di rotazione e la consultazione del PRNG cambia. La forma dell'albero risultante può differire in modo significativo, e la profondità media può discostarsi dalla complessità attesa O(log n). Un test che verifica la proprietà probabilistica della profondità media può passare in modalità debug e fallire in modalità release, oppure il comportamento opposto può verificarsi, senza che il debugger fornisca alcuna indicazione utile. Il PRNG viene interrogato lo stesso numero di volte, ma la correlazione tra le interrogazioni e lo stato della struttura dati è diversa, e la distribuzione risultante cambia. Una skip list randomizzata utilizzata in un sistema di deduplicazione dei dati può produrre layout diversi della struttura quando compilata con e senza assert, poiché la presenza dell'assert modifica il timing relativo tra l'inserimento dei nodi e la consultazione del PRNG. Questo può portare a fingerprint diversi e a hash diversi sugli stessi dati, e un sistema che salva e ricarica la skip list da disco può fallire nel round‑trip perché la forma della struttura non è più stabile tra build equivalenti. Gli algoritmi di tabulation hashing, come quelli di Carter e Wegman, Zobrist hashing, simple tabulation o twisted tabulation, dipendono dalla disposizione delle tabelle precalcolate in memoria. La distribuzione finale dei valori hash dipende dall'allineamento delle tabelle, dal padding inserito dal compilatore, dalla disposizione delle sezioni del binario e dal comportamento del prefetch della CPU. Un'assert che verifica un invariante della tabella può modificare il codegen in modo tale che le tabelle vengano allocate in sezioni diverse della memoria, con allineamenti diversi e con un pattern di accesso differente. Questo modifica la correlazione tra gli indici utilizzati e i valori letti, e la distribuzione degli hash prodotti cambia senza che la funzione hash abbia modificato la propria logica. Uno studio che verifica le proprietà statistiche di un tabulation hash tramite strumenti come *dieharder* può rilevare differenze tra la distribuzione prodotta in modalità debug e quella prodotta in modalità release, poiché il numero di bit significativi che superano i test di casualità può variare. Il PRNG viene interrogato lo stesso numero di volte, ma la correlazione tra le interrogazioni e lo stato della memoria è diversa, e la distribuzione risultante non coincide. La causa è proprio la presenza di un'assert che modifica il contesto di esecuzione in modo sufficiente a cambiare la distribuzione statistica dei risultati,pazzesco vero?


# **Il protocollo di isolamento e hardening**

Il comportamento degli algoritmi sensibili al contesto di compilazione può essere reso misurabile tramite un insieme di procedure che isolano le variabili rilevanti, controllano l'ambiente di esecuzione e quantificano le differenze tra build equivalenti. Questo protocollo non elimina la fragilità intrinseca degli algoritmi, ma consente di individuare con precisione i punti in cui l'equilibrio operativo viene alterato.


## **Prima mossa: build parallele sincronizzate**

Una strategia efficace consiste nell'eseguire in produzione una build release standard e, in parallelo, una build release identica ma con assert attive tramite un flag come `-DDEBUG_ASSERTS`. Le due build devono essere eseguite simultaneamente sullo stesso carico di lavoro, in modo da confrontare non solo i risultati finali, ma anche le distribuzioni statistiche degli output intermedi, le collisioni degli hash, i tempi di latenza e i pattern di accesso alla cache. Divergenze sistematiche tra le due build indicano la presenza di micro‑effetti introdotti dalle assert, che modificano il comportamento del compilatore o della CPU in modo sufficiente a produrre differenze osservabili.


## **Seconda mossa: matrici di test**

Una suite di test che abilita e disabilita assert in punti diversi del codice, una per volta o in combinazioni controllate, consente di identificare quali assert influenzano il comportamento degli algoritmi randomizzati. Ogni configurazione deve essere compilata come variante separata, e i test devono misurare la distribuzione degli output tramite strumenti statistici come test chi‑quadrato o Kolmogorov‑Smirnov. L'obiettivo non è verificare l'uguaglianza bit‑a‑bit, ma rilevare variazioni nella varianza, nello skew o nella coda della distribuzione, poiché tali variazioni indicano un cambiamento nel timing relativo delle interrogazioni al PRNG o nell'allineamento della memoria.


## **Terza mossa: replay deterministico e tracce di esecuzione**

Quando viene rilevata una divergenza, è utile catturare lo stato microarchitetturale nel momento in cui si manifesta. Strumenti come `perf record`, `perf script` o `llvm-mca` consentono di registrare valori dei registri, spill dello stack, cache miss e branch mispredictions. Confrontare le tracce tra la versione con assert e quella senza permette di individuare il punto esatto in cui il codegen diverge, poiché differenze nei registri allocati, nelle micro‑operazioni fuse o nei percorsi di esecuzione rivelano l'origine della variazione statistica.


## **Quarta mossa: allineamento e padding esplicito**

Per algoritmi sensibili all'allineamento della memoria, come tabulation hashing, è utile fissare l'allineamento delle tabelle tramite direttive del compilatore o del linker, come `__attribute__((aligned(64)))` o sezioni dedicate nei linker script. Questo riduce la libertà del compilatore di spostare le tabelle in memoria in risposta a cambiamenti nel codegen, stabilizzando il pattern di accesso e riducendo la variabilità della distribuzione degli hash.


## **Quinta mossa: UB benigno isolato**

Quando un bit‑hack utilizza forme di undefined behavior intenzionale, come aritmetica modulare su interi signed o shift che estraggono bit di segno, è utile isolare il codice in un modulo separato compilato con opzioni come `-fno-strict-overflow` o `-fwrapv`. Questo impedisce che modifiche nel resto del progetto influenzino il codegen del modulo, stabilizzando il comportamento dell'algoritmo e riducendo la variabilità introdotta dalle assert.


## **Sesta mossa: sanitizers e strumenti dinamici**

L'integrazione di strumenti come ASan e UBSan nelle build di test consente di rilevare spill, aliasing e forme di undefined behavior che possono essere mascherate dalla presenza delle assert. Eseguire i test con ASan attivo permette di identificare punti in cui l'assert introduce spill o modifica la pressione sui registri, poiché i report evidenziano differenze tra debug e release che non emergono tramite test funzionali.


## **Settima mossa: suite statistiche nella CI**

L'integrazione di suite statistiche come *dieharder*, *TestU01* o *PractRand* nella pipeline CI consente di rilevare immediatamente variazioni nella distribuzione prodotta da un PRNG o da una funzione hash. Ogni modifica ai flag di compilazione o alla configurazione delle assert deve essere accompagnata da una verifica statistica, poiché differenze nella distribuzione indicano un cambiamento nel comportamento del compilatore o della CPU.


## **Ottava mossa: da finire**

qui c'è una chicca che fa "letteramente paura" ma letteralmente come un fantasma, ma è da finire...

## **Nona mossa: determinismo di processo**

Una modalità di esecuzione deterministica che fissa l'allocazione dei registri, il layout dello stack, la frequenza della CPU e il core di esecuzione consente di ridurre la variabilità introdotta dal sistema operativo o dall'hardware. In questo ambiente controllato, le differenze tra debug e release devono derivare esclusivamente dal compilatore, e la presenza di assert non dovrebbe alterare la distribuzione statistica degli algoritmi.


## **Decima mossa: test di proprietà su invarianti formali**

Testare invarianti matematiche indipendenti dal codegen, come la proprietà di heap delle priorità casuali in un treap, consente di distinguere tra errori dell'algoritmo e variazioni introdotte dal compilatore. Se l'invariante fallisce, il problema è nell'algoritmo; se l'invariante è rispettato ma le prestazioni cambiano, il problema è nel codegen.

## **Undicesima mossa: isolamento dell'algoritmo fragile**

Separare il codice fragile dal resto del progetto e circondarlo con un'API stabile consente di evitare che modifiche esterne influenzino il codegen interno. Le assert devono essere collocate all'esterno dell'algoritmo, come verifiche di precondizione o postcondizione, in modo che il compilatore non modifichi la struttura interna dell'algoritmo in risposta alla loro presenza.

Così si chiude questa sezione che però resta aperta, è uno dei punti da finire di questo testo...

# **Le assert e gli algoritmi sensibili al contesto di esecuzione**

Esiste una categoria di algoritmi in cui gli effetti indiretti delle assert non sono un dettaglio teorico da conferenza, ma diventano un fattore pratico che può cambiare i risultati. Questi algoritmi dipendono in modo critico dal **contesto esatto** in cui vengono eseguiti e tutto può cambiare il risultato, i layout di memoria, l'ordine delle istruzioni generato dal compilatore, comportamento della cache e pattern di branch della CPU. Tra questi rientrano, senza sorpresa, **funzioni hash non crittografiche**, **generatori di numeri pseudocasuali non crittografici**, **strutture dati che usano randomizzazione interna**, **algoritmi di compressione sensibili ai pattern di memoria** e codice **branchless** progettato per proprietà di execution constant‑time.

Il fatto è che l'algoritmo astratto resta lo stesso sulla carta, ma la sua implementazione è concreta. Le assert, pur nate per illuminare invarianti, agiscono come piccoli registi invisibili che sussurrano al compilatore... _"qui succede questo"_, e il compilatore riscrive la scena di conseguenza. Il risultato è che due esecuzioni dello stesso sorgente, una con assert attive e una senza, possono raccontare due storie diverse.

**Esempi concreti e un po' maliziosi**

- **Tabulation hashing e allineamento**  
  Una tabella di lookup spostata di poche cache line cambia il pattern di miss e hit. Un'assert che mantiene in vita una variabile o che impedisce al compilatore di spostare la tabella può trasformare una distribuzione di hash “rumorosa” in una distribuzione “ordinata”.

- **PRNG e ordine delle chiamate**  
  Un'assert che legge o scrive qualcosa tra due chiamate al generatore cambia l'ordine delle chiamate stesse. Un test statistico che passava in debug fallisce in release.

- **Branchless e timing constant‑time**  
  Il codice branchless punta a un profilo di esecuzione prevedibile. Un'assert che introduce una lettura del clock o mantiene in vita una variabile altera il timing e può rompere la promessa di constant‑time.

- **Compressione e pattern di memoria**  
  Algoritmi che sfruttano pattern ripetuti nella memoria (sliding windows, LZ‑like) vedono le loro decisioni influenzate da come il compilatore dispone i buffer. Un'assert che cambia l'allocazione o la durata di una variabile altera i confini delle finestre e quindi il risultato della compressione.

- **Randomized data structures**  
  Strutture come skiplist o treap dipendono dalla sequenza di numeri casuali e dall'ordine delle operazioni. Un'assert che incrementa un contatore o che forza un accesso modifica la sequenza e può trasformare una struttura bilanciata in una scaletta.


Le assert influenzano le assunzioni che il compilatore usa per ottimizzare e anche quando le assert vengono rimosse in release, il compilatore ha già preso decisioni basate sulla loro presenza durante la fase di ottimizzazione. Il binario finale porta con sé l'eco di quelle decisioni, il sorgente rimane lo stesso, ma il comportamento osservabile cambia. Quindi trattare un algoritmo sensibile come se fosse una formula matematica pura è come aspettarsi che una ricetta dia lo stesso risultato se cambi forno, altitudine e tipo di farina senza adattare i tempi di cottura. Le assert sono come la saliera in più che tieni sul tavolo che a volte non serve ma a volte sono utili, e a volte può cambiare totalmente il risultato se quancuno lo usa male.


# **Hash non crittografici**

Funzioni hash come MurmurHash di Austin Appleby, xxHash di Yann Collet, CityHash di Google, FNV di Fowler‑Noll‑Vo e Jenkins di Bob Jenkins sono progettate per ottenere un buon compromesso tra velocità e distribuzione statistica, e vengono utilizzate in contesti come hash table, fingerprinting, deduplicazione e partition routing. Dal punto di vista matematico, una funzione hash riceve una sequenza di byte e produce un valore numerico. Dal punto di vista del codice macchina, una funzione hash è una sequenza di letture dalla memoria, operazioni aritmetiche, XOR, rotazioni e loop il cui numero di iterazioni dipende dalla lunghezza dell'input. Le prestazioni dipendono dalla capacità del processore di prefetchare i dati, mantenere i registri disponibili, vettorizzare il loop principale ed evitare branch mispredictions.

Aggiungere un'assert come `assert(input != NULL && len > 0)` all'inizio di una funzione come `MurmurHash3_x64_128` modifica il prologo della funzione, cambia la dimensione dello stack frame, sposta le variabili locali e può impedire l'inlining nel chiamante se la dimensione stimata della funzione supera la soglia prevista dal compilatore. Il risultato numerico dell'hash rimane identico, ma il throughput può cambiare in modo significativo, con variazioni che possono raggiungere il 10‑20% in sistemi che eseguono milioni di hash al secondo. In contesti multi‑thread con SMT, l'aggiunta di poche istruzioni può modificare il numero di micro‑operazioni in volo nella pipeline, alterare la competizione per le risorse condivise tra thread e produrre variazioni di performance in thread diversi da quello in cui l'assert è presente. Una pratica comune tra gli sviluppatori di funzioni hash ad alte prestazioni consiste nel profilare il codice tramite strumenti come `perf` o `tracy` utilizzando due binari distinti, uno con assert attive per verificare i test vector e uno senza assert per misurare le prestazioni reali. Le due misurazioni differiscono sempre, e la differenza non è mai trascurabile.


# **PRNG non crittografici**

Generatori pseudocasuali come Mersenne Twister, Xorshift, PCG e LCG producono sequenze deterministiche dato un seed iniziale e avanzano il proprio stato interno a ogni chiamata. Questa proprietà è essenziale per simulazioni Monte Carlo, test statistici e algoritmi randomizzati che richiedono riproducibilità. Un'assert che interroga il PRNG modifica l'ordine di consumo dei valori generati, alterando la sequenza prodotta.

```python
import random

rng = random.Random(42)

def estrai():
    valore = rng.random()
    assert rng.random() > 0  # consuma un altro valore!
    return valore
```

In questo esempio, l'assert verifica una proprietà sempre vera, ma consuma un valore del PRNG. La sequenza generata in modalità debug diventa `r1, r3, r5, ...`, mentre in modalità release diventa `r1, r2, r3, ...`. Un esperimento scientifico che dichiara `seed = 42` produce risultati diversi tra debug e release, poiché il numero di interrogazioni al PRNG dipende dalla presenza dell'assert. Questo problema è particolarmente grave nelle simulazioni Monte Carlo, dove la legge dei grandi numeri stabilizza l'aggregato ma le singole traiettorie dipendono dall'ordine esatto delle interrogazioni al PRNG. Un paper che dichiara un seed fisso per riproducibilità sta implicitamente dichiarando anche il numero di assert presenti nel percorso di esecuzione. La soluzione consiste nel garantire che il PRNG non venga mai interrogato all'interno di un'assert. Se è necessario verificare una proprietà su un valore generato, il valore deve essere estratto prima, salvato in una variabile e utilizzato sia per la logica dell'algoritmo sia per la verifica tramite assert.


### Skip list

Una skip list di William Pugh basa la sua complessità attesa O(log n) sulla scelta randomizzata del livello di ogni nodo inserito. La decisione *quale livello assegnare a questo nodo* avviene tramite consultazione del PRNG, e la struttura risultante dipende dall'ordine di consultazione del PRNG. Lo stesso vale per treap (binary search tree con priorità random), randomized binary search tree di Martínez e Roura, cuckoo hash table con seed randomizzato per le due hash function, HyperLogLog con seed per la hash function.

In tutti questi casi, un'assert che chiama il PRNG o che fa qualcosa che indirizzano il compilatore a riordinare la sequenza di chiamate al PRNG (per esempio assert su risultati parziali che cambiano il timing del codegen) produce strutture dati con shape diversa fra debug e release. Le conseguenze attraversano vari piani, la performance cambia, perché la shape determina le profondità attese e i tempi di accesso. La riproducibilità si rompe, perché un test che salva e ricarica la struttura dati trova layout diversi fra debug e release. La correttezza dei test di equivalenza vacilla, perché due esecuzioni dell'algoritmo sugli stessi dati con la stessa seed dovrebbero produrre strutture identiche, e mai lo fanno.

### Probing in hash table aperta

Le hash table a indirizzamento aperto sono campi di battaglia dove ogni probe è un passo di danza e ogni collisione è un piccolo incidente diplomatico. Il pattern di accesso alla memoria dipende dal load factor, dalla distribuzione delle chiavi e dalla funzione di hash, quando il load factor si avvicina alla soglia di rehash, il numero medio di probe per lookup esplode come una pentola a pressione dimenticata sul fuoco, e le prestazioni precipitano. Mettere un'`assert` dentro la zona critica di lookup è come piazzare un cameriere in mezzo alla cucina durante il servizio. L'`assert` consuma cicli macchina in debug e scompare in release, ma nel frattempo può costringere il compilatore a cambiare strategia. La presenza dell'`assert` può impedire l'inlining della funzione di hash, spostare variabili fuori dal registro, aumentare la dimensione del frame e rompere l'unrolling del loop di probing. Tutte queste modifiche alterano l'ordine delle istruzioni e il pattern di accesso alla memoria.

Il branch predictor, che è il piccolo oracolo della CPU, si nutre di storia e più bit di branch history ha a disposizione, meglio predice. Daniel Lemire ha mostrato che l'unrolling dei loop aiuta il predittore perché fornisce più “contesto” utile, trasformando rumore in segnali predicibili. Un'`assert` piazzata dentro il loop di probing inibisce l'unrolling che il compilatore avrebbe fatto, e il branch predictor si ritrova con meno informazioni utili e così la predizione peggiora, i mispredicted branch aumentano e la pipeline della CPU si riempie di scartoffie inutili. Così la lookup diventa più lenta a causa dell'`assert` che ha cambiato il modo in cui il compilatore e la CPU collaborano. La regola da seguire è quella di tenere le assert fuori dal loop di probing, isolare le verifiche di rappresentazione in punti non critici e misurare sempre le prestazioni sia con che senza assert.

# **Compressione LZ77, LZ4 e finestre scorrevoli**

Gli algoritmi di compressione basati su finestre scorrevoli, come LZ77 di Lempel‑Ziv, LZ4 di Yann Collet, LZSS e deflate di zlib, elaborano l'input byte per byte cercando corrispondenze nella finestra precedente e producono un output composto da letterali e coppie offset‑length. La correttezza dell'output è deterministica e dipende esclusivamente dall'input, ma le prestazioni dipendono in modo critico dal comportamento del compilatore, dal layout della memoria, dalla vettorizzazione del loop principale e dal pattern di accesso alla finestra. La hash table interna utilizzata per individuare i match nella finestra scorrevole è estremamente sensibile al modo in cui il compilatore gestisce le variabili locali, all'ordine delle istruzioni e alla pressione sui registri. L'aggiunta di un'assert che verifica un invariante interno, come `assert(finestra.posizione < FINESTRA_SIZE)`, può modificare il codegen in modo sufficiente a disattivare la vettorizzazione del loop di comparazione byte‑per‑byte. Implementazioni come LZ4 utilizzano istruzioni SIMD AVX2 o NEON per confrontare otto o sedici byte alla volta, e la presenza di un'assert nel corpo del loop può impedire al compilatore di applicare la vettorizzazione, poiché l'assert introduce un punto di controllo che interrompe l'analisi del loop. Il risultato è una riduzione drastica delle prestazioni, con throughput che può scendere da 3 GB/s a 800 MB/s, producendo un divario di quattro volte nonostante l'algoritmo rimanga logicamente identico. La situazione è ancora più critica nei sistemi che utilizzano LZ4 per la decompressione in tempo reale, come pipeline di log shipping o sistemi di replica che richiedono latenze prevedibili. La decompressione di LZ4 è spesso un parametro di SLA, e una singola assert lasciata nel codice di release, anche se marcata come `debug_assert!`, può modificare il codegen del decompressore in modo sufficiente a superare i limiti di latenza previsti. I test funzionali non rilevano il problema, poiché l'output rimane corretto, ma i test prestazionali falliscono perché la pipeline non riesce a mantenere il throughput richiesto. Il comportamento osservato deriva dalla sensibilità del codegen alle modifiche introdotte dalle assert infatti la presenza dell'assert modifica la dimensione del frame, altera la disposizione delle variabili locali, cambia la pressione sui registri e impedisce al compilatore di applicare ottimizzazioni come la vettorizzazione o l'unrolling del loop. La conseguenza è un cambiamento significativo delle prestazioni, anche se l'algoritmo rimane deterministico e l'output non cambia.

# **Branchless e constant‑time**

Il codice constant‑time utilizzato nelle implementazioni crittografiche rappresenta uno dei contesti in cui la perturbazione introdotta dalle assert raggiunge un livello critico, poiché la proprietà fondamentale di tali implementazioni consiste nel garantire che il tempo di esecuzione non dipenda dai dati segreti processati. Le implementazioni constant‑time di algoritmi come AES, Curve25519 o RSA blinded ottengono questa proprietà eliminando branch condizionali basati su dati sensibili e sostituendoli con operazioni branchless come `CMOV`, operazioni bitwise e selettori aritmetici.

```c
// branchless, constant-time
uint32_t select_ct(uint32_t condizione, uint32_t a, uint32_t b) {
    uint32_t maschera = -condizione;   // 0 oppure 0xFFFFFFFF
    return (a & maschera) | (b & ~maschera);
}
```

Una versione equivalente che utilizza `if (condizione) return a; else return b;` può essere compilata in modi diversi a seconda del compilatore, del livello di ottimizzazione e dell'architettura target, e in alcuni casi il compilatore introduce un branch condizionale che rende il tempo di esecuzione dipendente dal valore della condizione. Questo comportamento compromette la proprietà constant‑time e rende l'implementazione vulnerabile ad attacchi basati sulla misura dei tempi.

L'aggiunta di un'assert all'interno di codice constant‑time può modificare il codegen in modo sufficiente a reintrodurre branch condizionali o a modificare la disposizione delle istruzioni, alterando la latenza osservabile. In Rust, una `debug_assert!(condizione_sui_segreti)` introduce in modalità debug un branch basato su dati sensibili, e un attaccante che misura i tempi di esecuzione del binario di debug può estrarre informazioni che il binario di release non rivela. In modalità release l'assert viene rimossa e la proprietà constant‑time viene ripristinata, ma i test eseguiti in debug non rappresentano più il comportamento del codice in produzione, poiché misurano un'implementazione che non è constant‑time. Le linee guida della crittografia applicata, come quelle del progetto BearSSL e di libsodium, raccomandano di evitare completamente l'uso di assert all'interno del codice constant‑time e di eseguire i test funzionali su build prive di assert, verificando la proprietà constant‑time tramite strumenti dedicati come *dudect* di Reparaz et al. o *ctgrind* di Adam Langley. Questi strumenti analizzano il comportamento temporale del binario e rilevano variazioni statisticamente significative che indicano la presenza di branch o percorsi di esecuzione dipendenti dai dati.


# **La regola che mette tutto in ordine**

Una regola pratica attraversa tutti i domini in cui il comportamento del codice dipende da proprietà fini del contesto di esecuzione, come layout della memoria, timing, codegen, branch prediction, cache o ordine di consultazione di stato esterno. Il codice sensibile a tali proprietà deve essere trattato come una componente isolata rispetto alle assert, e le assert devono essere collocate esclusivamente all'esterno della componente, mai all'interno. Un test funzionale su una funzione hash deve invocare la funzione e verificare l'output, senza inserire assert nel loop interno che esegue le operazioni critiche. Una verifica di proprietà su un PRNG deve generare i valori con un seed fissato, salvarli e verificare le proprietà desiderate, senza interrogare il PRNG all'interno di un'assert. Una verifica su un algoritmo di compressione deve comprimere e decomprimere l'input e verificare che il round‑trip sia corretto, senza inserire controlli all'interno del match‑finder o del loop di comparazione.

Questa separazione consente di preservare il contesto di esecuzione necessario al codice sensibile e permette al programmatore di aggiungere verifiche senza alterare proprietà che non intende modificare. Il risultato è un sistema in cui il comportamento degli algoritmi fragili rimane stabile e prevedibile, mentre le assert svolgono il loro ruolo diagnostico senza interferire con la semantica o le prestazioni.


# **Assert nel mondo asincrono**

In ambienti asincroni il concetto di stato corrente cambia perché il flusso di controllo non scorre più su un'unica linea temporale ma attraversa interleaving con altri task e di conseguenza un'`assert` va interpretata come una verifica sullo stato osservabile al momento della ripresa del task, non come una garanzia sullo stato che esisteva prima della sospensione. Tra un `await` e il successivo altri task possono aver modificato variabili condivise, quindi leggere una variabile prima della sospensione e verificarla dopo la ripresa non prova che nessuno l'abbia cambiata. Questo spiega perché le `assert` possono essere utili come rilevatori a basso costo di race condition, purché siano progettate per osservare uno stato coerente rispetto al punto di ripresa, ma per proteggere sezioni critiche servono mutex asincroni, atomici o pattern di snapshot immutabili. Inoltre un'`assert` che scatta dentro un task non osservato può essere silenziata da una promise non gestita o da un handler che consuma l'errore, lasciando il problema nascosto fino all'analisi dei log, per questo è fondamentale propagare o loggare esplicitamente le rejection e non affidarsi al comportamento implicito del runtime. Infine, per ridurre le sorprese è buona pratica distinguere chiaramente tra verifiche diagnostiche usate solo in debug e controlli runtime che devono essere sempre eseguiti, testare sia scenari interleaved sia sequenziali e adottare pattern che rendano la visibilità dello stato esplicita e riproducibile.

# **Pattern utili**

## **Asserire dopo l'await sullo stato aggiornato**

```javascript
async function pagaOrdine(ordine) {
    assert(ordine.stato === "creato");
    const pagamento = await chiamaGateway(ordine);
    const ordineAggiornato = await ricaricaOrdine(ordine.id);
    assert(ordineAggiornato.stato === "creato",
        `stato inatteso ${ordineAggiornato.stato} dopo gateway`);
    ...
}
```

Immagina di essere uno chef che prepara una torta a strati in una cucina affollata, che fai? Prima di mettere la glassa controlli che il primo strato sia ancora intatto, poi esci un attimo per prendere lo zucchero e, al ritorno, ricontrolli che nessuno abbia spostato la torta. In ambienti asincroni il `await` è proprio quel momento in cui lasci la cucina tra una sospensione e la ripresa, altri cuochi (task) possono aver toccato gli ingredienti e l'`assert` dopo l'`await` è la fotografia del piatto al momento in cui torni al banco.

Questo pattern garantisce che la verifica venga effettuata sullo stato effettivamente valido nel momento della ripresa, evitando di fidarsi di una ricetta mentale che non tiene conto delle mani altrui. Se il secondo `assert` fallisce qualcuno probabilmente ha rimescolato gli ingredienti mentre eri via. In cucina come nel codice, la soluzione è che o si protegge la torta con una campana (mutex, token di cancellazione, snapshot immutabili) oppure si accetta che il controllo serva solo a rilevare che qualcosa è cambiato e si reagisce di conseguenza (retry, rollback, escalation).

## **Token di cancellazione**

```python
async def lavoro(ctx, dati):
    assert not ctx.cancelled()
    risultato = await elabora(dati)
    assert not ctx.cancelled(), "task cancellato durante elabora"
    return risultato
```

Stai preparando un piatto su richiesta, ma il cliente può cambiare idea e annullare l'ordine mentre sei impegnato a flambare. Le `assert` prima e dopo l'operazione asincrona sono come controllare che il cliente sia ancora seduto al tavolo prima di finire il piatto. Se il cliente se n'è andato, non ha senso continuare a sprecare ingredienti pregiati. In pratica, l'`assert` iniziale evita di iniziare un lavoro inutile, quella finale evita di consegnare un risultato che nessuno vuole più. Questo pattern è particolarmente utile quando l'elaborazione è costosa o produce effetti collaterali (scritture su DB, invio di notifiche). Se il task viene cancellato, meglio fermarsi e restituire un errore controllato piuttosto che lasciare dietro di sé una cucina sporca e ordini incompleti.

## **Promise non gestite e rilevazione degli errori**

```javascript
process.on('unhandledRejection', (reason) => {
    console.error('AssertionError in promise non gestita', reason);
    process.exit(1);
});
```

Una promise non gestita è come un piatto lasciato sul bancone senza che nessuno lo ritiri, può andare a male, attirare mosche e rovinare la reputazione del ristorante. Un'`assert` che fallisce dentro una promise non osservata rischia di restare invisibile, come un ingrediente bruciato nascosto sotto la salsa. Installare un handler globale per le rejection è come avere un maître che controlla il passaggio dei piatti e se qualcosa va storto, lo segnala subito e ferma il servizio prima che il danno si propaghi. Colsì gli errori non evaporano nell'etere, ma vengono trasformati in allarmi rumorosi che costringono a intervenire. In una cucina ben gestita non si lascia mai un piatto incustodito e in un sistema asincrono non si lascia mai una promise senza gestore.

### Un tocco bizzarro ma pratico per la tua cucina asincrona

Pensa alle `assert` come a piccoli post‑it colorati attaccati ai piatti... "controlla che il cliente sia ancora qui", "non finire se il forno è spento", "se il piatto è stato toccato, rifallo". Sono utili ma non sostituiscono le procedure di cucina quindi usale per rilevare anomalie, non per fare il lavoro che spetta ai meccanismi di sincronizzazione e gestione degli errori.

In conclusione, cucina con cura, metti le `assert` dove servono per verificare lo stato al ritorno dal banco, proteggi le sezioni critiche quando necessario, e non lasciare mai una promise incustodita sul bancone. Così il tuo ristorante asincrono servirà piatti coerenti, caldi e senza sorprese. Bon appétit e buon debugging.


## **Reentrancy e invarianti degli attori**

```python
class CodaLavoro:
    async def processa(self, msg):
        self._check_rep()
        risultato = await self._chiama_servizio(msg)
        self._check_rep()
        self._aggiorna(msg, risultato)
        self._check_rep()
```

In un modello a attori, un metodo asincrono può essere interrotto da altri messaggi elaborati dallo stesso attore, e un'assert che verifica l'invariante di rappresentazione dopo ogni sospensione consente di rilevare violazioni introdotte da interleaving non previsto.


# **Race condition e ordering**

Le race condition tra task asincroni sono difficili da individuare, e le assert collocate nei punti critici possono far emergere il problema vicino alla sua origine.

```python
class Contatore:
    def __init__(self):
        self._n = 0
        self._busy = False

    async def incrementa(self):
        assert not self._busy, "race su Contatore.incrementa"
        self._busy = True
        valore = self._n
        await asyncio.sleep(0)
        self._n = valore + 1
        self._busy = False
```

Il pattern del flag `busy` rappresenta un esempio classico di falsa mutua esclusione, poiché la sospensione introdotta da `await asyncio.sleep(0)` consente ad altri task di intervenire tra la lettura e la scrittura dello stato. La prima race condition fa fallire l'assert, rendendo immediatamente visibile un problema che altrimenti si manifesterebbe in modo intermittente e difficile da diagnosticare.

### Async in Python

`asyncio` mescola coroutine in un singolo thread, quindi le race fra coroutine vivono ai punti di `await`. L'idea di un *check_rep dopo ogni await* si applica con precisione chirurgica proprio perché i punti di sospensione sono visibili nel codice.

# **Async in Rust**

Rust applica un modello di esecuzione asincrono che mantiene un livello di rigore superiore rispetto a molti altri linguaggi, poiché i trait `Send` e `Sync` definiscono in modo statico quali tipi possono attraversare i confini tra thread e quali tipi possono essere condivisi in sicurezza tra più contesti di esecuzione. Le `debug_assert!` utilizzate all'interno dei futures rimangono strumenti validi per verificare invarianti locali, con il vantaggio aggiuntivo che la macchina a stati generata dal compilatore preserva le variabili locali attraverso i punti di sospensione introdotti dagli `.await`, garantendo che un'assert collocata prima di un `.await` si riferisca a un valore che rimane immutato durante la sospensione.

La semantica del modello asincrono di Rust implica che le variabili locali catturate nella macchina a stati vengano memorizzate nello stack frame del future, e quindi il loro valore rimanga stabile tra una sospensione e la successiva, mentre gli stati esterni come mutex, RwLock o strutture condivise possono essere modificati da altri task durante la sospensione. Un'assert collocata dopo un `.await` deve quindi essere interpretata come una verifica sullo stato osservabile nel momento della ripresa, e non come una verifica sullo stato precedente, poiché altri task possono aver modificato i dati condivisi nel frattempo. Questo comportamento rende Rust particolarmente adatto a utilizzare assert come strumenti di diagnosi nelle regioni asincrone, poiché la distinzione tra stato locale preservato e stato esterno mutabile è esplicita e verificabile a tempo di compilazione. Tuttavia, la presenza di `debug_assert!` può comunque influenzare il codegen del future, poiché la macchina a stati generata dal compilatore può assumere una forma diversa in presenza di assert, modificando la disposizione delle variabili, la dimensione del frame e il comportamento dell'ottimizzatore. Le assert non modificano la semantica del modello asincrono, ma possono alterare il layout della macchina a stati, e quindi influenzare il comportamento microarchitetturale del codice risultante.


### Async in JS, callback hell incluso

Nel mondo callback la regola d'oro suona così, asserisci nel callback ciò che assumi al momento della chiamata, e ricorda che le variabili catturate per closure hanno il valore di adesso, mica di quando hai registrato il callback.

```javascript
function caricaUtente(id, cb) {
    db.find(id, (err, utente) => {
        assert(err || utente, "callback chiamata senza dati e senza errore");
        if (err) return cb(err);
        cb(null, utente);
    });
}
```

# **Modelli di executor**

Comprendere il modello di esecuzione utilizzato dal runtime asincrono è essenziale per determinare dove collocare le assert e quale significato operativo esse assumano, poiché ogni modello definisce un insieme diverso di garanzie sullo scheduling, sulla concorrenza e sulla visibilità dello stato condiviso.


## **Single‑threaded event loop**  

*(Node.js, browser, Python asyncio)*

In un event loop a thread singolo, esiste una sola unità di esecuzione che alterna le coroutine esclusivamente nei punti di sospensione introdotti dagli `await`, e ogni segmento di codice compreso tra due `await` viene eseguito senza interruzioni dal punto di vista delle altre coroutine. Le race condition possibili si manifestano esclusivamente nei punti di sospensione, e un'assert collocata immediatamente dopo un `await` verifica lo stato osservabile in un confine temporale ben definito, poiché nessun altro codice può intervenire durante l'esecuzione del segmento precedente.


## **Multi‑threaded scheduler**

*(Rust Tokio multi‑thread, Java virtual threads, Go goroutine)*

In un modello multi‑threaded, più worker eseguono task in parallelo e i task possono migrare tra worker diversi, con la conseguenza che qualsiasi accesso a memoria condivisa può essere soggetto a race condition. Le assert che verificano invarianti su stato condiviso hanno significato operativo soltanto quando vengono collocate all'interno di sezioni protette da meccanismi di sincronizzazione come lock, operazioni atomiche o canali, poiché al di fuori di tali sezioni non esiste alcuna garanzia sulla stabilità dello stato tra due istruzioni consecutive.


## **Actor model**  

*(Akka, Erlang, attori di Swift, Pony)*

Nel modello ad attori, ogni attore possiede uno stato privato e processa un messaggio per volta, garantendo che nessun altro thread possa modificare lo stato durante l'elaborazione del messaggio corrente. Le assert che verificano l'invariante di rappresentazione trovano in questo modello un contesto particolarmente adatto, poiché possono essere collocate all'interno della chiusura di elaborazione del messaggio con la garanzia che lo stato non venga modificato da altri attori durante l'esecuzione del metodo.


## **Cooperative scheduler con suspension points espliciti**  

*(Lua coroutines, Python generator‑based coroutines)*

In un modello cooperativo, il programmatore decide esplicitamente quando cedere il controllo tramite punti di sospensione definiti manualmente, e questa caratteristica rende le assert sugli invarianti particolarmente efficaci, poiché il programmatore conosce con precisione i punti in cui il controllo può essere ceduto e può collocare le assert in modo da verificare lo stato in momenti deterministici e facilmente analizzabili.

# **Assert nel mondo distribuito**

Quando un sistema viene suddiviso in componenti che operano su macchine diverse e comunicano tramite protocolli di rete, le assert assumono un ruolo diverso rispetto ai sistemi monolitici, poiché il loro fallimento non interrompe direttamente il flusso di controllo del chiamante e deve essere propagato attraverso meccanismi di comunicazione remota. In un sistema distribuito, lo stato globale non risiede in un singolo nodo, e gli invarianti devono essere classificati come locali o globali, con regole operative differenti per ciascuna categoria.


# **Cosa cambia rispetto al singolo processo**

Un'assert che fallisce in un servizio remoto non interrompe l'esecuzione del chiamante, ma viene trasformata in un errore HTTP o RPC che deve essere trasportato, gestito e registrato in modo esplicito. Lo stato globale del sistema è distribuito tra nodi diversi, e gli invarianti devono essere definiti in modo distinto per lo stato locale e per lo stato globale, poiché i due livelli seguono modelli di coerenza differenti. L'idempotenza diventa una proprietà essenziale, poiché una richiesta che verifica una condizione e modifica lo stato deve essere in grado di sopravvivere a retry, duplicazioni e riordini introdotti dalla rete. Le partizioni di rete rappresentano condizioni reali e frequenti, e un'assert che dipende dalla raggiungibilità di un altro servizio verifica una proprietà che può essere temporaneamente non valida, anche se il sistema nel suo complesso rimane corretto.


# **Invarianti locali e globali**

Gli invarianti locali, che riguardano lo stato interno di un servizio come la sua memoria o il suo database, possono essere verificati tramite assert, poiché il servizio possiede una visione coerente del proprio stato. Gli invarianti globali, che coinvolgono più servizi come la somma dei saldi mantenuti da due microservizi diversi, devono essere verificati tramite processi di riconciliazione, audit log o procedure periodiche che ricalcolano e confrontano lo stato distribuito. Tentare di verificare un invariante globale in un singolo punto del codice è inefficace, poiché lo stato globale di un sistema distribuito non esiste come istantanea coerente se non in finestre temporali ristrette e costose da ottenere. Le assert devono quindi essere utilizzate esclusivamente per invarianti locali, mentre gli invarianti globali richiedono meccanismi di controllo distribuiti.


# **Idempotenza, retry, deduplicazione**

Le assert collocate negli handler di richieste idempotenti devono tenere conto del fatto che la stessa richiesta può essere ricevuta più volte a causa di retry, duplicazioni o riordini introdotti dalla rete.

```python
def handler_pagamento(req):
    key = req.idempotency_key
    if già_processata(key):
        return risposta_cached(key)

    assert req.importo > 0
    assert req.utente_id is not None

    risultato = processa(req)
    salva(key, risultato)
    return risultato
```

Un'assert che fallisce durante il secondo tentativo della stessa richiesta indica un errore nella logica di deduplicazione, e tale errore deve essere rilevato immediatamente, poiché rappresenta una violazione della proprietà fondamentale che consente al sistema di tollerare retry e riordini. Le assert in questo contesto non verificano soltanto la correttezza dei dati, ma anche la correttezza del protocollo di idempotenza, poiché un sistema distribuito deve essere in grado di gestire richieste duplicate senza produrre effetti collaterali indesiderati.


### Ordering e consistenza (da finire)

Asserire un ordine causale fra eventi è raro che funzioni se l'ordine viaggia su clock di macchine diverse. La via giusta è asserire proprietà che il sistema preserva per costruzione, versioni, vector clock, lamport timestamp.

```python
def applica_evento(stato, evento):
    assert evento.versione == stato.versione + 1, \
        f"evento fuori sequenza, atteso {stato.versione + 1}, " \
        f"arrivato {evento.versione}"
    stato.versione = evento.versione
    stato.applica(evento.payload)
```


# **Fail‑fast contro graceful degradation**

La distinzione tra una strategia fail‑fast e una strategia di graceful degradation rappresenta una decisione architetturale che determina come un sistema distribuito reagisce a un fallimento rilevato tramite assert, poiché le due strategie ottimizzano proprietà differenti come consistenza interna e disponibilità esterna. La strategia fail‑fast interrompe immediatamente il processo quando un'assert fallisce, delegando all'orchestratore esterno la responsabilità di riavviare il servizio, e garantisce che nessun codice venga eseguito in presenza di uno stato incoerente che potrebbe propagare errori verso altri componenti del sistema. La strategia di graceful degradation cattura l'errore, lo registra in modo strutturato, restituisce un errore al chiamante e continua a servire le altre richieste, preservando la disponibilità del servizio anche in presenza di condizioni anomale che non compromettono la coerenza globale. La strategia fail‑fast è particolarmente utile quando l'assert fallita indica una violazione dell'invariante interno del servizio, poiché tale violazione implica che lo stato locale non è più affidabile e che qualsiasi operazione successiva potrebbe produrre effetti non deterministici o incoerenti. La strategia di graceful degradation è invece appropriata quando l'assert fallita riguarda una singola richiesta e non compromette la correttezza dello stato persistente, poiché il servizio può continuare a operare in modo sicuro per le richieste successive.

Un'implementazione tipica combina entrambe le strategie, distinguendo tra assert che indicano corruzione dello stato interno e assert che riguardano condizioni anomale limitate a una singola richiesta.

```python
def handler(req):
    try:
        return processa(req)
    except AssertionError as ae:
        sentry.capture_exception(ae)
        metriche.incr("assertion_failed")
        if è_assert_di_stato(ae):
            sys.exit(70)            # restart del processo
        return errore_500("internal inconsistency")
```

In un sistema distribuito, questa distinzione è essenziale perché un riavvio non coordinato può influenzare il comportamento di altri servizi, mentre un errore locale gestito correttamente può essere isolato senza compromettere la stabilità complessiva.


# **Replica e quorum**

Nei sistemi basati su quorum, come quelli implementati tramite algoritmi di consenso quali **Raft** o **Paxos**, le assert vengono collocate all'interno della macchina a stati replicata e devono essere valide per ogni replica, poiché un fallimento in una singola replica indica una divergenza nella sequenza di operazioni applicate. La macchina a stati replicata assume che ogni replica applichi le stesse operazioni nello stesso ordine, e un'assert fallita rappresenta un errore critico che richiede un'analisi approfondita del log replicato, dell'ordine delle entry e della semantica delle operazioni applicate.

```rust
fn applica_log(&mut self, entry: LogEntry) {
    debug_assert_eq!(entry.term, self.current_term,
        "log entry term diverso dal current_term");
    debug_assert!(entry.index == self.last_applied + 1,
        "log entry fuori sequenza, attesa {}, ricevuta {}",
        self.last_applied + 1, entry.index);
    self.apply_to_state_machine(&entry);
    self.last_applied = entry.index;
    self.check_rep();
}
```

Un'assert fallita in questo contesto non rappresenta soltanto un errore locale, ma un'indicazione che la replica ha perso la coerenza con il cluster, e tale condizione può derivare da problemi come reorder del log, perdita di messaggi, errori di implementazione nella macchina a stati o violazioni delle garanzie di ordering fornite dal protocollo di consenso. La diagnosi richiede l'analisi del log replicato, dei commit index, dei term e della sequenza delle entry applicate.


# **Tracing distribuito**

Un'assert che fallisce in un servizio downstream assume un valore diagnostico molto maggiore quando include il `trace_id` associato alla richiesta che ha causato il fallimento, poiché tale informazione consente di correlare l'errore con l'intero percorso della richiesta attraverso il sistema distribuito. La propagazione del contesto di tracing richiede l'uso di logging strutturato e protocolli di propagazione del contesto come quelli definiti da **OpenTelemetry**, poiché tali strumenti garantiscono che ogni servizio coinvolto nella richiesta possa allegare informazioni coerenti al trace.

```python
def assert_con_trace(cond, msg, trace_id):
    if not cond:
        log.error("assertion_failed",
                  msg=msg, trace_id=trace_id)
        raise AssertionError(msg)
```

L'integrazione del tracing con le assert consente di identificare rapidamente il punto in cui la richiesta ha incontrato una condizione incoerente, poiché il `trace_id` collega il fallimento a un insieme di eventi distribuiti che possono essere analizzati tramite strumenti di osservabilità. Questo approccio riduce il tempo necessario per individuare la causa del fallimento e consente di correlare errori locali con condizioni globali come ritardi di rete, retry, riordini o partizioni temporanee.

# **Modelli di consistenza e cosa si può asserire**

Il modello di consistenza scelto per un sistema distribuito è la bussola che indica dove ha senso piazzare un'assert e dove invece bisogna affidarsi a reconciliation e audit periodici. Ogni modello consegna promesse diverse sulla visibilità e sull'ordine delle operazioni, e queste promesse definiscono il perimetro entro cui una verifica locale ha valore semantico. Conoscere il modello significa sapere se l'asserzione che stai scrivendo cattura una violazione reale o se sta semplicemente suonando un campanello in un universo osservabile solo a pezzi.

## **Linearizable**

Nel modello linearizable ogni operazione appare come se fosse eseguita in un punto preciso della linea temporale reale e ogni lettura che segue una scrittura completata vede quel valore o uno più recente. In questo contesto le assert che verificano la monotonicità delle scritture o la visibilità immediata degli aggiornamenti diventano verifiche robuste e significative. Ottieni la comodità di poter trasferire invarianti locali in controlli distribuiti senza sorprese, ma paghi il conto operativo con protocolli di consenso e sincronizzazione che aumentano la complessità dell'esercizio quotidiano. In pratica, se il tuo sistema è linearizable puoi trattare molte asserzioni come verità operative e non come mere ipotesi.

## **Serializable**

Nel modello serializable le transazioni si comportano come se fossero eseguite in qualche ordine seriale, senza che quell'ordine debba rispettare il tempo reale. Dentro una transazione le assert possono essere ambiziose perché la transazione osserva uno stato coerente e il commit riflette un ordine seriale valido. Fuori dalla transazione la vista del mondo può invece apparire frammentata e ingannevole, perciò una assert posta al di fuori del contesto transazionale perde la stessa solidità. In altre parole, le verifiche dentro la transazione sono affidabili, le verifiche esterne sono sospette.

## **Strict Serializable**

Quando combini serializability e linearizability ottieni strict serializable, un modello che garantisce sia un ordine seriale astratto sia la coerenza con il tempo reale. Qui le assert più forti tornano ad avere senso anche in presenza di transazioni, perché ogni operazione rispetta sia l'isolamento che la relazione temporale. Il prezzo da pagare è ancora più alto rispetto ai modelli precedenti, ma il vantaggio è che invarianti che altrove richiederebbero reconciliation o controlli esterni possono essere verificati direttamente e con fiducia.

## **Snapshot Isolation**

Snapshot isolation consegna a ogni transazione uno snapshot coerente dello stato al momento dell'inizio e rileva i conflitti di scrittura al commit. All'interno della transazione le assert che verificano relazioni tra oggetti sono affidabili grazie allo snapshot consistente. Il modello però permette il fenomeno del write skew in cui due transazioni, pur osservando snapshot coerenti, producono insieme uno stato finale incoerente. Perciò le assert devono limitarsi a proprietà locali allo snapshot e non pretendere di imporre invarianti globali senza meccanismi aggiuntivi.

## **Causal consistency**

La Causal consistency impone un ordine solo tra operazioni causalmente correlate mentre lascia le operazioni indipendenti libere di essere osservate in ordini diversi. Le assert che verificano proprietà legate a relazioni causali funzionano bene perché il modello garantisce la visibilità degli effetti dipendenti. Tentare di imporre un ordine totale con assert in un sistema causalmente consistente porta a fallimenti intermittenti e a confusione, perché il modello non promette un ordine globale e le verifiche che lo pretendono inseguono un'illusione. Quindi prima di piazzare una assert in un sistema distribuito valuta la promessa che il modello mantiene davvero. Se il modello garantisce visibilità e ordine sufficienti, l'assert diventa uno strumento potente per catturare violazioni di invarianti. Se il modello non lo fa, l'assert rischia di trasformarsi in un campanello che suona a vuoto, segnalando sintomi senza risolvere la causa. Conoscere il modello di consistenza significa sapere dove ha senso verificare subito e dove invece è necessario progettare meccanismi di riconciliazione, audit o consenso per far valere gli invarianti che contano davvero.

## **Eventual consistency**

Nel modello **eventual consistency**, le repliche convergono a uno stato comune dopo un intervallo di tempo non deterministico, e non esiste alcuna garanzia sulla coerenza istantanea tra repliche. Le assert che verificano la coerenza tra repliche in un istante specifico sono destinate a fallire, poiché il modello non garantisce alcuna coerenza temporale. Le assert devono invece verificare proprietà di convergenza asintotica, come la distanza tra snapshot coerenti letti da repliche diverse, e tali proprietà devono essere controllate tramite processi periodici di reconciliation, non tramite assert inline.

```python
# antipattern in sistema eventually consistent
def handler():
    replica_a = leggi_da_A()
    replica_b = leggi_da_B()
    assert replica_a == replica_b   # salterà appena la rete sospira

# pattern corretto, asserisce convergenza differita
def audit_periodico():
    snapshot_a = leggi_consistente_da_A()
    snapshot_b = leggi_consistente_da_B()
    metriche.record("divergenza",
                    distanza(snapshot_a, snapshot_b))
    assert distanza(snapshot_a, snapshot_b) < soglia_tollerata
```

Questo pattern consente di verificare proprietà compatibili con il modello di consistenza, evitando assert che richiedono garanzie non fornite dal sistema.


# **Jepsen e l'arte di rompere i sistemi distribuiti**

Jepsen, sviluppato da Kyle Kingsbury, rappresenta uno strumento progettato per verificare in modo sistematico la robustezza dei sistemi distribuiti tramite l'iniezione controllata di condizioni avverse come partizioni di rete, latenze elevate, clock skew e crash di processi, e la successiva analisi delle proprietà che il sistema continua a rispettare. La libreria sottostante, chiamata **Knossos**, esegue un controllo di linearizability a posteriori ricostruendo un ordine totale compatibile con la storia osservata, e determina se esiste una sequenza di operazioni che rispetta le garanzie dichiarate dal sistema. L'idea è che le assert sulle proprietà globali di un sistema distribuito non debbano essere collocate nel codice di produzione, poiché il codice di produzione non possiede una visione globale dello stato distribuito, ma debbano essere collocate in un harness di test che orchestra fault injection, raccoglie le storie di esecuzione e verifica le proprietà tramite un oracle esterno. Questo approccio consente di verificare proprietà come linearizability, serializability o causal consistency senza introdurre overhead nel percorso critico del sistema.

```clojure
;; pseudocode in stile Jepsen
(defn check-bank-invariant [history]
  (let [final-state (replay history)]
    (assert (= (total-balance final-state) initial-total)
            "denaro scomparso durante il test")))
```

In produzione, le assert devono essere limitate agli invarianti locali del nodo, poiché il nodo possiede una visione coerente del proprio stato interno. Nei test in stile Jepsen, le assert devono essere collocate sull'oracle globale, poiché solo l'oracle possiede una visione completa della storia distribuita. Questa separazione consente di verificare proprietà globali senza compromettere le prestazioni del sistema in produzione. L'approccio Jepsen evidenzia inoltre che molte violazioni di consistenza non emergono durante test funzionali tradizionali, poiché tali test non introducono condizioni avverse come partizioni di rete o riordini di messaggi. Le assert globali devono quindi essere verificate tramite strumenti che simulano condizioni realistiche di fallimento, poiché tali condizioni rappresentano scenari operativi comuni nei sistemi distribuiti.

# **CAP, PACELC e assert**

I modelli teorici **CAP** e **PACELC** definiscono i limiti strutturali dei sistemi distribuiti e determinano quali assert possono essere considerate valide e quali assert sono destinate a fallire. Il teorema CAP afferma che, in presenza di una partizione di rete, un sistema deve scegliere tra consistenza e disponibilità, e questa scelta determina quali proprietà possono essere verificate tramite assert. In un sistema AP, le assert che richiedono consistenza globale durante una partizione falliscono inevitabilmente, poiché il sistema privilegia la disponibilità. In un sistema CP, il sistema diventa indisponibile durante la partizione, e le assert che richiedono consistenza globale hanno meno opportunità di essere eseguite.

Il modello PACELC estende CAP affermando che, anche in assenza di partizioni, esiste un trade‑off tra latenza e consistenza. Un sistema EC ottimizza per consistenza e accetta una latenza maggiore, mentre un sistema EL ottimizza per latenza e accetta stati incoerenti per brevi intervalli. Le assert che richiedono consistenza forte in un sistema EL rappresentano assunzioni non supportate dal modello, poiché il sistema può restituire valori incoerenti per brevi periodi anche in condizioni normali. Conoscere la classificazione del sistema consente di determinare quali assert sono semanticamente valide e quali assert rappresentano aspettative irrealistiche. Ad esempio:

- DynamoDB è classificato come AP‑EL  
- Cassandra è AP‑EL con consistenza tunable  
- MongoDB (default) è AP‑EL  
- Spanner è CP‑EC  
- CockroachDB è CP‑EC  

Questa classificazione consente di prevedere quali assert possono essere verificate in modo affidabile e quali assert falliranno in modo intermittente, evitando di interpretare come bug condizioni che rappresentano semplicemente conseguenze del modello di consistenza adottato.

## Ottimizzazioni e costi nei contesti veri

Le assert hanno un costo, e nei contesti asincroni e distribuiti quel costo si amplifica, perché viene moltiplicato per i task in volo, per le richieste al secondo, per le repliche, e per i nodi che lo subiscono ecc. Sarebbe buona pratica avere tre livelli di assert, attivati da flag separati.

Livello 1) **assert sempre attive**: Verifiche O(1), basso costo, che colgono al volo violazioni gravi. In Rust `assert!`, in altri linguaggi un `if` che lancia eccezione.

Livello 2) **assert di debug**: Verifiche O(1) o O(log n) che girano in dev e staging, spente in produzione. `debug_assert!` di Rust, `#ifdef DEBUG` in C, `if __debug__:` in Python.

Livello 3) **assert pesanti**: Verifiche O(n) o peggio che girano nei test e durante audit periodici, spente sia in dev sia in produzione. Macro custom tipo `HEAVY_CHECK(...)`, o moduli dedicati al property-based testing.

```rust
macro_rules! heavy_assert {
    ($cond:expr) => {
        #[cfg(feature = "heavy_checks")]
        { assert!($cond); }
    };
}
```

### Sampling delle assert pesanti

In sistemi ad alto throughput, asserire un invariante O(n) a ogni richiesta è insostenibile. La soluzione è eseguirlo su una frazione delle chiamate, diciamo 1 su 1000, scelte a caso.

```python
import random

def handler(req):
    risultato = processa(req)
    if random.random() < 0.001:
        check_rep_costoso()   # campione statistico
    return risultato
```

Il throughput resta alto, e una corruzione persistente verrà colta entro poche migliaia di richieste.


# **Assert in hot path**

In percorsi di esecuzione ad alta frequenza, dove una funzione viene invocata milioni di volte al secondo, anche un'assert apparentemente leggera può introdurre un overhead sufficiente a compromettere obiettivi di latenza come p99 o p999, poiché ogni istruzione aggiuntiva aumenta la pressione sulla pipeline e riduce la capacità del compilatore di applicare ottimizzazioni come la vettorizzazione o l'unrolling del loop. La valutazione del costo reale deve essere effettuata tramite strumenti di profilazione come **`perf`**, **`pprof`** o **`tracy`**, poiché tali strumenti forniscono misure precise dell'impatto dell'assert sul percorso critico.

Una strategia comune consiste nello spostare l'assert fuori dal loop interno, mantenendo la verifica logica ma riducendo drasticamente il costo per iterazione, poiché il compilatore può ottimizzare il loop di lavoro in modo più aggressivo quando non contiene istruzioni di controllo aggiuntive.

```c
// invece di asserire dentro il for stretto
for (size_t i = 0; i < n; i++) {
    assert(arr[i] != NULL);   // costoso a ogni iterazione
    fai_qualcosa(arr[i]);
}

// estrai la verifica prima
for (size_t i = 0; i < n; i++) {
    assert(arr[i] != NULL);
}
for (size_t i = 0; i < n; i++) {
    fai_qualcosa(arr[i]);
}
```

Questo schema consente al compilatore di vettorizzare il loop principale, poiché la presenza dell'assert nel loop interno impedisce spesso l'autovectorization, l'unrolling e la fusione delle micro‑operazioni.

# **Argomenti orfani**

Alcuni temi non rientrano nelle categorie precedenti ma possiedono comunque rilevanza pratica significativa, poiché influenzano la qualità diagnostica delle assert, la loro integrazione con strumenti di test e la loro interazione con modelli di concorrenza e strumenti di telemetria.

# **Assert e logging strutturato**

Un'assert che fallisce deve produrre informazioni sufficienti per consentire un'analisi accurata del contesto in cui è avvenuto il fallimento, e il messaggio associato deve essere trattato come un log strutturato che include variabili rilevanti, identificativi della richiesta e metadati utili alla diagnosi. L'inclusione di campi come `ordine.id`, `ordine.versione` e `trace_id` consente di correlare il fallimento con eventi precedenti e successivi, facilitando l'analisi retrospettiva tramite strumenti di osservabilità.

```python
assert ordine.stato == "creato", \
    f"stato inatteso ordine_id={ordine.id} stato={ordine.stato} " \
    f"versione={ordine.versione} trace_id={ctx.trace_id}"
```

Questo approccio riduce il tempo necessario per individuare la causa del fallimento, poiché il messaggio dell'assert contiene già le informazioni essenziali per ricostruire il contesto operativo.


# **Assert e fuzzing, property‑based testing**

Le assert rappresentano un complemento naturale per tecniche come il fuzzing e il property‑based testing, poiché tali tecniche generano input non convenzionali che esercitano percorsi di esecuzione rari e verificano automaticamente la robustezza degli invarianti. Strumenti come **Hypothesis**, **QuickCheck** o **proptest** generano input che esplorano lo spazio dei casi limite, e ogni assert fallita diventa un controesempio concreto che documenta una violazione dell'invariante.

```python
from hypothesis import given, strategies as st

@given(st.lists(st.integers(), min_size=1))
def test_media_proprieta(lst):
    m = media(lst)
    assert min(lst) <= m <= max(lst)
```

Le assert interne alla funzione `media` collaborano con il fuzzer, poiché ogni violazione viene catturata e minimizzata in un caso riproducibile, migliorando la qualità del test e riducendo il tempo necessario per individuare errori strutturali.


# **Assert, race condition, lock e memoria condivisa**

In codice multi‑thread, un'assert che legge una variabile condivisa senza sincronizzazione osserva un valore potenzialmente obsoleto, poiché il modello di memoria consente riordini e visibilità parziale degli aggiornamenti. Le assert devono quindi essere collocate all'interno di sezioni critiche protette da lock, operazioni atomiche o barriere di memoria, poiché solo tali meccanismi garantiscono visibilità coerente degli aggiornamenti.

```rust
let guard = mutex.lock().unwrap();
debug_assert!(guard.invariante_ok());
// modifica protetta
guard.aggiorna();
debug_assert!(guard.invariante_ok());
drop(guard);
```

Asserire al di fuori della sezione critica equivale a verificare uno stato non sincronizzato, e tale verifica non possiede significato operativo in presenza di concorrenza reale. Le assert devono quindi essere progettate per rispettare il modello di memoria del linguaggio e del runtime.


# **Assert e refactoring**

Un'assert che fallisce dopo un refactoring non funzionale indica che l'assert era legata all'implementazione piuttosto che al comportamento osservabile, e tale legame riduce la robustezza del test. Le assert devono verificare proprietà semantiche del risultato, non dettagli dell'implementazione, poiché tali dettagli possono cambiare senza alterare la correttezza dell'algoritmo. La capacità di riscrivere un algoritmo senza modificare le assert rappresenta un indicatore affidabile della qualità delle assert stesse.

# **Assert, telemetria, sentry e metriche**

Un'assert che fallisce in produzione deve essere registrata tramite strumenti di telemetria come Sentry, Datadog o Rollbar, poiché tali strumenti aggregano le eccezioni per signature e consentono di identificare pattern ricorrenti. Una metrica come `assertion_failed_total{nome=...}` consente di costruire alert basati sulla frequenza dei fallimenti, e il pattern "cattura e rilancia" consente di preservare il comportamento fail‑fast arricchendo al contempo la telemetria.

```python
try:
    operazione()
except AssertionError as ae:
    sentry_sdk.capture_exception(ae)
    statsd.incr("assertion_failed", tags=["op:operazione"])
    raise
```

Questo approccio consente di monitorare la stabilità del sistema senza compromettere la semantica delle assert.


# **Assert, codice generato, serializzazione e round‑trip**

Nel codice che genera codice, come parser, code generator o trasformazioni IR, e nel codice che serializza e deserializza strutture dati, le assert di round‑trip rappresentano uno strumento essenziale per verificare la correttezza della trasformazione. La proprietà `deserializza(serializza(x)) == x` rappresenta una specifica eseguibile che garantisce che la trasformazione sia invertibile e che nessuna informazione venga persa.

```python
def test_round_trip(oggetto):
    blob = serializza(oggetto)
    ricostruito = deserializza(blob)
    assert oggetto == ricostruito, \
        f"round-trip rotto, orig={oggetto}, rebuilt={ricostruito}"
```

Una rete di assert di round‑trip fornisce una garanzia robusta sulla correttezza del codice generato, poiché ogni violazione rappresenta un caso concreto che documenta una perdita di informazione o una trasformazione non invertibile.

### Assert e signal, segfault, panic, recovery

Quando un'assert fallisce in C su un thread separato, il `SIGABRT` ammazza l'intero processo, quando fallisce in Rust dentro `tokio::spawn`, il panic si limita al task, salvo configurazioni diverse. Quando fallisce in Python dentro un thread, l'eccezione resta nel thread e manca di risalire al main, finché qualcuno gestisce la cosa con un hook. Conoscere il comportamento del runtime sotto stress fa la differenza fra un servizio che cade in modo prevedibile e uno che cade in modo creativo.

```python
import threading
import sys

def excepthook(args):
    print(f"thread {args.thread.name} è caduto", file=sys.stderr)
    sys.exit(1)

threading.excepthook = excepthook
```

# **Assert come specifica leggibile**

Le assert rappresentano anche una forma di documentazione eseguibile che esplicita in modo preciso le assunzioni operative del codice. Un nuovo sviluppatore che analizza una funzione dotata di assert collocate nei punti critici ottiene una descrizione immediata delle precondizioni, delle postcondizioni e degli invarianti intermedi, riducendo il tempo necessario per comprendere la struttura logica dell'algoritmo. Le assert fungono quindi da specifica locale che descrive ciò che il codice richiede e ciò che il codice garantisce, senza richiedere la consultazione di documentazione esterna.


```cpp
void push(int x) {
    assert(size_ < capacity_);
    buffer_[size_] = x;
    size_++;
    assert(size_ <= capacity_);
}
```

Esempio in Rust:

```rust
fn insert(&mut self, idx: usize, value: T) {
    debug_assert!(idx <= self.len);
    self.shift_right(idx);
    self.data[idx] = value;
    self.len += 1;
    debug_assert!(self.rep_ok());
}
```

Esempio in Python:

```python
def enqueue(q, item):
    assert q.tail < len(q.buffer)
    q.buffer[q.tail] = item
    q.tail += 1
    assert q.tail <= len(q.buffer)
```

In tutti questi casi, le assert esplicitano proprietà che il lettore avrebbe comunque dovuto inferire, ma che ora sono dichiarate in modo chiaro e verificabile. Questo rende il codice più facile da mantenere, più semplice da analizzare e più robusto rispetto a modifiche future.


# **Assert e type system**

Il rapporto tra type system e assert può essere descritto come una continuità lungo la quale i tipi rappresentano verifiche statiche effettuate dal compilatore, mentre le assert rappresentano verifiche dinamiche che il type system non è in grado di esprimere. In linguaggi con type system forti e ricchi, come Rust, Haskell o OCaml, molte proprietà possono essere espresse direttamente nei tipi, eliminando la necessità di assert che verifichino condizioni già garantite staticamente.

Esempio in Rust:

```rust
fn somma(a: u32, b: u32) -> u32 {
    // inutile: u32 è sempre non negativo
    debug_assert!(a >= 0);
    a + b
}
```

In questo caso, l'assert è ridondante perché il type system garantisce che `a` sia sempre non negativo. La regola generale è che, quando il type system fornisce una garanzia, l'assert deve essere evitata, poiché rappresenta una duplicazione inutile della logica. Ma esistono proprietà che il type system tradizionale non può esprimere, come "lista non vuota", "intero positivo", "vettore di lunghezza n", "indice valido per questo array", "stringa JSON valida", "timestamp monotonicamente crescente". In tali casi, le assert rappresentano un complemento naturale del type system.

I **refinement types** e i **dependent types**, come quelli offerti da **Liquid Haskell**, **F\*** o **Idris**, estendono la capacità del type system di esprimere proprietà logiche complesse, riducendo ulteriormente la necessità di assert dinamiche. Dove tali sistemi sono disponibili, molte assert diventano superflue, poiché la proprietà viene verificata staticamente.

Esempio in Liquid Haskell:

```haskell
{-@ type Pos = {v:Int | v > 0} @-}

{-@ increment :: Pos -> Pos @-}
increment x = x + 1
```

In questo caso, l'assert "x > 0" è incorporata nel tipo stesso.

In TypeScript, le **assertion functions** rappresentano un punto di contatto interessante tra verifica statica e dinamica, poiché un'assert dinamica può raffinare il tipo statico a valle, consentendo al type checker di utilizzare informazioni ottenute a runtime.

```typescript
function assertString(x: unknown): asserts x is string {
    if (typeof x !== "string") throw new Error("non è una stringa");
}

function uso(input: unknown) {
    assertString(input);
    // qui input ha tipo string
    return input.toUpperCase();
}
```

Esempio aggiuntivo in TypeScript con un tipo più complesso:

```typescript
function assertNonEmpty<T>(xs: T[]): asserts xs is [T, ...T[]] {
    if (xs.length === 0) throw new Error("lista vuota");
}

function head<T>(xs: T[]) {
    assertNonEmpty(xs);
    return xs[0]; // xs è ora un tuple type non vuoto
}
```

Esempio in Python con type hints e assert come raffinamento dinamico:

```python
from typing import List, NoReturn

def assert_non_empty(xs: List[int]) -> None:
    assert len(xs) > 0, "lista vuota"

def head(xs: List[int]) -> int:
    assert_non_empty(xs)
    return xs[0]
```

In questo caso, il type checker non può dedurre che `xs` sia non vuota, ma l'assert dinamica fornisce una garanzia operativa che il programmatore può sfruttare.

Esempio in Rust con `Option<T>`:

```rust
fn usa(x: Option<i32>) -> i32 {
    debug_assert!(x.is_some());
    x.unwrap()
}
```

Qui l'assert documenta un'invariante che il type system non può garantire da solo, poiché `Option<T>` rappresenta un dominio più ampio di quello richiesto dalla funzione.

# **Assert in linguaggi che mancano del costrutto**

Alcuni linguaggi non forniscono un costrutto `assert` standard oppure lo forniscono in forma limitata, e in tali contesti il programmatore deve ricorrere a meccanismi equivalenti che svolgono la stessa funzione semantica, ovvero verificare invarianti locali e interrompere l'esecuzione quando tali invarianti vengono violati. Ogni ecosistema ha sviluppato convenzioni specifiche che riflettono il modello di errore del linguaggio, il suo runtime e la sua filosofia di progettazione.


## **NO PANIC**

La filosofia di Go, che privilegia errori espliciti e percorsi di controllo chiari quindi scoraggia l'uso di assert e incoraggia ula gestione esplicita degli errori, ma la combinazione di un controllo esplicito e di un `panic` rappresenta l'equivalente funzionale di un'assert, poiché interrompe l'esecuzione quando un contratto interno viene violato.

```go
func divide(a, b int) int {
    if b == 0 {
        panic("divisione per zero, contratto rotto")
    }
    return a / b
}
```

In codice di libreria, il pattern viene spesso incapsulato in funzioni di validazione:

```go
func assertNonEmpty(xs []int) {
    if len(xs) == 0 {
        panic("slice vuota, precondizione violata")
    }
}
```


## **Shell scripting: `set -euo pipefail` come assert implicite**

Nel mondo POSIX, la mancanza di un costrutto `assert` viene compensata da opzioni della shell che trasformano errori silenziosi in fallimenti immediati. Le opzioni `set -e`, `set -u` e `set -o pipefail` rappresentano una forma rudimentale ma efficace di assert globale, poiché interrompono l'esecuzione quando un comando fallisce, quando una variabile non definita viene utilizzata o quando una pipeline fallisce in un punto non terminale.

```bash
set -euo pipefail
[[ -d "$config_dir" ]] || { echo "config_dir mancante" >&2; exit 1; }
```

In script complessi, si usano funzioni dedicate:

```bash
assert_file() {
    [[ -f "$1" ]] || { echo "file mancante: $1" >&2; exit 1; }
}
```


## **SQL: CHECK constraints e RAISE come assert del database**

Nel mondo SQL, gli invarianti vengono espressi tramite **CHECK constraints** e tramite istruzioni `RAISE` nelle stored procedure. Questi meccanismi rappresentano assert statiche e dinamiche che garantiscono la coerenza dei dati a livello di tabella e di transazione.

```sql
CREATE TABLE conto (
    id     SERIAL PRIMARY KEY,
    saldo  NUMERIC NOT NULL CHECK (saldo >= 0)
);
```

Esempio con `RAISE` in PL/pgSQL:

```sql
IF NEW.saldo < 0 THEN
    RAISE EXCEPTION 'saldo negativo %, violazione invariante', NEW.saldo;
END IF;
```

# **Quando NaN e Inf travolgono le assert**

Nel modello di aritmetica floating‑point definito dallo standard **IEEE‑754**, i valori speciali `NaN` e `Inf` introducono comportamenti che rendono alcune assert apparentemente ovvie completamente inaffidabili, poiché lo standard definisce regole di confronto non intuitive che devono essere comprese prima di scrivere assert numeriche corrette. In particolare, `NaN != NaN` per definizione, e qualsiasi confronto che coinvolge un `NaN` restituisce `false`, rendendo inutilizzabile la forma ingenua `assert(x == x)` come verifica di identità numerica, ma rendendola invece un test efficace per rilevare la presenza di `NaN`.

```python
import math

x = float('nan')
assert x == x                  # salta, NaN != NaN
assert not math.isnan(x)       # forma idiomatica
assert math.isfinite(x)        # copre NaN e ±Inf
```

La presenza di `Inf` introduce ulteriori problemi, poiché operazioni come divisioni per zero, overflow numerici o somme di valori molto grandi possono produrre `Inf` senza generare eccezioni, e tali valori possono propagarsi attraverso la pipeline numerica fino a invalidare completamente il risultato finale. Le assert devono quindi verificare esplicitamente la finitezza dei valori in punti critici della pipeline, poiché la propagazione di `NaN` o `Inf` rappresenta una delle principali cause di instabilità numerica.


## **Confronti floating‑point**

L'assert `assert(0.1 + 0.2 == 0.3)` fallisce in tutti i linguaggi conformi a IEEE‑754, poiché la rappresentazione binaria dei numeri decimali non è esatta e la somma produce un valore leggermente diverso da `0.3`. La forma corretta utilizza una tolleranza assoluta o relativa, a seconda della scala dei valori.


# **Assert e LLM, agent AI, pipeline di linguaggio**

Nel contesto delle pipeline che integrano modelli linguistici di grandi dimensioni, le assert assumono un ruolo radicalmente diverso rispetto al codice deterministico tradizionale, poiché l'output di un LLM non possiede alcuna garanzia formale di tipo, struttura o coerenza semantica. Le proprietà che in un programma convenzionale sono garantite dal type system, dal compilatore o dal contratto della funzione diventano incerte, e l'unico modo per evitare che un output malformato propaghi errori nella pipeline consiste nell'introdurre assert che verificano forma, dominio e coerenza. Una funzione tradizionale f : X → Y garantisce che, per ogni input x ∈ X, il valore restituito appartenga a Y, e che eventuali violazioni siano rilevate dal compilatore o dal runtime tramite eccezioni. Una chiamata a un LLM, invece, implementa una mappatura stocastica f̂(x) ∼ p(y ∣ x), dove y non è garantito appartenere a nessun insieme Y definito staticamente, e dove la distribuzione p può produrre valori sintatticamente corretti ma semanticamente invalidi. In questo scenario, le assert diventano l'unico meccanismo che consente di verificare che l'output soddisfi vincoli strutturali e semantici. Le violazioni tipiche sono tantissime, JSON non valido, campi mancanti rispetto a uno schema, valori con tipo errato, valori fuori dominio, incoerenze logiche tra chiamate successive, contraddizioni rispetto a fatti precedenti,........ Poiché la chiamata HTTP è formalmente riuscita, nessuna eccezione viene sollevata automaticamente, e l'errore semantico deve essere rilevato manualmente. Quindi possiamo vedere i vari ruoli che le assert prendono.


## **1. Validatori di forma**

I validatori di forma assicurano che l'output rispetti uno schema sintattico e strutturale prima che venga consumato dalle fasi successive della pipeline. Se lo schema atteso è **S** e l'output è **y**, il controllo è `assert(y ∈ S)`, dove **S** può essere definito come un insieme di vincoli strutturali del tipo `S = { y ∣ ∀ k ∈ K, k ∈ keys(y) ∧ type(yₖ) = Tₖ }`. In pratica questo significa verificare presenza di chiavi, tipi dei campi e forme aggregate: ad esempio che il campo `"name"` sia una stringa, che `"age"` sia un intero e che `"scores"` sia una lista di float. Ogni violazione deve essere intercettata prima che l'oggetto venga passato oltre. Un buon validatore non si limita a un singolo controllo monolitico ma scompone lo schema in assert elementari e interpretabili: `assert("name" ∈ keys(y))`, `assert(type(y["age"]) = int)`, `assert(∀ s ∈ y["scores"], type(s) = float)`. Questa granularità rende immediata la diagnosi, permette azioni differenziate al fallimento (retry con prompt corretivo, normalizzazione automatica, escalation umana) e facilita la raccolta di telemetria utile per migliorare prompt e schema. Quando possibile, i validatori dovrebbero restituire un payload diagnostico strutturato che includa il campo fallito, il tipo atteso, il valore ricevuto e un codice di errore standardizzato.

Inoltre i validatori devono essere resilienti all'evoluzione degli schemi e versionare lo schema, includendo un campo di metadati che dichiari la versione attesa e prevedere meccanismi di migrazione o fallback per campi opzionali. In ambienti dove lo schema cambia frequentemente invece è preferibile adottare una strategia di compatibilità progressiva che accetti campi aggiuntivi ma segnali quelli mancanti o con tipo errato come warning o error a seconda della criticità. Questo dovrebbe ridurre i falsi positivi e mantenere la pipeline operativa mentre si raccolgono dati per aggiornare i controlli ma non è garantito. Inoltre ogni `assert(y ∈ S)` fallita deve generare log strutturati. Questi artefatti permettono di distinguere tra gli errori dovuti a prompt malformati, limiti del modelo o regressioni introdotte da cambi di versione. Progettare i validatori come componenti testabili e riutilizzabili consente inoltre di eseguire test automatici sia in build di debug sia in build di release.

## **2. Validatori di dominio**

Verificano che i valori appartengano a un dominio semantico coerente con l'applicazione. Se un campo rappresenta una probabilità, la condizione è assert(0 ≤ p ≤ 1). Se un campo rappresenta una data storica: assert(t < t_oggi). E se un campo rappresenta un importo monetario assert(v ≥ 0). Questi vincoli non sono deducibili dalla forma del JSON, ma rappresentano proprietà del dominio applicativo.

## **3. Validatori di consistenza inter‑chiamata**

Verificano che chiamate successive non producano risposte logicamente incompatibili. Se due risposte y₁ e y₂ devono essere coerenti rispetto a una proprietà P, la condizione è assert(P(y₁) = P(y₂)).

Per esempio:

- prima chiamata: "Roma è in Italia"  
- seconda chiamata: "Roma è in Francia"  

La proprietà geografica è violata assert(country(Roma) = Italia), questo tipo di assert è essenziale nelle pipeline multi‑step, negli agenti che mantengono uno stato interno e nei sistemi che richiedono coerenza narrativa o fattuale.

## **Esempi di incoerenze tipiche rilevabili solo tramite assert**

Gli assert intercettano errori che la sola validazione sintattica non può scoprire, valori semanticamente inappropriati e fuori dominio. Un caso tipico lo abbiamo quando un campo numerico viene restituito come stringa leggibile dall'uomo, ad esempio ` "age": "ventidue" ` invece dell'intero `22`. Allo stesso modo un importo monetario negativo come ` "price": -5.0 ` è formalmente un numero ma viola la regola applicativa `assert(v ≥ 0)` e deve essere bloccato o normalizzato prima dell'uso. Un altro esempio è questo, una probabilità ` "probability": 1.7 ` supera il range consentito e richiede `assert(0 ≤ p ≤ 1)`, mentre una data futura o non storica deve essere fermata da `assert(t < t_oggi)`. Questi controlli non si possono dedurre dallo schema JSON e l'ideale sarebbe avere una semantica formale del risultato voluto.

Notiamo che le incoerenze tra chiamate successive sono un'altra classe critica di problemi che vanno gestiti, se la prima risposta afferma che `country(Roma) = Italia` e una chiamata successiva restituisce `country(Roma) = Francia`, la contraddizione è rilevabile solo confrontando gli output con assert del tipo `assert(P(y₁) = P(y₂))`. In pipeline multi‑step o in agenti con stato interno, tali assert prevengono la propagazione di narrazioni incoerenti o fatti contraddittori. Infine, esistono casi ibridi dove la forma è corretta ma il valore è fuori contesto e questi sono subdoli, per esempio, immagioniamo un campo ` "status" ` che può contenere un valore non previsto dallo schema (ad esempio ` "archived_later"` quando lo schema accetta solo `["open","closed","pending"]`), oppure un elenco di punteggi può includere elementi non numerici o fuori range. Senza assert che codifichino le regole semantiche e le soglie applicative, questi errori rimangono nascosti e possono causare malfunzionamenti a valle mentre con assert sensate si otterrebbe un punto di controllo esplicito.


# **Assert sullo schema dell'output**

La pratica più immediata che si può pensare nelle pipeline LLM è richiedere al modello un output strutturato e nel verificare al rientro che tale output rispetti uno schema dichiarato. Questo approccio separa in modo la validazione sintattica dalla validazione semantica. In termini formali, se S è lo schema atteso e y è l'output del modello, la validazione sintattica verifica: assert(y ∈ S), dove S è un insieme definito da vincoli strutturali S = { y ∣ ∀ k ∈ K, k ∈ keys(y) ∧ type(yₖ) = Tₖ }. Una volta verificata la forma, le assert di dominio verificano proprietà aggiuntive che non possono essere espresse nello schema, come vincoli di range, coerenza tra campi e plausibilità dei valori.

Esempio in Python con Pydantic:

```python
from pydantic import BaseModel, Field, ValidationError
from typing import Literal

class RispostaAnalisi(BaseModel):
    sentiment: Literal["positivo", "negativo", "neutro"]
    confidenza: float = Field(ge=0.0, le=1.0)
    motivi: list[str] = Field(min_length=1, max_length=5)

def analizza_testo(testo: str) -> RispostaAnalisi:
    raw = chiama_llm(prompt(testo), formato="json")
    try:
        risultato = RispostaAnalisi.model_validate_json(raw)
    except ValidationError as e:
        log.error("output LLM malformato", raw=raw, errore=str(e))
        raise

    # assert di dominio oltre lo schema
    assert risultato.confidenza > 0.0, \
        f"confidenza zero, modello incerto, raw={raw}"
    if risultato.sentiment == "neutro":
        assert risultato.confidenza < 0.9, \
            "sentiment neutro con confidenza altissima, sospetto"
    return risultato
```

La separazione tra enforcement dello schema e assert di dominio è essenziale, poiché lo schema garantisce type(yₖ) = Tₖ mentre le assert garantiscono assert(P(yₖ)) dove P è una proprietà del dominio applicativo, non esprimibile tramite semplice tipizzazione.

# **Constrained generation e quando le assert restano necessarie**

Tecniche moderne come **constrained decoding**, **structured output**, **JSON schema enforcement** e strumenti come **outlines** per modelli open‑weight consentono di forzare il modello a produrre output che rispetta uno schema *per costruzione*. Questo approccio riduce drasticamente la probabilità di errori sintattici, ma non elimina la possibilità di errori semantici, poiché il modello continua a scegliere valori all'interno dello spazio consentito senza alcuna garanzia di correttezza.

In termini formali, il constrained decoding garantisce y ∈ S ma non garantisce P(y) = true con P che rappresenta una proprietà semantica, come "la data è nel passato", "la temperatura è fisicamente plausibile", "la categoria è coerente con il contesto".

Esempio:

```python
risposta = client.chat.completions.create(
    model="gpt-4o",
    response_format={"type": "json_schema", "json_schema": SCHEMA},
    messages=[...]
)
dati = json.loads(risposta.choices[0].message.content)

# lo schema è garantito, il senso no
assert dati["data_evento"] <= oggi_iso, \
    f"evento storico nel futuro? data={dati['data_evento']}"
assert dati["temperatura_celsius"] > -273.15, \
    "temperatura sotto lo zero assoluto, modello in delirio"
```

Il modello può produrre un JSON perfettamente valido ma semanticamente assurdo, e l'unico modo per intercettare tali errori è tramite assert di dominio.

Esempi di vincoli che il constrained decoding **non** può garantire:

### Espressioni in simboli unicode

- coerenza temporale:`t_inizio ≤ t_fine`

- plausibilità fisica: `T > −273.15`

- coerenza geografica: `country(Roma) = Italia`

- normalizzazione di probabilità: `Σ_i p_i = 1 ± ε`
  
Questi vincoli richiedono assert esplicite.


# **Assert sul grafo di tool call di un agent**

Un agent è un sistema in cui un LLM pianifica e invoca tool in sequenza per raggiungere un obiettivo, generando un grafo di esecuzione che deve rispettare vincoli strutturali e di policy. In questo contesto, le assert non verificano solo la forma dell'output, ma anche la coerenza del comportamento dell'agente, la validità delle transizioni e l'assenza di loop patologici.

Formalmente, se il grafo di esecuzione è G = (V, E) dove V sono gli step e E le transizioni tra tool, le assert verificano proprietà come:

### 1. Consistenza interna

assert(|storia| = i), qui i è il numero di iterazioni eseguite.

### 2. Assenza di loop comportamentali

Se gli ultimi k tool sono identici: ∀ j ∈ [1, k], T_{n−j} = Tₙ allora: assert(false)

### 3. Enforcement di policy

assert(Tₙ ∈ whitelist)

Esempio:

```python
class AgentRunner:
    def __init__(self, max_iter=20, max_stesso_tool_consec=3):
        self.max_iter = max_iter
        self.max_stesso_tool_consec = max_stesso_tool_consec
        self.storia: list[ToolCall] = []

    def esegui(self, obiettivo: str) -> Risultato:
        for i in range(self.max_iter):
            assert len(self.storia) == i, \
                "discrepanza fra contatore iterazioni e storia"

            azione = self.modello.decidi(obiettivo, self.storia)

            # check di loop su tool ripetuti
            ultimi = self.storia[-self.max_stesso_tool_consec:]
            if len(ultimi) == self.max_stesso_tool_consec:
                stessi = all(t.nome == azione.nome and
                             t.argomenti == azione.argomenti
                             for t in ultimi)
                assert not stessi, \
                    f"loop rilevato su {azione.nome}({azione.argomenti})"

            # check di policy
            assert azione.nome in self.tool_consentiti, \
                f"tool {azione.nome} fuori dalla whitelist"

            risultato = self.esegui_tool(azione)
            self.storia.append(ToolCall(azione, risultato))

            if azione.nome == "termina":
                return risultato

        raise RuntimeError(f"agent fuori dal budget di {self.max_iter} step")
```

Le assert garantiscono la coerenza dello stato interno dell'agente e rilevano loop comportamentali che il modello non è in grado di evitare così impediscono violazioni di policy che potrebbero compromettere la sicurezza.

### Validatori di consistenza inter-chiamata

Un modello che si contraddice fra una chiamata e l'altra è un sintomo che vuoi vedere subito. Le assert qui sono cross-call, e richiedono un magazzino di fatti già asseriti dal modello.

```python
class CoerenzaTracker:
    def __init__(self):
        self.fatti: dict[str, set[str]] = {}

    def registra(self, entita: str, proprieta: str, valore: str):
        chiave = f"{entita}::{proprieta}"
        if chiave in self.fatti:
            valori_visti = self.fatti[chiave]
            valori_visti.add(valore)
            assert len(valori_visti) == 1, \
                f"contraddizione su {chiave}, valori visti: {valori_visti}"
        else:
            self.fatti[chiave] = {valore}

tracker = CoerenzaTracker()
risp1 = chiama_llm("In che continente è il Marocco?")
tracker.registra("Marocco", "continente", risp1.contenuto)
risp2 = chiama_llm("Il Marocco è africano o europeo?")
tracker.registra("Marocco", "continente", risp2.contenuto)
# assert salta se risp1 e risp2 differiscono
```

Il pattern si estende a tutte le entità tracciate in conversazioni lunghe e a vincoli di policy che il modello deve rispettare per tutta la sessione.

### Assert sulla provenienza e tracciabilità

Un controllo spesso trascurato ma estremamente utile prima di entrare nella logica di retrieval è la verifica esplicita della provenienza e della tracciabilità dei documenti e dei metadati associati. In un sistema RAG serve garantire che ogni frammento di contesto abbia un identificatore immutabile, un timestamp, una fonte dichiarata e, quando possibile, una firma e magari anche un checksum che ne certifichi l'integrità. Questi elementi permettono di distinguere tra informazioni realmente recuperate dall'indice e contenuti che il modello potrebbe aver inventato o ricostruito in modo errato. Gli assert di provenienza dovrebbero verificare la presenza e la coerenza dei metadati prima che i documenti vengano passati al modello. Ad esempio:

- `assert(d.id ≠ None)` garantisce che ogni documento abbia un identificatore; 
- `assert(d.timestamp ≤ ora_corrente)` verifica che il documento non dichiari una data futura; 
- `assert(d.checksum = hash(d.testo))` assicura l'integrità del testo; 
- `assert(d.source ∈ trusted_sources)` applica un filtro di policy sulle fonti consentite. 

Questi controlli intercettano alcuni casi ma sono abbastanza sicuro siano moltissimi. Quando un'assert di provenienza fallisce, il sistema deve registrare il documento incriminato con tutte le informazioni e questo payload diagnostico rendà riproducibile il problema facilitando la correzione. Inoltre, mantenere riferimenti immutabili ai documenti consente di implementare assert incrociati che confrontano le citazioni generate dal modello con gli ID effettivamente passati: `assert(citazioni ⊆ ids_recuperati)`.

E avere questi controlli sulla provenienza ci proiettano verso controlli più avanzati come la validazione delle affermazioni rispetto alle fonti (fact‑checking automatizzato) e la gestione delle versioni dei documenti. Integrare questi assert prima della sezione RAG riduce il rischio di allucinazioni... anche nel lettore di questo testo 🤠

### Assert su retrieval e RAG

In un sistema **RAG** (Retrieval-Augmented Generation), il modello riceve documenti recuperati da un indice e li usa per rispondere. I bug classici, documenti irrilevanti che vengono recuperati per tutto, documenti rilevanti che mai vengono recuperati, modello che ignora i documenti, allucinazioni, modello che cita documenti che mai gli sono stati passati, e qui le assert possono essere un vero tesoro:

```python
def chiama_rag(query: str) -> Risposta:
    documenti = retriever.cerca(query, top_k=5)

    assert len(documenti) > 0, \
        f"retrieval vuoto per query={query}, indice rotto?"
    assert all(d.score >= 0 for d in documenti), \
        "score negativo nel retriever"
    assert documenti == sorted(documenti, key=lambda d: -d.score), \
        "documenti non ordinati per score decrescente"

    risposta = llm.genera(query, contesto=documenti)

    # assert che le citazioni nel testo puntano a documenti recuperati
    citazioni = estrai_citazioni(risposta.testo)
    ids_recuperati = {d.id for d in documenti}
    citazioni_fantasma = citazioni - ids_recuperati
    assert not citazioni_fantasma, \
        f"modello cita doc che non esistono nel retrieval: {citazioni_fantasma}"

    return risposta
```

L'assert sulle citazioni fantasma è il caso più utile in pratica, perché pesca al volo le allucinazioni dove il modello inventa fonti bibliografiche o numeri di pratica.


# **Cosa sono i sistemi safety‑critical**

I sistemi safety‑critical sono sistemi software in cui un malfunzionamento può produrre danni a cose o persone e la loro progettazione richiede un livello di rigore che supera di molto quello dei sistemi convenzionali, poiché ogni comportamento deve essere deterministico, tracciabile e analizzabile in modo esaustivo. Il determinismo implica che lo stesso input debba produrre lo stesso output in ogni condizione operativa, senza dipendenze nascoste da stato globale, concorrenza non controllata o effetti temporali non modellati; la tracciabilità richiede che ogni riga di codice sia collegata a un requisito documentato, verificabile, giustificatoe dimostrato, in modo che l'intero sistema possa essere ricostruito logicamente a partire dalle sue specifiche. La failure analysis impone che per ogni possibile fallimento esista una risposta progettata, documentata e validata, poiché nessun comportamento imprevisto può essere tollerato in un contesto in cui un singolo errore può avere conseguenze irreversibili. In questo scenario, le assert diventano parte integrante della rete di sicurezza del sistema, con un ruolo che richiede documentazione formale, classificazione del comportamento in caso di violazione e, in alcuni casi, certificazione da parte di enti regolatori. Ogni assert deve essere giustificata, verificata e integrata nel safety case, poiché la sua presenza o assenza modifica il profilo di rischio del sistema.

Gli standard che regolano i sistemi safety‑critical definiscono in modo come le assert devono essere progettate, documentate e verificate, poiché ogni comportamento non deterministico o non tracciabile è incompatibile con i requisiti di certificazione. Lo standard DO‑178C, utilizzato in avionica civile, richiede che ogni assert sia tracciata a un requisito, coperta da test e classificata come deactivated code se disabilitata in release, con giustificazione formale, e impone criteri di copertura come MC/DC che obbligano a dimostrare che ogni condizione logica all'interno dell'assert influenzi il risultato in modo indipendente. Lo standard ISO 26262, utilizzato nell'automotive, richiede che le assert presenti nei componenti con livello ASIL elevato siano parte della safety argumentation e rimangano attive in produzione con una reazione progettata che porti il sistema in uno stato sicuro, poiché un semplice abort non è accettabile in un sistema che controlla sterzo, freni o accelerazione. Lo standard IEC 62304, utilizzato nei dispositivi medicali, richiede che le assert siano trattate come defensive checks documentati e che ogni assert disabilitata in release sia accompagnata da una giustificazione tracciabile nel software development plan. Lo standard EN 50128, utilizzato nel ferroviario, impone che le assert in codice SIL elevato siano soggette a peer review formale e che il comportamento in caso di fallimento sia giustificato e verificato. Lo standard ECSS‑E‑ST‑40C, utilizzato nel software spaziale, richiede che le assert siano integrate in un sistema più ampio di defensive programming e che il comportamento in caso di violazione sia definito in termini di transizione a safe mode o passaggio a un sistema ridondato.

# **MISRA‑C e le regole sulle assert**

MISRA‑C, lo standard di riferimento per il software automotive scritto in C, definisce regole precise sull'uso delle assert, poiché il preprocessore può rimuoverle in release e modificare il comportamento del programma. La regola più importante impone che l'argomento di un'assert sia privo di side effect, poiché un'assert che contiene un'assegnazione o una chiamata a funzione può alterare lo stato del programma quando viene disattivata tramite NDEBUG, producendo un comportamento diverso tra debug e release. Questo vincolo rende necessario separare la logica di controllo dalla logica di verifica, garantendo che l'assert sia una pura condizione booleana. Altre regole MISRA impongono che le assert non siano utilizzate in funzioni che gestiscono interrupt, poiché tali funzioni devono essere prive di comportamenti non deterministici; che non siano utilizzate in signal handler, poiché tali contesti non consentono chiamate non reentrant, che l'uso di abort sia sostituito da una funzione custom che porta il sistema in safe state e che i messaggi di assert non utilizzino funzioni variadic, poiché tali funzioni introducono complessità non verificabile.


# **SPARK Ada, contratti formali in produzione**

PARK è un sottoinsieme estremamente disciplinato di Ada, progettato con l’ambizioso obiettivo di portare la verifica formale fuori dai libri di logica e dentro il codice reale. La caratteristica più distintiva di questo guardiano della specifica formale è la capacità di trasformare le assert da semplici in contratti formali che descrivono con rigore quasi notarile quello che un programma deve fare. Il sistema è in pratica... prolog... no scherzo, ma è un dimostratore automatico che analizza il codice e tenta di provare matematicamente che ogni proprietà dichiarata nei contratti sia rispettata per tutti, proprio tutti i possibili input. Quando il dimostratore riesce SPARK elimina la corrispondente verifica dal codice generato perché non c’è motivo di controllarlo di nuovo. Naturalmente, non tutte le proprietà sono decidibili e alcune resistono alle prove automatiche e in questi casi, SPARK trasforma la proprietà in una assert dinamica, che rimane attiva a runtime ma sempre dando al programmatore una grande possibilità di movimento perché può essere modulata in base al livello di criticità del sistema.

Per esempio guardiamo questo codice semplificato che calcola la radice quadrata intera di un numero.


```ada
package Integer_Sqrt
with SPARK_Mode => On
is
   function Sqrt (N : Natural) return Natural
     with
       Pre  => N <= 10_000_000,  -- Limite arbitrario per evitare overflow
       Post => Sqrt'Result * Sqrt'Result <= N
               and (Sqrt'Result + 1) * (Sqrt'Result + 1) > N;
end Integer_Sqrt;

package body Integer_Sqrt
with SPARK_Mode => On
is
   function Sqrt (N : Natural) return Natural is
      R : Natural := 0;
   begin
      -- Invariante: R*R <= N sempre
      pragma Loop_Invariant (R * R <= N);

      while (R + 1) * (R + 1) <= N loop
         R := R + 1;
      end loop;

      -- Assert finale: R è davvero la radice intera
      pragma Assert (R * R <= N);
      pragma Assert ((R + 1) * (R + 1) > N);

      return R;
   end Sqrt;
end Integer_Sqrt;
```

---

La precondizione è `N <= 10_000_000`, l'’invariante di ciclo `R * R <= N` è la parte più accademica del codice e serve a garantire che, a ogni iterazione, il nostro `R` non diventi improvvisamente troppo grande. Se tutto fila, SPARK elimina l’invariante dal codice generato. Supponiamo che, per qualche motivo, la logica del ciclo fosse più complicata, ad esempio, se ci fosse un ramo condizionale ambiguo o un overflow potenziale, in quel caso SPARK direbbe "Mi dispiace, caro sviluppatore, ma questa proprietà non posso provarla. Te la lascio come assert dinamica, così almeno a runtime qualcuno controllerà sperando non faccia la fine di Netscape". E quell’assert rimarrebbe nel codice eseguibile.


# **Cosa fare quando un'assert fallisce in flight**

In un sistema safety‑critical, il pattern fail‑fast con abort non è accettabile, poiché un sistema di controllo non può semplicemente terminare l'esecuzione. La risposta a un'assert violata deve essere progettata, documentata e verificata, e deve garantire che il sistema rimanga in uno stato sicuro anche in presenza di un errore interno. Una possibile risposta consiste nel portare il sistema in safe state, cioè in uno stato predefinito a basso rischio che riduce al minimo le conseguenze del fallimento, un'altra consiste nel trasferire il controllo a un sistema ridondato, che continua l'operazione in modo indipendente. Un'altra ancora consiste nell'attivare un watchdog reset, che riavvia il processore e ripristina uno stato noto; un'ulteriore possibilità consiste nel continuare l'esecuzione con funzionalità ridotte, mantenendo comunque un comportamento sicuro. In ogni caso, la reazione deve essere parte del safety case e deve essere verificata tramite analisi formale, test e revisione.

Un esempio tipico di implementazione firmware è il seguente:

```c
#define SAFETY_ASSERT(cond, reazione) do {                          \
    if (!(cond)) {                                                  \
        log_safety_event(__FILE__, __LINE__, #cond);                \
        (reazione)();                                               \
    }                                                               \
} while (0)

SAFETY_ASSERT(motor_current_ok(), enter_safe_state);
SAFETY_ASSERT(sensor_plausibile(), failover_to_backup);
SAFETY_ASSERT(memoria_invariante_ok(), trigger_watchdog_reset);
```

In questo modello, ogni assert è associata a una reazione e il comportamento in caso di fallimento è parte integrante del safety case.

# **Tooling e processi di certificazione**

Il mondo safety‑critical utilizza una costellazione di strumenti che operano su livelli diversi della catena di sviluppo, e ciascuno di essi contribuisce a costruire un quadro di evidenze verificabili che confluiscono nel safety case finale. Gli strumenti di analisi statica come LDRA, Polyspace e Coverity eseguono un'analisi formale del codice sorgente, producono report di coverage MC/DC, identificano percorsi non esercitati, rilevano condizioni logiche non coperte e segnalano la presenza di assert disattivate che potrebbero alterare il comportamento del sistema in release. Gli strumenti di testing unitario come VectorCAST, Tessy e Cantata forniscono un'infrastruttura per collegare ogni assert a un requisito documentato, generare test che la esercitano, registrare l'esito e produrre un tracciato completo che dimostra la copertura funzionale e strutturale del codice. Gli strumenti di analisi semantica e temporale come Rapita, Frama‑C e Astrée analizzano il worst‑case execution time, verificano l'assenza di errori di runtime come divisioni per zero, overflow o buffer overrun e dimostrano proprietà semantiche che il compilatore non può garantire autonomamente; Astrée, in particolare, è in grado di dimostrare l'assenza di intere classi di errori su firmware automotive e avionico, fornendo una garanzia matematica che nessuna esecuzione possibile violerà gli invarianti analizzati. Le review formali rappresentano un altro pilastro del processo di certificazione, poiché ogni assert introdotta nel codice viene esaminata da revisori qualificati che chiedono spiegazioni dettagliate sulla sua collocazione, sulla sua semantica e sulle conseguenze operative di un eventuale fallimento. Ogni risposta viene registrata in un documento che confluisce nel materiale sottoposto al regolatore, e la presenza di tale documentazione diventa parte integrante della dimostrazione che il sistema è stato progettato con un livello di rigore adeguato alla sua criticità.


# **A che ci serve a noi che facciamo app per cellulare**

Anche quando si scrive software che non deve pilotare un aereo o gestire un reattore nucleare, alcune pratiche nate nel mondo dei sistemi critici pagano dividendi concreti migliorando la qualità del codice e riducendo i misteri in fase di debug e non richiedono di vendere un rene per essere adottate. Documentare esplicitamente cosa deve succedere quando un'`assert` salta trasforma un controllo anonimo in una decisione operativa. Una breve nota accanto all'`assert` che dichiara se il sistema deve loggare, degradare la funzionalità, inviare un alert o riavviare un componente evita discussioni da bar tra sviluppatori su "ma cosa succede se...", e rende chiaro al prossimo che leggerà il codice tra sei mesi se quel controllo è un campanello d'allarme o una sentenza di morte per il processo. È utile distinguere con chiarezza le `assert` progettate dalle `assert` opportunistiche. Le prime sono parte della logica di sicurezza dell'app, sono vincoli che non si possono ignorare e richiedono una reazione esplicita in produzione mentre le seconde sono controlli difensivi pensati per aiutare lo sviluppo e possono essere rimosse nelle build di release per risparmiare overhead. Introdurre convenzioni o macro come `safety_assert` e `debug_assert` ci aiuta e dice al compilatore e al team quali verifiche devono sopravvivere alla compilazione in release e quali possono essere sacrificate per il bene delle prestazioni. Questa semplice disciplina evita che una `assert` nata per aiutare diventi un fardello.

La scelta consapevole delle `assert` da mantenere attive in produzione permette di preservare gli invarianti critici ssenza perdere prestazioni. Quando un'`assert` è considerata parte della logica di sicurezza, la sua documentazione dovrebbe includere la strategia di mitigazione, i test che ne verificano l'efficacia e il piano di monitoraggio in produzione, quando è diagnostica, va marcata come tale e confinata a build di debug o a canali di telemetria non invasiva. Sapere in anticipo cosa deve succedere quando un'invariante salta significa poter automatizzare la risposta, raccogliere i dati giusti e spiegare ai product manager perché l'errore è avvenuto, senza dover ricostruire la scena come in un giallo mal scritto. E dal punto di vista operativo, mantenere una policy sulle `assert` riduce il rischio di comportamenti divergenti tra build di sviluppo e build di produzione. Le differenze tra debug e release non devono essere sorprese romantiche ma elementi noti e misurati. Integrare la scelta delle `assert` nella pipeline CI, eseguire test di regressione sia funzionali sia prestazionali e raccogliere telemetria mirata sulle violazioni consente di valutare l'impatto reale delle verifiche attive in produzione. Quindi per chi sviluppa app mobili, progettare e documentare le `assert`, distinguere tra safety e debug, adottare convenzioni chiare e automatizzare i controlli nella CI rende il codice più prevedibile, il comportamento in produzione più gestibile e le notti del team meno insonni. E' buon mestiere, e se volete aggiungere un pizzico di stile potete anche firmare le note con un'emoji di avvertimento che personalmente ritengo piacevole.

# **La psicologia delle assert e il lavoro in team**

Introdurre le `assert` in un gruppo che non le ha mai usate è una piccola rivoluzione culturale per un team abituato a debug con `print`, sessioni di gdb improvvisate e test legacy poco affidabili e che tende a vedere le `assert` come un intralcio o come un'imposizione. Il punto di ingresso più chiaramente sensato per introdurle sono i test. Nessuno si offende e ti lancia il caffè in faccia se una `assert` compare in un test perché il fallimento è il comportamento atteso e il feedback è immediato. Dopo i test, il passo successivo è quello di introdurre `assert` nei moduli interni, nelle funzioni private che non costituiscono API pubbliche. Qui le `assert` intercettano bug prima che escano dal modulo e riducono il costo del debug. Il rischio percepito resta basso e il valore percepito cresce rapidamente, perché i problemi vengono catturati vicino alla fonte.

Quando i moduli diventano più affidabili, si può estendere la pratica a invarianti di rappresentazione su classi delicate. Funzioni private come `checkRep` chiamate ai confini delle operazioni pubbliche rendono esplicite le proprietà che devono valere sempre. A questo punto la `assert` diventa una promessa esplicita al chiamante e nelle code review non si discute più se aggiungere l'`assert`, ma quale garanzia essa esprime e se quella garanzia è corretta.

Ma attenzione il comportamento quando un'`assert` salta in produzione deve essere deciso a priori e documentato. Un buon approccio prevede log strutturati con contesto, metriche che contano le violazioni, feature flag per disabilitare temporaneamente verifiche non critiche e procedure di escalation automatica per le `safety_assert`. Invece il post‑mortem deve concentrarsi sulle assunzioni sbagliate. La trasformazione culturale si consolida quando emergono esempi concreti come quella di un'`assert` che ha evitato un incidente, una race condition intercettata prima del rilascio, un refactoring che non ha rotto invarianti critici. Questi casi diventano storie condivise che legittimano la pratica e la rendono parte dell'identità tecnica del team. Per rendere il cambiamento pratico e misurabile, conviene introdurre regole come il numero di `assert` attive in produzione e confrontare con i bug trovati e la velocità di prototipazione. Questi numeri trasformano una sensazione soggettiva in evidenza oggettiva e aiutano a calibrare la strategia. Se siete sopravvissuti fino a questo punto e vi viene in mente qualcosa che ho dimenticato, e c'è un sacco di roba da aggiungere in teoria, provate a proporla.

# **Assert(documento == Concluso) = False**

E ora, signore e signori, prima che le lampade a olio si spengano del tutto e il vento del deserto torni a fischiare tra le assi del tendone, devo confessarvi una cosa che un presentatore non dovrebbe mai dire, ma che in questo circo è più vera di qualunque numero andato a buon fine: lo spettacolo che avete visto finora non è completo perché dietro le quinte gli artisti stanno ancora provando, le assert continuano a scappare dalle gabbie, gli algoritmi si rifiutano di entrare in scena senza prima discutere con la statistica e io stesso non ho ancora finito di scrivere la scaletta, che cambia ogni volta che qualcuno accende una lanterna o sposta una variabile, e così questo documento resta aperto come un cavallo selvaggio che non vuole farsi sellare, e voi dovrete tornare, prima o poi, per vedere come andrà a finire, perché il circo delle asserzioni fantastiche non chiude mai davvero, si limita a prendere la rincorsa e a preparare il prossimo salto, e io sarò qui, con il cappello storto e la voce roca, pronto a darvi il benvenuto quando il resto dello spettacolo sarà finalmente pronto a mostrarsi.



---

Eccoti il testo **completo**, **pulito**, **pronto da incollare** nella tua pagina, in **doppia lingua** (Italiano + Inglese), formulato in modo chiaro e legalmente sensato per la licenza **CC BY‑NC‑ND 4.0 con eccezione esplicita per la traduzione**.

Ho mantenuto un tono professionale, perché questa è una sezione che deve risultare credibile anche in contesti formali.  
Puoi però chiedermi una versione più teatrale, più circense o più “vecchio West”.

---


# 📜 **Licenza (IT + EN)**


## 🇮🇹 **Italiano**

Questo documento è rilasciato sotto licenza **Creative Commons CC BY‑NC‑ND 4.0**.  
È consentita la **condivisione** del testo, a condizione che:

- venga fornita **attribuzione** all’autore;  
- non venga effettuato **alcun uso commerciale**;  
- il contenuto non venga **modificato**, **adattato**, **remixato** o trasformato in alcun modo.

**Eccezione per la traduzione:** In deroga alla clausola *ND (NoDerivatives)*, è **espressamente consentita la traduzione integrale** del documento, purché:

- la traduzione sia **fedele** al testo originale;  
- venga mantenuta l’**attribuzione** all’autore;  
- non venga effettuato **alcun uso commerciale**;  
- sia chiaramente indicato che si tratta di una **traduzione autorizzata**.

Qualsiasi altra forma di modifica o opera derivata non è permessa.

---

## 🇬🇧 **English**

This document is licensed under the **Creative Commons CC BY‑NC‑ND 4.0** license.  
You may **share** the text provided that:

- proper **attribution** is given to the author;  
- no **commercial use** is made;  
- the content is not **modified**, **adapted**, **remixed**, or transformed in any way.

**Translation Exception**: As an explicit exception to the *ND (NoDerivatives)* clause, **full and faithful translations** of this document are permitted, provided that:

- the translation remains **faithful** to the original text;  
- proper **attribution** to the author is maintained;  
- no **commercial use** is made;  
- it is clearly stated that the work is an **authorized translation**.

Any other form of modification or derivative work is not allowed.

---
