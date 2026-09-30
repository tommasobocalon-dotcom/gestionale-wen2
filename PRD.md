# PRD di Gestionale Impianti Termici · Team snus

## Informazioni sul documento

|              |                                                                           |
| ------------ | ------------------------------------------------------------------------- |
| **Prodotto** | Gestionale impianti termici (caldaie, centrali termiche, climatizzazione) |
| **Team**     | snus                                                                      |
| **Autori**   | Bolea Alessandro, Bocalon Tommaso                                         |
| **Versione** | 1.0                                                                       |
| **Data**     | 23/09/26                                                                  |
| **Stato**    | Bozza                                                                     |

### Storico delle versioni

| Versione | Data     | Autore                            | Cosa è cambiato e perché                                                                                                    |
| -------- | -------- | --------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 1.0      | 23/09/26 | Bolea Alessandro, Bocalon Tommaso | Prima stesura                                                                                                               |
| 1.1      | 25/09/26 | Bolea Alessandro, Bocalon Tommaso | User story spostate nella cartella `userstories/`; tolta la sezione "Requisiti funzionali" con le decisioni lasciate aperte |
| 1.2      | 25/09/26 | Bolea Alessandro, Bocalon Tommaso | Aggiunto il tracciamento degli interventi (data, ora, tecnico che li ha eseguiti) e la user story US-07                     |

---

# Prima parte · Il cosa

## Scopo e perimetro

### Perché esiste il prodotto

**Dal lato business.** Aiuta ad organizzare e catalogare le informazioni aziendali in maniera ordinata, intuitiva e accessibile.

**Dal lato tecnico.** Copre anagrafica, posizione del cliente, tipo di impianto, marca, modello, documentazione di affidabilità, ecc.

### Cosa è incluso

- Anagrafica clienti
- Posizione del cliente
- Tipo di impianto, marca, modello
- Documentazione di affidabilità
- Tracciamento degli interventi su ogni impianto: giorno, ora, tipo di intervento e tecnico che l'ha eseguito

### Cosa non è incluso

- Prezzi
- Preventivi
- Accesso al cliente

---

## Stakeholder

| Stakeholder       | Cosa fa                     | Cosa gli interessa                        | Come lo coinvolgete                                                     |
| ----------------- | --------------------------- | ----------------------------------------- | ----------------------------------------------------------------------- |
| Direttore azienda | Usa il CRM                  | Un CRM funzionante e veloce da consultare | Incontri periodici di validazione dei requisiti e demo dell'avanzamento |
| Docente del corso | Valuta il PRD e il prodotto | Correttezza metodologica e completezza    | Presentazione e sessione di domande                                     |
| Sviluppatori      | Sviluppo del Crm            | Realizzare un progetto full stack         | -                                                                       |

---

## Destinatari e contesto d'uso

### L'azienda per cui progettiamo

W&N Assistenza Caldaie: centro di assistenza tecnica specializzato nella manutenzione, riparazione e controllo dei fumi delle caldaie e degli impianti a gas.

|                            | Valore                                                     |
| -------------------------- | ---------------------------------------------------------- |
| Dipendenti operativi       | 2                                                          |
| Dipendenti amministrazione | 1                                                          |
| Orario di utilizzo         | Principalmente il mattino                                  |
| Connettività               | Rete Wi-Fi aziendale; applicazione su server esterno (VPS) |

### Gli archetipi

| ID      | Archetipo         | Contesto d'uso                       | Competenze digitali | Dispositivo principale | Frequenza d'uso |
| ------- | ----------------- | ------------------------------------ | ------------------- | ---------------------- | --------------- |
| ARC-001 | Direttore         | Ufficio, telefono con cliente        | Normali             | PC desktop             | Giornaliera     |
| ARC-002 | Tecnico operativo | Ufficio, prima e dopo gli interventi | Normali             | PC desktop             | Giornaliera     |
| ARC-003 | Amministrazione   | Ufficio                              | Normali             | PC desktop             | Giornaliera     |

---

## Panoramica e casi d'uso

### Il prodotto in poche righe

Gestionale web per aziende termoidrauliche che permette di cercare, inserire e aggiornare rapidamente i dati di clienti e impianti, di archiviare la documentazione tecnica associata (libretti di impianto, certificati, verbali di manutenzione) e di registrare ogni intervento eseguito su un impianto, con giorno, ora e tecnico che l'ha eseguito.

### User flow e scenari

---

**Storia:** Marco, tecnico operativo, è al telefono con un cliente che chiama per un guasto. Deve trovare in pochi secondi i dati dell'impianto installato.

**User flow**

