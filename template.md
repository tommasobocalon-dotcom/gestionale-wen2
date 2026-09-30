# PRD Template

# PRD di ScuolaChill · Team [nome del team]

<aside>
💡

**Come usare questo template**

Duplica questa pagina e compilala con il tuo team. Dove trovi del testo in *corsivo*, sostituiscilo con il vostro. I callout 💡 sono consigli per te: cancellali prima della consegna da questo markdown.

Il documento ha due parti. Nella prima scrivi **cosa** fa ScuolaChill, nella seconda **come** lo costruirai. Tienile separate. Chi legge la prima parte deve capire tutto senza sapere cos'è Spring Boot.

Un buon PRD sta fra le 15 e le 25 pagine. Se ne scrivi di più, probabilmente stai descrivendo invece di decidere.

</aside>

---

## Informazioni sul documento

|  |  |
| --- | --- |
| **Prodotto** | ScuolaChill |
| **Team** | *nome del team* |
| **Autori** | *nome e cognome di ogni membro* |
| **Versione** | *1.0* |
| **Data** | *gg/mm/aaaa* |
| **Stato** | *Bozza · In revisione · Validato* |

### Storico delle versioni

| Versione | Data | Autore | Cosa è cambiato e perché |
| --- | --- | --- | --- |
| 1.0 | *gg/mm/aaaa* | *nome* | Prima stesura |
|  |  |  |  |

<aside>
💡

Il PRD cambierà durante l'anno. Ogni modifica va registrata qui, con la sua ragione. Un PRD che dice una cosa mentre il codice ne fa un'altra è peggio di nessun PRD.

</aside>

---

# Prima parte · Il cosa

## Scopo e perimetro

### Perché esiste ScuolaChill

**Dal lato business.** *Quale problema risolve, e per chi. Due o tre frasi.*

**Dal lato tecnico.** *Cosa copre il sistema, in grandi linee. Due o tre frasi.*

### Cosa è incluso

- *Esempio: gestione di classi, docenti e studenti da parte del Direttore*
- *…*

### Cosa non è incluso

- *Esempio: ScuolaChill non gestisce le assenze né le comunicazioni con le famiglie*
- *…*

<aside>
💡

La lista di cosa **non** è incluso è la più preziosa del documento. Ogni riga qui ti evita una settimana di discussioni più avanti.

</aside>

---

## Stakeholder

| Stakeholder | Cosa fa | Cosa gli interessa | Come lo coinvolgete |
| --- | --- | --- | --- |
| Direttore | *…* | *…* | *…* |
| Docenti | *…* | *…* | *…* |
| Studenti | *…* | *…* | *…* |
| Docente del corso | Valida il PRD | *…* | Presentazione e domande |
| Collaudatori del primo anno | Usano ScuolaChill come utenti reali | *…* | *Intervista, collaudo* |
| *Altri?* |  |  |  |

<aside>
💡

Gli stakeholder non sono solo gli utenti. Sono anche chi approva, chi paga, chi manterrà il sistema. Chiediti chi resterebbe deluso se ScuolaChill non funzionasse.

</aside>

---

## Destinatari e contesto d'uso

### La scuola che avete immaginato

*Descrivi la scuola per cui progettate. Che tipo di istituto è, dove si trova, come si organizza la giornata. Questi dati tornano nella stima del carico, quindi scegli numeri che poi userai davvero.*

|  | Valore |
| --- | --- |
| Numero di studenti | *…* |
| Numero di docenti | *…* |
| Numero di classi | *…* |
| Orario scolastico | *es. 8:00 – 14:00, dal lunedì al venerdì* |
| Connettività | *es. Wi-Fi scolastico condiviso, rete mobile degli studenti, …* |

### Gli archetipi

Arricchisci gli archetipi della traccia.

| ID | Archetipo | Contesto d'uso | Competenze digitali | Dispositivo principale | Frequenza d'uso |
| --- | --- | --- | --- | --- | --- |
| ARC-001 | Direttore | *…* | *…* | *…* | *…* |
| ARC-002 | Docente | *…* | *…* | *…* | *…* |
| ARC-003 | Studente | *…* | *…* | *…* | *…* |

<aside>
💡

I collaudatori veri sono i ragazzi del primo anno. Usano lo smartphone in corridoio o il PC in laboratorio? La risposta cambia l'interfaccia, i requisiti di usabilità e perfino il dimensionamento.

</aside>

---

## Panoramica e casi d'uso

### ScuolaChill in poche righe

*Racconta ScuolaChill come lo spiegheresti al Direttore in un minuto. Niente termini tecnici.*

### User flow e scenari

