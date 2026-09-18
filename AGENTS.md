# Istruzioni obbligatorie — Libro giornale, partita doppia e liquidazione IVA

> **A chi legge questo file (assistente AI):** questo repository è la fonte canonica delle istruzioni personali dello studente per questi esercizi.
>
> **Ordine operativo obbligatorio per ogni nuovo esercizio:**
> 1. Leggi **integralmente il testo dell'esercizio inviato dallo studente** prima di iniziare.
> 2. Poi leggi **integralmente questo file `AGENTS.md`**.
> 3. Consulta anche [`piano-dei-conti.md`](piano-dei-conti.md) e, se una denominazione è dubbia, confrontala con le fotografie originali nelle cartelle `riferimenti/`.
> 4. Solo dopo svolgi l'esercizio applicando tutte le regole qui sotto.
> 5. Se il repository è accessibile, preferisci sempre la versione corrente dei file del repository a copie vecchie ricordate da chat precedenti.

## 0. Procedura da seguire per ogni esercizio

1. Leggi l'intero testo dell'esercizio prima di scrivere qualunque scrittura.
2. Per ogni operazione individua: quali conti sono coinvolti, se sono finanziari o economici, se stanno aumentando o diminuendo.
3. Applica le regole delle Sezioni 1-4.
4. Usa **esclusivamente** i conti elencati nella Sezione 5 e in [`piano-dei-conti.md`](piano-dei-conti.md). Non crearne di nuovi anche se sembrano plausibili: se manca un conto necessario, segnalalo invece di inventarlo.
5. Se l'operazione dipende da un'aliquota, una soglia, una scadenza o un regime particolare, verifica che l'informazione sia ancora aggiornata invece di affidarti solo alla memoria (vedi Sezione 6).
6. Prima di mostrare la risposta, passa dalla checklist della Sezione 7. Correggi ogni scrittura che non la supera.
7. Se sei incerto tra due trattamenti contabili possibili, dillo esplicitamente e motiva la scelta fatta, invece di deciderne uno in silenzio.
8. Se per completare una scrittura hai dovuto assumere qualcosa non specificato nel testo, dichiaralo nella risposta.

## 1. Il metodo della partita doppia

Il libro giornale registra in ordine cronologico ogni operazione di gestione (art. 2216 c.c.: il libro giornale "deve indicare giorno per giorno le operazioni relative all'esercizio dell'impresa"; obbligo di tenuta ex art. 2214 c.c.). Ogni scrittura ha sempre almeno un conto in Dare e uno in Avere, e:

**Totale Dare = Totale Avere, in ogni singola scrittura.**

I conti si distinguono in due famiglie:

| Categoria | Esempi | DARE | AVERE |
|---|---|---|---|
| Conti finanziari | Cassa, Banca c/c, Crediti v/clienti, Debiti v/fornitori, IVA a credito, IVA a debito, Cambiali attive/passive | Variazione Numeraria Attiva (VNA): aumento di liquidità/crediti, diminuzione di debiti | Variazione Numeraria Passiva (VNP): diminuzione di liquidità/crediti, aumento di debiti |
| Conti economici | Merci c/acquisti, Merci c/vendite, Salari, Interessi attivi/passivi, Fitti passivi, Costi di gestione | Variazione Economica Negativa (VEN): costi, oneri | Variazione Economica Positiva (VEP): ricavi, proventi |

Domanda guida per ogni conto coinvolto: *è finanziario o economico? sta aumentando o diminuendo? è un costo o un ricavo?* La risposta determina automaticamente Dare o Avere — non decidere "a sensazione".

## 2. Formato obbligatorio di ogni scrittura

Ogni scrittura deve riportare, nell'ordine: data, numero progressivo, breve descrizione dell'operazione, conto/i in Dare con importo, conto/i in Avere con importo.

Esempio:

```text
N. 12 — 05/03/20XX — Acquisto merci a credito da Fornitore Rossi, fattura n. 340
Merci c/acquisti ................. Dare    1.000,00
IVA a credito .................... Dare      220,00
     a Debiti verso fornitori ............ Avere   1.220,00
```

> Nell'esercizio reale usa sempre la **denominazione esatta** prevista dal piano dei conti autorizzato.

## 3. Gestione dell'IVA