1. Marco apre il gestionale dal browser del PC in ufficio e accede con le proprie credenziali.
2. Digita il nome o il numero di telefono del cliente nella barra di ricerca.
3. Seleziona il cliente dalla lista dei risultati e visualizza la scheda con i dati dell'impianto e i documenti allegati.

**Scenario principale.** Il cliente è presente nel database. Marco trova l'impianto in meno di 30 secondi, legge marca, modello e matricola e comunica le informazioni al cliente.

**Scenari alternativi.** Se la ricerca non restituisce risultati, il sistema mostra un messaggio "Nessun cliente trovato" con il suggerimento di inserirne uno nuovo. Se esistono più clienti con lo stesso nome, il sistema mostra una lista disambiguata con indirizzo e telefono.

---

**Storia:** Laura, tecnico operativo, torna da un sopralluogo e deve inserire un nuovo cliente con il relativo impianto appena rilevato.

**User flow**

1. Laura accede al gestionale e clicca su "Nuovo cliente".
2. Compila l'anagrafica (nome, cognome, indirizzo, telefono) e salva.
3. Dalla scheda cliente appena creata, clicca su "Aggiungi impianto" e inserisce tipo, marca, modello, matricola e anno di installazione.
4. Salva l'impianto e verifica che la scheda completa sia corretta.

**Scenario principale.** Tutti i campi obbligatori sono compilati. Il sistema salva cliente e impianto e mostra la scheda riepilogativa.

**Scenari alternativi.** Se un cliente con lo stesso numero di telefono esiste già, il sistema mostra un avviso di possibile duplicato prima del salvataggio. Se un campo obbligatorio è vuoto, il sistema evidenzia il campo con un messaggio di errore inline senza perdere i dati già inseriti.

---

**Storia:** Sara, addetta all'amministrazione, deve caricare il libretto di manutenzione di un impianto dopo un intervento completato.

**User flow**

1. Sara cerca il cliente nel gestionale e apre la scheda dell'impianto interessato.
2. Clicca su "Carica documento", seleziona il file PDF dal proprio PC e sceglie la tipologia (libretto di impianto, certificato, verbale).
3. Conferma l'upload e verifica che il documento compaia nella lista allegati dell'impianto.

**Scenario principale.** Il file è un PDF sotto i 10 MB. L'upload va a buon fine e il documento è immediatamente consultabile dalla scheda impianto.

**Scenari alternativi.** Se il file supera i 10 MB, il sistema mostra un errore prima dell'upload. Se il formato non è supportato (solo PDF e immagini JPG/PNG), il sistema lo segnala con un messaggio chiaro.

---

**Storia:** Marco, tecnico operativo, rientra in ufficio dopo la manutenzione annuale di una caldaia e deve registrare l'intervento eseguito.

**User flow**

1. Marco cerca il cliente e apre la scheda dell'impianto su cui ha lavorato.
2. Clicca su "Registra intervento", sceglie il tipo (manutenzione, riparazione, controllo fumi), inserisce giorno e ora dell'intervento e una breve nota.
3. Il campo "Eseguito da" è precompilato con il suo nome; Marco lo lascia così e salva.
4. L'intervento compare in cima allo storico interventi dell'impianto.

**Scenario principale.** Il sistema salva l'intervento con giorno, ora, tipo, tecnico esecutore e nota, e registra in automatico chi lo ha inserito e quando.

**Scenari alternativi.** Se l'intervento è stato eseguito da un collega, Marco sceglie il tecnico corretto dall'elenco degli utenti. Se giorno e ora sono nel futuro, il sistema mostra un errore inline e non salva.

---

## Requisiti funzionali

### User stories

### US-01 · Ricerca cliente

**Storia.** Come tecnico, voglio cercare un cliente per nome o numero di telefono, così da trovare i suoi dati rapidamente durante una chiamata.

**Archetipo:** ARC-002 Tecnico operativo (usata anche da Direttore e Amministrazione).
**Priorità:** alta – milestone MVP (15/11/2026).

#### Contesto e motivazione

Il caso d'uso più frequente: un cliente chiama per un guasto e il tecnico, ancora al telefono, deve risalire all'impianto installato. Oggi le informazioni sono su carta o sparse, e la ricerca richiede minuti. Il direttore in intervista: _"Quando un cliente chiama devo trovare subito i suoi dati, anche se sono al telefono"_.

Il valore della storia sta nella velocità: se la ricerca è lenta o richiede di ricordare il nome esatto, il gestionale non viene usato durante la chiamata e i dati tornano su carta.

#### Criteri di accettazione

