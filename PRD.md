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