Aliquote indicate nel protocollo al 17/09/2026: **22% ordinaria**, ridotte **10%, 5%, 4%** per beni e servizi specifici. Usa l'aliquota indicata nel testo dell'esercizio; se non è indicata, usa il 22% salvo che il bene/servizio rientri chiaramente in una categoria agevolata. Se il dato è normativamente rilevante o può essere cambiato, applica la Sezione 6 e verificalo su fonte ufficiale aggiornata.

### 3.1 Acquisti → IVA a credito

```text
Merci c/acquisti (o altro costo) ......... Dare  [imponibile]
IVA a credito ............................. Dare  [imponibile × aliquota]
     a Debiti verso fornitori / Cassa / Banca .... Avere [totale]
```

Nel caso concreto sostituisci le etichette generiche con i conti **esatti** presenti nel piano autorizzato.

### 3.2 Vendite → IVA a debito

```text
Crediti verso clienti / Cassa / Banca .... Dare  [totale]
     a Merci c/vendite (o altro ricavo) .......... Avere [imponibile]
     a IVA a debito ............................... Avere [imponibile × aliquota]
```

### 3.3 Liquidazione periodica dell'IVA

A fine periodo si confrontano IVA a debito e IVA a credito tramite **IVA c/liquidazione**.

**Passo 1 — giro dell'IVA a credito:**

```text
IVA c/liquidazione ........... Dare   [totale IVA a credito del periodo]
     a IVA a credito ................ Avere  [totale IVA a credito del periodo]
```

**Passo 2 — giro dell'IVA a debito:**

```text
IVA a debito ................. Dare   [totale IVA a debito del periodo]
     a IVA c/liquidazione ........... Avere  [totale IVA a debito del periodo]
```

**Passo 3 — si legge il saldo di IVA c/liquidazione e lo si chiude:**

Se il saldo è **Avere** (IVA a debito > IVA a credito), l'impresa deve versare la differenza:

```text
IVA c/liquidazione ........... Dare   [differenza]
     a Debiti per IVA ............... Avere  [differenza]
```

Se il saldo è **Dare** (IVA a credito > IVA a debito), l'impresa ha un credito IVA:

```text
Crediti per IVA .............. Dare   [differenza]
     a IVA c/liquidazione ........... Avere  [differenza]
```

**Passo 4 — al momento del versamento** (solo se dal Passo 3 risulta un debito), usare il conto bancario esatto previsto dall'esercizio e dal piano:

```text
Debiti per IVA ............... Dare   [importo]
     a Banca [conto autorizzato] .... Avere  [importo]
```

Le scadenze e i requisiti per periodicità mensile/trimestrale possono cambiare: quando servono per risolvere l'esercizio, verificare sempre la normativa aggiornata secondo la Sezione 6.

## 4. Altre operazioni ricorrenti — checklist di riconoscimento

Quando l'operazione rientra in una di queste categorie, presta particolare attenzione prima di scrivere la scrittura:

- **Cambiali**: attive per chi le riceve come creditore (Dare), passive per chi le emette come debitore (Avere).
- **Sconti, abbuoni, resi** su acquisti/vendite: rettificano il costo/ricavo e, quando previsto, l'IVA proporzionalmente; non vanno confusi con altre voci.
- **Incassi/pagamenti diretti** in Cassa o Banca c/c, distinti da quelli "a credito".
- **Costituzione dell'azienda e conferimenti** del titolare/soci.
- **Scritture di assestamento** (ratei, risconti, ammortamenti): trattale solo se l'esercizio le richiede esplicitamente.


### 4.1 Regole anti-errore su trasporti, anticipazioni, interessi e bollo

Queste regole sono state aggiunte dopo il controllo completo dell'esercizio 6.20 e servono a evitare errori già commessi in passato.

#### A. Trasporto e anticipazioni: costruire sempre la timeline prima della scrittura

Prima di registrare un trasporto, separa obbligatoriamente questi elementi:

1. chi sostiene economicamente il costo;
2. chi paga materialmente il vettore;
3. a chi è intestata la fattura del vettore;
4. se il pagamento è effettuato **in nome e per conto** della controparte;
5. se l'importo viene poi recuperato/riaddebitato.

Regole operative:

