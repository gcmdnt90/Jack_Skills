---
name: grill-with-docs
description: Sessione di interrogazione che mette alla prova il tuo piano rispetto al modello di dominio esistente, affina la terminologia e aggiorna la documentazione (CONTEXT.md, ADR) man mano che le decisioni si consolidano. Usala quando l'utente vuole verificare un piano rispetto al linguaggio e alle decisioni documentate del progetto, definire i termini del dominio, o dice "intervistami con i documenti", "interrogami con la documentazione", "definizione", "linguaggio del dominio", "glossario", "grill with docs".
---

<cosa-fare>

Intervistami senza tregua su ogni aspetto di questo piano finché non raggiungiamo una comprensione condivisa. Percorri ogni ramo dell'albero di progettazione, risolvendo una alla volta le dipendenze tra le decisioni. Per ogni domanda, proponi la tua risposta consigliata.

Fai le domande una alla volta, aspettando un riscontro su ciascuna domanda prima di proseguire.

Se una domanda può trovare risposta esplorando il codice, esplora il codice invece di chiedere.

</cosa-fare>

<informazioni-di-supporto>

## Consapevolezza del dominio

Durante l'esplorazione del codice, cerca anche la documentazione esistente:

### Struttura dei file

La maggior parte dei repository ha un singolo contesto:

```
/
├── CONTEXT.md
├── docs/
│   └── adr/
│       ├── 0001-ordini-event-sourced.md
│       └── 0002-postgres-per-il-write-model.md
└── src/
```

Se nella radice esiste un file `CONTEXT-MAP.md`, il repository ha più contesti. La mappa indica dove si trova ciascuno:

```
/
├── CONTEXT-MAP.md
├── docs/
│   └── adr/                          ← decisioni a livello di sistema
├── src/
│   ├── ordini/
│   │   ├── CONTEXT.md
│   │   └── docs/adr/                 ← decisioni specifiche del contesto
│   └── fatturazione/
│       ├── CONTEXT.md
│       └── docs/adr/
```

Crea i file con pigrizia — solo quando hai qualcosa da scrivere. Se non esiste alcun `CONTEXT.md`, crealo quando il primo termine viene definito. Se non esiste alcuna cartella `docs/adr/`, creala quando serve il primo ADR.

## Durante la sessione

### Confronta con il glossario

Quando l'utente usa un termine che è in conflitto con il linguaggio già presente in `CONTEXT.md`, segnalalo subito. "Il tuo glossario definisce 'cancellazione' come X, ma sembri intendere Y — quale dei due?"

### Affina il linguaggio impreciso

Quando l'utente usa termini vaghi o sovraccarichi di significato, proponi un termine canonico preciso. "Stai dicendo 'account' — intendi il Cliente o l'Utente? Sono due cose diverse."

### Discuti scenari concreti

Quando si discutono le relazioni del dominio, mettile alla prova con scenari specifici. Inventa scenari che sondano i casi limite e costringono l'utente a essere preciso sui confini tra i concetti.

### Verifica incrociando con il codice

Quando l'utente afferma come funziona qualcosa, controlla se il codice è d'accordo. Se trovi una contraddizione, falla emergere: "Il tuo codice cancella interi Ordini, ma hai appena detto che è possibile la cancellazione parziale — qual è quella corretta?"

### Aggiorna CONTEXT.md sul momento

Quando un termine viene definito, aggiorna `CONTEXT.md` lì per lì. Non accumularli — registrali nel momento in cui emergono. Usa il formato in [CONTEXT-FORMAT.md](./CONTEXT-FORMAT.md).

`CONTEXT.md` deve essere completamente privo di dettagli implementativi. Non trattare `CONTEXT.md` come una specifica, un foglio di appunti o un contenitore per decisioni implementative. È un glossario e nient'altro.

### Proponi gli ADR con parsimonia

Proponi di creare un ADR solo quando tutte e tre le condizioni sono vere:

1. **Difficile da invertire** — il costo di cambiare idea in seguito è significativo
2. **Sorprendente senza contesto** — chi leggerà in futuro si chiederà "perché l'hanno fatto così?"
3. **Il risultato di un vero compromesso** — c'erano alternative reali e ne hai scelta una per motivi specifici

Se manca anche una sola delle tre, salta l'ADR. Usa il formato in [ADR-FORMAT.md](./ADR-FORMAT.md).

</informazioni-di-supporto>

<!--
Adattamento e traduzione in italiano della skill "grill-with-docs" di Matt
Pocock (mattpocock/skills), distribuita con licenza MIT. Vedi CREDITS.md nella
radice del repository per la nota di copyright e la licenza complete.
-->