Per ogni ruolo, scegli **almeno tre** storie principali e descrivi il percorso completo.

**Storia:** *es. STU-02 · Svolgere una verifica*

**User flow**

1. *Lo studente accede a ScuolaChill*
2. *Apre la sezione Verifiche*
3. *…*

**Scenario principale.** *Racconta il caso in cui tutto va bene, con un personaggio e una situazione concreta.*

**Scenari alternativi.** *Cosa succede quando qualcosa va storto? Connessione che cade, scadenza superata, doppia scheda aperta…*

*Ripeti il blocco per le storie principali di Direttore e Docente.*

---

## Requisiti funzionali

### Le user story della traccia

| ID | Storia | AC aggiunti dal team | Note |
| --- | --- | --- | --- |
| DIR-01 | Creare account docente | *…* | *…* |
| DIR-02 | Creare account studente | *…* | *…* |
| DIR-03 | Creare classi e comporle | *…* | *…* |
| DIR-04 | Vedere tutto | *…* | *…* |
| DOC-01 | Caricare materiale didattico | *…* | *…* |
| DOC-02 | Creare le proprie verifiche | *…* | *…* |
| DOC-03 | Assegnare i voti | *…* | *…* |
| STU-01 | Consultare il materiale didattico | *…* | *…* |
| STU-02 | Svolgere una verifica | *…* | *…* |
| STU-03 | Consultare i propri voti | *…* | *…* |

<aside>
💡

Gli acceptance criteria della traccia sono il minimo. Puoi aggiungerne, non toglierne. Scrivi quelli nuovi nello stesso formato *Dato che / Quando / Allora*.

</aside>

### Le decisioni lasciate aperte dalla traccia

La traccia lascia alcune scelte a te. Ognuna diventa un requisito con il suo ID. Usa questo formato.

> **FR-[AREA]-[NN] · [Titolo]** (collegato a *ID della storia*)
*Cosa avete deciso, in modo verificabile.Motivazione:* *perché avete scelto così.*
> 

I punti che devi decidere almeno sono questi.