- Se il vettore fattura direttamente all'impresa, il costo di trasporto e la relativa IVA si registrano **una sola volta** dalla fattura del vettore.
- Se un fornitore paga quella fattura **in nome e per conto** dell'impresa, il successivo rimborso al fornitore **non crea un secondo costo e non crea una seconda IVA**: si chiude il debito verso il vettore e si trasferisce la somma nel debito verso il fornitore che ha anticipato.
- Se invece è l'impresa ad anticipare in contanti o banca una spesa **in nome e per conto del cliente**, usare il conto autorizzato **05.03 Clienti c/costi anticipati** al momento dell'uscita; quando la somma viene recuperata in fattura, il medesimo conto si chiude. Non trasformare il rimborso in ricavo di vendita.
- Prima di confermare la scrittura, verifica che nessuno stesso trasporto compaia due volte come costo o che la stessa IVA sia stata detratta due volte.

#### B. Distinguere con precisione: imponibile, escluso, esente

Non usare mai come sinonimi “fuori IVA”, “escluso” ed “esente”.

- **Spese accessorie** (es. trasporto, imballaggio) effettuate dal cedente/prestatore o per suo conto e a sue spese, quando accessorie a un'operazione imponibile, seguono l'operazione principale e concorrono alla base imponibile IVA (art. 12 DPR 633/1972).
- **Anticipazioni documentate in nome e per conto della controparte** sono **escluse dalla base imponibile** (art. 15, c. 1, n. 3 DPR 633/1972).
- **Interessi moratori e penalità per ritardi/irregolarità** sono **esclusi dalla base imponibile** (art. 15, c. 1, n. 1 DPR 633/1972).
- **Interessi per una dilazione di pagamento concordata** sono invece **operazioni esenti IVA**, perché rientrano nelle operazioni finanziarie/dilazioni di pagamento dell'art. 10, c. 1, n. 1 DPR 633/1972. In questo caso la parola corretta è “esente”, non “escluso”.

Prima di scrivere “esente” o “escluso”, individua quindi la causa giuridica concreta.

#### C. Interessi calcolati a giorni: non assumere 365 o 360 senza controllo

Se la traccia indica tasso e giorni ma **non specifica la convenzione temporale**:

1. controlla prima gli esempi svolti dello stesso libro/capitolo;
2. se il libro usa anno civile: formula con denominatore **36.500**;
3. se il libro usa anno commerciale: formula con denominatore **36.000**;
4. se la convenzione non è ricavabile dal materiale disponibile, **non scegliere in silenzio**: dichiara l'ambiguità e chiedi conferma allo studente oppure presenta entrambi i risultati.

Esempio generale:
- anno civile: I = C × r × g / 36.500;
- anno commerciale: I = C × r × g / 36.000.

La normativa IVA stabilisce il trattamento fiscale degli interessi, ma **non decide la convenzione didattica 360/365 usata dal libro**.

#### D. Imposta di bollo: separare regola fiscale e scelta del conto

Quando compare il bollo:

- verifica su fonte ufficiale l'importo e la soglia applicabili; al controllo effettuato nel 2026, per le fatture interessate il bollo è di **2 euro** e la soglia rilevante è **77,47 euro**;
- non dedurre automaticamente il conto contabile dalla sola regola fiscale;
- lato acquirente, un bollo addebitato può essere rilevato come costo usando il conto autorizzato previsto dal manuale;
- lato venditore, il **recupero del bollo dal cliente** può essere trattato diversamente a seconda dell'impostazione didattica del libro (ad esempio come debito fiscale oppure come recupero/nettizzazione del costo). Prima di scegliere, controlla un esempio già svolto dello stesso libro;
- se il manuale non chiarisce la convenzione, dichiarare il punto come **scelta contabile da verificare** e non presentarla come obbligo univoco.

#### E. Controllo dei mastri IVA

Quando si costruisce il mastro **16.01 IVA c/liquidazione**, controllare non solo gli importi ma anche la colonna:

- giro IVA a credito → **IVA c/liquidazione in Dare**;
- giro IVA a debito → **IVA c/liquidazione in Avere**;
- se emerge debito IVA, chiusura verso **14.03 Debiti per IVA** → **IVA c/liquidazione in Dare**.

Un errore di formattazione Dare/Avere nel mastro è un errore contabile anche se il totale numerico è corretto.