1. **Dato** un cliente registrato, **quando** il tecnico digita tutto o parte del nome, cognome o ragione sociale, **allora** il cliente compare tra i risultati.
2. **Dato** un cliente registrato, **quando** il tecnico digita tutto o parte del numero di telefono, **allora** il cliente compare tra i risultati.
3. La ricerca è case-insensitive (`rossi` trova `Rossi`).
4. Ogni risultato mostra nome, indirizzo e telefono, sufficienti a distinguere omonimi.
5. I risultati sono visibili in meno di 1 s con un database fino a 5 000 clienti (NFR-01).
6. **Quando** la ricerca non restituisce risultati, **allora** il sistema mostra "Nessun cliente trovato" con un collegamento a "Nuovo cliente" (US-03).
7. Selezionando un risultato si apre la scheda cliente (US-02).

#### Fuori perimetro

- Ricerca per indirizzo, matricola o marca dell'impianto.
- Ricerca fuzzy o tollerante agli errori di battitura.

#### Collegamenti

- NFR-01 (prestazioni), NFR-03 (apprendibilità), NFR-05 (compatibilità browser).
- Scenario "Marco, tecnico operativo, è al telefono con un cliente" nella PRD.

### US-02 · Scheda cliente

**Storia.** Come tecnico, voglio visualizzare la scheda di un cliente con l'elenco dei suoi impianti e i documenti allegati, così da avere tutte le informazioni in un'unica vista.

**Archetipo:** ARC-002 Tecnico operativo (usata anche da Direttore e Amministrazione).
**Priorità:** alta – milestone MVP (15/11/2026).

#### Contesto e motivazione

Trovato il cliente (US-01), al tecnico servono marca, modello e matricola dell'impianto e i documenti disponibili (libretto, certificati, verbali). Se queste informazioni sono su pagine diverse, durante una telefonata si perde tempo a navigare. La scheda unica è il punto di arrivo di quasi tutti i flussi del gestionale.

Il tecnico in intervista: _"Dobbiamo sapere quali documenti abbiamo per ogni caldaia, adesso sono su carta o persi"_.

#### Criteri di accettazione

1. La scheda mostra i dati anagrafici del cliente: nome o ragione sociale, indirizzo, telefono.
2. La scheda mostra la lista degli impianti del cliente con tipo, marca, modello, matricola e anno di installazione.
3. Per ogni impianto la scheda mostra la lista dei documenti allegati con tipologia, nome file e data di caricamento.
4. Ogni documento è scaricabile con un clic.
5. Per ogni impianto la scheda mostra lo storico degli interventi (US-07), dal più recente, con giorno, ora, tipo e tecnico esecutore.
6. **Dato** un cliente senza impianti o un impianto senza documenti o interventi, **allora** la scheda mostra un messaggio esplicito ("Nessun impianto", "Nessun documento", "Nessun intervento") invece di una lista vuota.
7. La scheda si carica in meno di 1 s (NFR-01), con una sola lettura aggregata cliente + impianti + documenti + interventi (nessun problema N+1).
8. Dalla scheda sono raggiungibili le azioni "Aggiungi impianto" (US-03), "Carica documento" (US-04), "Registra intervento" (US-07) e "Modifica" (US-05).

#### Fuori perimetro

- Anteprima inline dei PDF.

#### Collegamenti

- NFR-01 (prestazioni), NFR-05 (compatibilità browser).

### US-03 · Inserimento cliente e impianto

**Storia.** Come tecnico, voglio inserire un nuovo cliente con almeno un impianto associato, così da registrare i dati rilevati durante il sopralluogo.

**Archetipo:** ARC-002 Tecnico operativo (permessa anche a Direttore e Amministrazione).
**Priorità:** alta – milestone MVP (15/11/2026).

#### Contesto e motivazione

Dopo un sopralluogo il tecnico torna in ufficio con i dati del nuovo cliente e dell'impianto rilevato. Se l'inserimento è lento o fa perdere i dati in caso di errore, il tecnico rimanda e l'informazione si perde. Senza questa storia il database resta vuoto e US-01 e US-02 non hanno valore.

Il controllo sui duplicati è importante: due schede per lo stesso cliente dividono impianti e documenti e rendono la ricerca inaffidabile.

#### Criteri di accettazione