- [ ]  La scala dei voti (DOC-03). Da quanto a quanto, con quale passo, se ammette segni come "+" e "−".
- [ ]  Il trasferimento di uno studente fra classi (DIR-03). Si può fare? Cosa succede ai voti?
- [ ]  La modifica di una verifica dopo lo svolgimento (DOC-02).
- [ ]  La connessione che cade durante una verifica (STU-02).
- [ ]  Il fallimento del servizio esterno (per esempio l'email delle credenziali).
- [ ]  *Altre decisioni che il team ha scoperto*

---

## Requisiti non funzionali

Ogni requisito ha una soglia, una condizione e un modo per verificarlo. Ed è collegato ad almeno una user story.

| ID | Famiglia | Requisito | Soglia e condizione | Come si verifica | Storie collegate |
| --- | --- | --- | --- | --- | --- |
| NFR-01 | Prestazioni | *es. Apertura della verifica nel picco* | *es. meno di 2 s per il 95% delle richieste, 75 utenti nello stesso minuto* | *Test di carico* | *STU-02* |
| NFR-02 | Sicurezza | *…* | *…* | *…* | *…* |
| NFR-03 | Usabilità | *…* | *…* | *…* | *…* |
| NFR-04 | Disponibilità | *…* | *…* | *…* | *…* |
| NFR-05 | Ambientale | *…* | *…* | *…* | *…* |
| NFR-06 | Supporto | *…* | *…* | *…* | *…* |
| NFR-07 | Interazione | *…* | *…* | *…* | *…* |
| NFR-08 | Conformità | *…* | *…* | *…* | *…* |

<aside>
💡

Le famiglie da coprire sono queste. **Prestazioni, disponibilità, scalabilità, sicurezza** e **conformità** vengono dalla lezione sui requisiti funzionali e non funzionali. **Usabilità, ambientali, supporto** e **interazione** vengono dalla lezione sul PRD. Se una famiglia resta vuota, scrivi perché non vi riguarda.

I requisiti trasversali della traccia (HTTPS, paginazione, OpenAPI, errori uniformi, Dev e Prod) sono già obbligatori. Riportali qui con il loro ID.

</aside>

### Requisiti impliciti

Prima di chiudere questa sezione, intervista per dieci minuti un ragazzo del primo anno. La domanda è una sola. *"Cosa daresti per scontato che un'app di questo tipo faccia sempre, o non faccia mai?"*

| Chi avete intervistato | Cosa ha detto | Requisito che ne avete ricavato |
| --- | --- | --- |
| *nome o iniziali* | *"Il voto non deve sparire, mai"* | *NFR-…* |
|  |  |  |

---

## Assunzioni, vincoli e dipendenze

### Assunzioni

Quello che date per vero senza poterlo garantire.

| ID | Assunzione | Cosa succede se è falsa |
| --- | --- | --- |
| ASS-01 | *es. La scuola ha 800 studenti e 60 docenti* | *Il dimensionamento va rifatto* |
|  |  |  |

### Vincoli

I limiti che non potete cambiare.

| ID | Vincolo | Da dove viene |
| --- | --- | --- |
| VIN-01 | *es. Il budget cloud è quello dei crediti studente* | *Traccia del progetto* |
|  |  |  |

### Dipendenze

Le cose esterne senza cui non potete andare avanti.

| ID | Dipendenza | Serve entro | Chi se ne occupa |
| --- | --- | --- | --- |
| DIP-01 | *es. Account attivo sul servizio email* | *Prima del collaudo* | *nome* |
|  |  |  |  |

---

# Seconda parte · Il come

<aside>
💡

Da qui in poi parli al tuo docente e al tuo team, non al Direttore. Ogni scelta tecnica va motivata e confrontata con almeno un'alternativa. "Lo conosciamo" è una motivazione valida, ma non può essere l'unica.

</aside>

## Stima del carico

### Utenti concorrenti

| Situazione | Utenti concorrenti | Da dove viene il numero |
| --- | --- | --- |
| Uso normale durante la giornata | *…* | *…* |
| Picco delle 9:00 (verifiche) | *…* | *…* |
| Fine quadrimestre (voti) | *…* | *…* |

### Profilo di carico

| Operazione | Frequente? | Pesante? | Critica? | Note |
| --- | --- | --- | --- | --- |
| Login | *…* | *…* | *…* | *…* |
| Apertura verifica | *…* | *…* | *…* | *…* |
| Consegna verifica | *…* | *…* | *…* | *…* |
| Dashboard del Direttore | *…* | *…* | *…* | *…* |
| Caricamento materiale | *…* | *…* | *…* | *…* |

<aside>
💡

I numeri di qui devono essere coerenti con la scuola che avete immaginato e con i requisiti non funzionali. Se dichiarate 800 studenti, non potete dimensionare per 20 utenti senza spiegare perché.

</aside>

---

## Scelte tecnologiche

| Area | Scelta | Alternativa considerata | Perché avete scelto così |
| --- | --- | --- | --- |
| Backend | *…* | *…* | *…* |
| Frontend | *…* | *…* | *…* |
| Database | *…* | *…* | *…* |
| Provider cloud | *…* | *…* | *…* |
| Servizi cloud | *…* | *…* | *…* |
| Regione | *…* | *…* | *…* |
| Servizio esterno | *…* | *…* | *…* |

---

## Architettura

### Diagramma dei componenti

*Inserisci qui il diagramma. Deve mostrare i componenti principali e come comunicano.*

### I livelli

| Livello | Cosa fa in ScuolaChill | Esempio concreto |
| --- | --- | --- |
| Presentation / API | *…* | *…* |
| Application / Business | *…* | *…* |
| Data access | *…* | *…* |

### Le dipendenze fra i livelli

*Chi può conoscere chi, e in quale direzione. Spiega come questa struttura riduce l'accoppiamento e rende il sistema testabile.*

---

## Le API

### Le risorse

*Elenca le risorse REST principali. Es. `/classi`, `/verifiche`, `/voti`.*

### Il contratto delle API principali

| Verbo | Route | Chi può chiamarla | Payload di esempio | Risposte previste |
| --- | --- | --- | --- | --- |
| `POST` | `*/api/docenti*` | *Direttore* | `*{ "nome": "…", "email": "…" }*` | *201, 400, 403, 409* |
| `GET` | *…* | *…* | *…* | *…* |
| `PUT` | *…* | *…* | *…* | *…* |
| `PATCH` | *…* | *…* | *…* | *…* |
| `DELETE` | *…* | *…* | *…* | *…* |

### Errori, validazione e paginazione

**Formato uniforme degli errori.** *Mostra un esempio di risposta di errore.*

**Validazione degli input.** *Dove avviene e con quali regole.*

**Paginazione.** *Come funziona. Parametri, dimensione di default, formato della risposta.*

**Documentazione e verifica.** *Come userete OpenAPI/Swagger e la collezione Postman.*

---

## Persistenza e modello dei dati

### Diagramma ER

*Inserisci qui il diagramma entità-relazioni con le cardinalità.*

### Identificatori

*Come vengono generati gli ID, e perché. Numeri incrementali, UUID, altro?*

### Tre modelli diversi

| Entità | Nel database | Nel dominio | Esposta dall'API | Dove differiscono e perché |
| --- | --- | --- | --- | --- |
| *es. Voto* | *…* | *…* | *…* | *…* |

### Normalizzazione e letture aggregate

*Come è normalizzato il modello. Dove serve una lettura denormalizzata, per esempio la pagina dei voti per materia o la dashboard del Direttore.*

### Accesso ai dati

*Strategia di accesso ai dati e uso delle query parametrizzate contro la SQL injection.*

---

## Sicurezza e integrazione

### Autenticazione e token

*Come si ottiene il token, cosa contiene, come viaggia il profilo utente.*

### Chi può fare cosa

| Operazione | Direttore | Docente | Studente |
| --- | --- | --- | --- |
| Creare un docente | ✅ | ❌ | ❌ |
| Caricare materiale | *…* | *…* | *…* |
| Vedere i voti di uno studente | *…* | *…* | *…* |
| *…* |  |  |  |

*Spiega dove viene fatto rispettare questo controllo. Ricorda che il frontend non basta mai.*

### L'API esterna

*Quale servizio usate, per cosa, e cosa succede quando non risponde.*

### Configurazione e segreti

*Dove vivono connection string e segreti, e come cambiano fra Development e Production.*

---

## Qualità architetturale

### Organizzazione del codice

*Struttura di progetti, moduli e cartelle, con le motivazioni.*

### Dependency inversion e IoC

*Dove li applicate e a cosa servono in ScuolaChill.*

### Testabilità

*Cosa testerete, e come separate database e API esterne per sostituirli nei test.*

### Development e Production

|  | Development | Production |
| --- | --- | --- |
| Database | *…* | *…* |
| Segreti | *…* | *…* |
| Log | *…* | *…* |
| *…* |  |  |

---

## Dimensionamento e costi

| Componente | Servizio | Taglia (CPU, RAM, storage) | Istanze | Costo mensile stimato |
| --- | --- | --- | --- | --- |
| Backend | *…* | *…* | *…* | *…* |
| Database | *…* | *…* | *…* | *…* |
| Storage dei file | *…* | *…* | *…* | *…* |
| *…* |  |  |  |  |
| **Totale** |  |  |  | ***…*** |

**Strategia di scalabilità.** *Verticale o orizzontale? Manuale o automatica?*

**Se la stima si rivela sbagliata.** *Cosa fate se gli utenti sono il doppio? E se sono la metà?*

---

## Piano di deployment

*Come ScuolaChill arriva sul cloud scelto. Come si passa da una versione alla successiva. Come vengono gestite nel tempo le modifiche allo schema del database.*

---

# Terza parte · Tempi e valutazione

## Milestone

| Milestone | Cosa è pronto | Data prevista | Responsabile |
| --- | --- | --- | --- |
| PRD validato | Questo documento | *…* | *tutto il team* |
| *Prima versione in cloud* | *…* | *…* | *…* |
| *Collaudo con il primo anno* | *…* | *…* | *…* |
| *…* |  |  |  |

<aside>
💡

Stima il tempo di ogni fase come se tutto andasse bene. Poi aggiungi un margine. Non va mai tutto bene.

</aside>

## Piano di valutazione

Come capirete che ScuolaChill funziona e come validerete che la vostra soluzione sta avendo un impatto positivo?

| Metrica | Obiettivo | Come la misurate | Quando |
| --- | --- | --- | --- |
| *es. Collaudatori che completano una verifica senza aiuto* | *90%* | *Osservazione durante il collaudo* | *Collaudo* |
| *es. Voti persi* | *0* | *Confronto fra voti inseriti e voti salvati* | *Primo mese* |
|  |  |  |  |

---

## Acceptance Criteria di questa PRD

- [ ]  Ogni parte rappresentata da questo template ha tutte le sezioni richieste senza saltare nessun punto
- [ ]  Avete deciso tutti i punti che la traccia e gli esempi lasciano aperti.
- [ ]  Ogni requisito non funzionale ha una soglia e una condizione.
- [ ]  Ogni NFR è collegato ad almeno una user story.
- [ ]  Avete inserito i requisiti impliciti emersi da interviste che avete fatto.
- [ ]  Assunzioni, vincoli e dipendenze sono separati e scritti.
- [ ]  I numeri della stima del carico sono coerenti con la scuola immaginata e con il dimensionamento.
- [ ]  Ogni scelta tecnica ha almeno un'alternativa scartata e una motivazione.
- [ ]  La prima parte non contiene scelte tecniche.
- [ ]  Lo storico delle versioni è aggiornato .