#### F. Diagnosi obbligatoria prima della risposta

Se una soluzione precedente è stata corretta, individua sempre **perché** era nata l'errore e trasforma la causa in un controllo preventivo. In particolare, evitare:

- duplicazione dello stesso costo/IVA quando c'è un'anticipazione;
- confusione tra debito verso vettore e debito verso fornitore che anticipa;
- uso indistinto di “esente” ed “escluso”;
- scelta automatica di 365 giorni senza verificare la convenzione del libro;
- scelta automatica del conto del bollo senza controllare l'impostazione didattica;
- mastri formalmente sbagliati anche quando i totali quadrano.

## 5. Piano dei conti autorizzato

Il piano dei conti autorizzato è **quello fotografato nelle pagine 588-589** e trascritto integralmente in:

**[`piano-dei-conti.md`](piano-dei-conti.md)**

Le fotografie originali sono:

- [`riferimenti/piano-dei-conti-pag-588.jpg`](riferimenti/piano-dei-conti-pag-588.jpg)
- [`riferimenti/piano-dei-conti-pag-589.jpg`](riferimenti/piano-dei-conti-pag-589.jpg)

### Regola bloccante

**Non usare conti esterni all'elenco. Non inventare denominazioni.**

Se un esercizio richiede apparentemente un conto non presente:

1. ricontrolla il testo dell'esercizio;
2. ricontrolla `piano-dei-conti.md`;
3. se resta assente, scrivi chiaramente che il conto necessario non compare nel piano autorizzato;
4. chiedi conferma allo studente prima di introdurre qualunque denominazione esterna.

## 6. Verifica normativa — parte obbligatoria quando pertinente

Le regole di logica contabile (Dare/Avere, meccanismo IVA a credito/debito, quadratura) sono concettualmente stabili.

Invece **aliquote, soglie di fatturato, scadenze di versamento e regimi particolari** (reverse charge, split payment, beni usati, regime forfettario, ecc.) possono cambiare.

Regola pratica: se un'operazione dipende da uno di questi elementi e c'è anche solo un minimo dubbio che possa essere cambiato, **cerca l'informazione aggiornata su fonti ufficiali o primarie** (ad esempio Agenzia delle Entrate, Normattiva/Codice Civile, DPR 633/1972 vigente) prima di applicarla, e cita la fonte nella risposta.

Non fingere una verifica online se non è stata effettivamente eseguita. Se l'accesso a fonti aggiornate non è disponibile, dichiaralo.

## 7. Checklist finale prima di consegnare la risposta

- [ ] Ho letto l'intero esercizio prima di registrare?
- [ ] Ho letto integralmente questo `AGENTS.md`?
- [ ] In ogni scrittura, **Totale Dare = Totale Avere**?
- [ ] Ogni conto usato è presente in `piano-dei-conti.md`?
- [ ] L'aliquota IVA applicata è quella indicata/corretta per l'operazione?
- [ ] Numerazione progressiva e date sono coerenti e in ordine cronologico?
- [ ] Se è presente una liquidazione IVA, il confronto debito/credito e il verso del saldo finale sono corretti?
- [ ] Se l'operazione ha implicazioni normative specifiche, sono state verificate su fonte aggiornata?
- [ ] Ogni scrittura ha una descrizione chiara e coerente con l'operazione?
- [ ] Ho dichiarato eventuali assunzioni o dati mancanti?
- [ ] Se ci sono interessi a giorni, ho verificato se il libro usa 360 o 365 giorni invece di assumere una convenzione?
- [ ] Ho distinto correttamente spese accessorie imponibili, anticipazioni escluse, interessi moratori esclusi e interessi di dilazione esenti?
- [ ] Se c'è un'anticipazione di trasporto, ho verificato che costo e IVA non siano duplicati e che i debiti verso i soggetti coinvolti siano cronologicamente coerenti?
- [ ] Se c'è un recupero del bollo, ho verificato la convenzione contabile usata dal libro prima di scegliere il conto?
- [ ] Nei mastri IVA ho controllato anche la colonna Dare/Avere, non solo i totali?
- [ ] Ho corretto tutti gli errori trovati prima di mostrare il risultato?

**Se anche un solo punto non è soddisfatto, correggere prima di rispondere.**