1. Campi obbligatori del cliente: nome o ragione sociale, telefono. Campi facoltativi: cognome, indirizzo.
2. Campi dell'impianto: tipo, marca, modello, matricola, anno di installazione.
3. **Quando** un campo obbligatorio è vuoto o non valido, **allora** il sistema evidenzia il campo con un messaggio inline e **non** perde i dati già inseriti.
4. **Dato** un cliente esistente con lo stesso numero di telefono, **quando** il tecnico salva, **allora** il sistema mostra un avviso di possibile duplicato con un collegamento alla scheda esistente e chiede conferma prima di salvare.
5. Dopo il salvataggio del cliente, il sistema apre la scheda appena creata con l'azione "Aggiungi impianto" in evidenza.
6. Dopo il salvataggio dell'impianto, la scheda riepilogativa mostra cliente e impianto (US-02).
7. Tutto il form è compilabile solo da tastiera (NFR-07).
8. Il form mostra il riferimento all'informativa sul trattamento dei dati personali (NFR-08).

#### Fuori perimetro

- Importazione massiva di clienti da file (Excel, CSV).
- Inserimento da dispositivo mobile durante il sopralluogo.

#### Collegamenti

- NFR-02 (sicurezza), NFR-03 (apprendibilità), NFR-06 (backup), NFR-07 (tastiera), NFR-08 (GDPR).
- Scenario "Laura, tecnico operativo, torna da un sopralluogo" nella PRD.

### US-04 · Caricamento documento

**Storia.** Come tecnico o amministrazione, voglio caricare un documento (PDF o immagine) su un impianto, così da archiviare libretti e certificati.

**Archetipo:** ARC-003 Amministrazione, ARC-002 Tecnico operativo.
**Priorità:** media – milestone "Upload documenti" (30/11/2026).

#### Contesto e motivazione

Libretti di impianto, certificati e verbali di manutenzione oggi sono su carta o dispersi. Sono documenti con obblighi di legge: se non si trovano, l'azienda deve ricostruirli o non può dimostrare la manutenzione fatta. Collegare il documento all'impianto, e non solo al cliente, permette di distinguere i documenti quando un cliente ha più impianti.

#### Criteri di accettazione

1. Dalla scheda impianto, l'utente sceglie "Carica documento", seleziona un file e sceglie la tipologia: libretto di impianto, certificato, verbale.
2. Formati accettati: PDF, JPG, PNG.
3. Dimensione massima: 10 MB.
4. **Quando** il file supera 10 MB, **allora** il sistema mostra un errore **prima** dell'upload.
5. **Quando** il formato non è supportato, **allora** il sistema mostra un messaggio chiaro con i formati ammessi.
6. **Quando** l'upload va a buon fine, **allora** il documento compare subito nella lista allegati dell'impianto (US-02), senza ricaricare la pagina.
7. Il controllo su formato e dimensione avviene anche lato server, non solo nel browser.
8. I documenti caricati sono inclusi nel backup giornaliero (NFR-06).

#### Fuori perimetro

- Anteprima inline dei PDF.
- Upload multiplo di più file in una sola operazione.
- Numero massimo di documenti per impianto.

#### Collegamenti

- NFR-04 (disponibilità), NFR-06 (backup).
- Scenario "Sara, addetta all'amministrazione, deve caricare il libretto di manutenzione" nella PRD.

### US-05 · Modifica cliente o impianto

**Storia.** Come amministrazione, voglio modificare i dati di un cliente o di un impianto esistente, così da mantenere le informazioni aggiornate.

**Archetipo:** ARC-003 Amministrazione (permessa anche a Direttore e Tecnico operativo).
**Priorità:** alta – milestone MVP (15/11/2026).

#### Contesto e motivazione

I dati cambiano: il cliente cambia numero di telefono o indirizzo, l'impianto viene sostituito. Un dato vecchio è peggio di un dato mancante, perché il tecnico si fida e chiama il numero sbagliato o si presenta con il ricambio sbagliato. Registrare chi ha fatto la modifica e quando permette di risalire all'origine di un errore.

#### Criteri di accettazione

1. Dalla scheda cliente l'utente può modificare anagrafica e dati di ogni impianto.
2. Le regole di validazione sono le stesse dell'inserimento (US-03), compreso l'avviso di duplicato sul telefono.
3. Ogni modifica registra data, ora e utente che l'ha effettuata.
4. La scheda mostra la data e l'autore dell'ultima modifica.
5. **Quando** l'utente annulla la modifica, **allora** i dati restano invariati.
6. Tutto il form è compilabile solo da tastiera (NFR-07).
7. L'eliminazione di un cliente o impianto è permessa solo a Direttore e Amministrazione, non al Tecnico operativo.
8. Su richiesta del cliente, i suoi dati personali possono essere esportati o cancellati (NFR-08).

#### Fuori perimetro

