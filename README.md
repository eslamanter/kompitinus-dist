# Kompitìnus

## 📌 Cos'è?
È una applicazione per organizzare e gestire i compiti lavorativi in modo semplice ed efficace.  
Grazie a un **database locale condiviso**, puoi inviare e ricevere compiti personali e monitorare i compiti degli altri in **trasparenza**.  

## ✨ Funzionalità
✅ **Gestione dei compiti**: Invia, ricevi, visualizza e aggiorna i compiti personali che hai assegnato o che ti sono stati assegnati.
✅ **Priorità e scadenze**: Controlla le date di scadenza e gestisci le priorità con facilità.
✅ **Consultazione rapida**: Gli utenti possono vedere il titolo e la scadenza dei compiti assegnati agli altri, se resi consultabili.  
✅ **Esportazione dei report**: Crea riepiloghi di tutti i compiti contrassegnati ed esportali facilmente in qualsiasi momento.

## ℹ️ Come si usa?
Al primo avvio dell'applicazione ti verrà chiesto di:
- Definire il percorso del database di riferimento selezionando:
  - Il file del database, se ne esiste già uno,
  - Oppure, in caso contrario, la cartella in cui creare il nuovo database.
- Inserire le credenziali di accesso, se sei già registrato, oppure i dati per registrarti come nuovo utente.

Dopo la configurazione del percorso e l'accesso, viene creato un file di configurazione **config.json**, utile per mantenere l'accesso senza la necessità di reinserire le credenziali nei successivi avvii.

## 🖥 Struttura dell'interfaccia
L'interfaccia principale è suddivisa in tre sezioni verticali:

### 1️⃣ Gestione corrispondenza
- Seleziona per visualizzare il riepilogo della corrispondenza dei tuoi compiti personali o dei compiti assegnati agli utenti registrati.
- Le corrispondenze personali sono suddivise in:
  - **Inbox** → Compiti ricevuti
  - **Outbox** → Compiti inviati
  - Entrambe le sezioni possono essere filtrate in:
    - **Contrassegnati** → Compiti contrassegnati
    - **Scaduti** → Compiti che risultano scaduti
- Visualizzazione delle corrispondenze relative ai compiti contrassegnati ricevuti dagli altri utenti.
- **Doppio clic** sul nome dell'utente destinatario per inviare un nuovo compito, compilando successivamente i dettagli nel pannello apposito.

### 2️⃣ Riepilogo compiti
- Visualizza l'elenco dei compiti associati alla corrispondenza selezionata.
- Dalla tabella puoi scegliere un compito da visualizzare o modificare nel **Pannello dettagli**.
- I dati dei compiti includono le seguenti colonne:
  - **ID del compito**
  - **Data e ora dell'ultima modifica**
  - **Nome e cognome dell'utente responsabile**
  - **Nome e cognome dell'utente incaricato**
  - **Titolo del compito**
  - **Data e ora di scadenza**
  - **Note sullo stato del compito**

#### 📌 Ordinamento dei compiti:
- Generalmente, i compiti sono ordinati in base alla data dell'ultima modifica (dal più recente al più lontano).
- I compiti **scaduti** vengono invece ordinati per data di scadenza (dal più lontano al più recente).

#### 🎨 Colorazione dello stato del compito:
- **Grigio** → Archiviato
- **Blu** → Completato
- **Rosso** → Scaduto & Contrassegnato
- **Arancione** → Scaduto
- **Verde** → In progress

- Lo stato del compito è indicato anche nella colonna **Note**.
- Se un compito è in più stati contemporaneamente (es. completato e archiviato), viene associato al colore di priorità superiore.

### 3️⃣ Pannello dettagli
Contiene le informazioni del compito selezionato oppure da compilare per l'invio:
- **Titolo** (max 160 caratteri)
- **Descrizione**
- **Riferimento locale** (es. percorso cartella) o **riferimento esterno** (es. link web)
- **Data e ora di scadenza**
- **Data e ora prevista dall'utente incaricato per lo svolgimento del compito**
- **Risposta dell'utente incaricato**

#### 🛠 Opzioni disponibili nel tasto `(...)` accanto al riferimento:
- **Seleziona cartella** → Apri dialogo di selezione
- **Copia link** → Copia il riferimento
- **Incolla link** → Incolla un testo dagli appunti
- **Cancella link** → Rimuovi il riferimento

#### ✅ Caselle di selezione disponibili:
- **Contrassegnato** → Permette agli altri di consultare titolo e scadenza
- **Archiviato** → Nasconde il compito agli altri, incluso l'utente incaricato
- **Fatto** → Segna il completamento del compito

- I dettagli modificabili per un compito inviato sono gli stessi di quelli già ricevuti, **con l'aggiunta** della possibilità di impostare la data e l'ora prevista per il completamento come suggerimento.
- Per i compiti inviati, **di default viene impostata la data e l'ora del mezzogiorno lavorativo successivo**.

#### 🔄 Aggiornamento dettagli:
- Tutti i dettagli possono essere aggiornati in qualsiasi momento, in base alle competenze dell'utente.
- La **data e l'ora di scadenza** o di completamento prevista verranno evidenziate in **rosso** se:
  - Il giorno cade di **sabato, domenica o festivo nazionale**
  - L'orario è **fuori dagli orari lavorativi aziendali** (9:00 - 18:59)

## 🏷 Barra dei comandi (in alto)
- **Utente > Dati Utente** → Visualizza e modifica i dati utente (nome, cognome, email, PIN)
  - L'indirizzo email modificato **non deve coincidere con un altro già registrato**
- **Esporta > Contrassegnati** → Genera report Excel (`report.xlsx`) contenente:
  - **ID del compito**
  - **Ultima modifica**
  - **Nome e cognome del responsabile**
  - **Nome e cognome dell'incaricato**
  - **Titolo del compito**
  - **Data e ora di scadenza**
  - **Ritardo in giorni**
- **Info > App, Guida** → Informazioni sull'applicazione e guida utente

## 📌 Barra di stato (in basso)
- Mostra le azioni su testo: selezionato, copiato, incollato o cancellato
- Indica il successo della creazione o modifica di un compito, mostrando l'ID relativo

## ⚠️ Avviso
🔹 Questo software gestisce un **database aperto**, il che significa che potrebbe essere soggetto a **modifiche esterne o danneggiamenti**.  
🔹 Alcuni compiti non contrassegnati potrebbero **non essere visibili** agli altri utenti.  
🔹 Si consiglia **di non condividere informazioni sensibili o riservate**.  
🔹 Il software è fornito **senza alcuna garanzia** di prestazioni o risultati.  

## 💡 Aiuto?
Per domande o supporto, contatta eslam.anter@outlook.com  