- Storico completo delle versioni precedenti di un record (si registra solo chi e quando).
- Cancellazione fisica: si usa il soft delete (`deleted_at`), come da PRD.

#### Collegamenti

- NFR-02 (sicurezza), NFR-07 (tastiera), NFR-08 (GDPR).
- Tabella "Chi può fare cosa" nella PRD.

### US-06 · Accesso con credenziali personali

**Storia.** Come direttore, voglio accedere al gestionale con credenziali personali, così da garantire che solo il personale autorizzato possa operare.

**Archetipo:** ARC-001 Direttore (vale per tutti gli utenti).
**Priorità:** alta – prerequisito di tutte le altre storie.

#### Contesto e motivazione

Il gestionale contiene dati personali dei clienti ed è raggiungibile da internet (VPS). Senza autenticazione chiunque conosca l'indirizzo può leggere o modificare i dati. Credenziali personali, e non un account condiviso, servono anche a US-05: la modifica registra _chi_ l'ha fatta, e questo ha senso solo se ogni utente ha il proprio account.

#### Criteri di accettazione

1. Login con email e password.
2. **Quando** le credenziali sono errate, **allora** il sistema mostra un messaggio generico, senza indicare se è errata l'email o la password.
3. Nessuna pagina è accessibile senza sessione valida: un accesso diretto a un URL protetto porta alla pagina di login (NFR-02).
4. La sessione scade dopo 8 ore di inattività.
5. L'utente può fare logout in modo esplicito.
6. L'utente può reimpostare la password tramite email (SMTP della casella email del dominio).
7. In produzione il sito è servito solo in HTTPS.
8. Solo il Direttore può aggiungere o rimuovere utenti.

#### Fuori perimetro

- Autenticazione a due fattori.
- Login con account esterni (Google, Microsoft).
- Token JWT: si usa la sessione server-side, come da PRD.

#### Collegamenti

- NFR-02 (sicurezza).
- Sezione "Sicurezza e integrazione" della PRD.

### US-07 · Registrazione intervento

**Storia.** Come tecnico, voglio registrare ogni intervento eseguito su un impianto con giorno, ora e tecnico che l'ha eseguito, così da sapere sempre chi ha lavorato su un impianto e quando.

**Archetipo:** ARC-002 Tecnico operativo (permessa anche a Direttore e Amministrazione).
**Priorità:** alta – milestone MVP (15/11/2026).

#### Contesto e motivazione

W&N esegue manutenzioni, riparazioni e controlli fumi. Oggi non c'è traccia strutturata di chi è intervenuto e quando: se un cliente richiama per un guasto, il tecnico non sa se l'impianto è stato visto di recente né da quale collega. Lo storico degli interventi permette di:

- rispondere al cliente sapendo quando è stata fatta l'ultima manutenzione;
- risalire al tecnico che ha eseguito un lavoro, in caso di contestazione o di dubbio tecnico;
- avere evidenza delle manutenzioni periodiche previste dalla normativa.

Chi ha **eseguito** l'intervento e chi lo ha **registrato** sono due informazioni distinte: spesso l'amministrazione inserisce l'intervento a nome del tecnico.

#### Criteri di accettazione

1. Dalla scheda impianto l'utente sceglie "Registra intervento".
2. Campi: tipo (manutenzione, riparazione, controllo fumi), giorno e ora dell'intervento, tecnico esecutore, note facoltative.
3. Il campo tecnico esecutore è precompilato con l'utente autenticato e si può cambiare scegliendo da un elenco degli utenti.
4. **Quando** giorno e ora sono nel futuro, **allora** il sistema mostra un errore inline e non salva.
5. **Quando** un campo obbligatorio è vuoto, **allora** il sistema evidenzia il campo senza perdere i dati inseriti.
6. Il sistema registra in automatico chi ha inserito l'intervento e quando (`created_by`, `created_at`).
7. Lo storico interventi è visibile nella scheda impianto (US-02), ordinato dal più recente, con giorno, ora, tipo, tecnico esecutore e note.
8. Tutto il form è compilabile solo da tastiera (NFR-07).

#### Fuori perimetro

- Pianificazione di interventi futuri e calendario appuntamenti.
- Collegamento automatico tra intervento e documento caricato (es. verbale).
- Ore lavorate, materiali usati, costi.

#### Collegamenti

- NFR-02 (sicurezza), NFR-05 (compatibilità browser), NFR-06 (backup), NFR-07 (tastiera).
- Scenario "Marco rientra in ufficio dopo la manutenzione annuale" nella PRD.
- US-02 (scheda cliente), US-05 (modifica dati).

## Requisiti non funzionali

### Requisiti impliciti
