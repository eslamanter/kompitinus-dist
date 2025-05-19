# Kompitìnus

## 📌 Cos'è?
Questa applicazione crea e gestisce un **database locale condiviso**, offrendo un'interfaccia per **organizzare**, **analizzare** e **condividere** i **compiti lavorativi** con **trasparenza**, nel rispetto delle regole aziendali. Permette di impostare **priorità** con **scadenze flessibili**, indicando i giorni mancanti o scaduti. Gli utenti autenticati possono consultare **il titolo** e **la scadenza** dei compiti assegnati agli altri, con la possibilità di **esportare report** riepilogativi dei compiti contrassegnati.  

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
L'interfaccia principale è suddivisa in **tre** sezioni verticali:

### 1️⃣ Gestione corrispondenza
- Seleziona per visualizzare il riepilogo della corrispondenza dei tuoi compiti personali o dei compiti assegnati agli utenti registrati.
- Le corrispondenze personali sono suddivise in:
  - **Inbox** → Compiti ricevuti, **ad eccezione** di quelli archiviati
  - **Outbox** → Compiti inviati
  - Entrambe le sezioni possono essere filtrate in:
    - **Contrassegnati** → Compiti contrassegnati
    - **Scaduti** → Compiti che risultano scaduti, **ad eccezione** di quelli archiviati o fatti
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
- **Blu** → Fatto
- **Rosso** → Scaduto & Contrassegnato
- **Arancione** → Scaduto
- **Verde** → In progress

- Lo stato del compito è indicato anche nella colonna **Note**.
- Se un compito è in più stati contemporaneamente (es. fatto e archiviato), viene associato al colore di priorità superiore.

### 3️⃣ Pannello dettagli
Contiene le informazioni del compito selezionato oppure da compilare per l'invio:
- **Titolo** (max 160 caratteri)
- **Descrizione**
- **Riferimento** locale (es. percorso cartella) o esterno (es. link web)
- **Data di scadenza** impostata dal responsabile
- **Data prevista** dall'utente incaricato per il completamento del compito
- **Risposta** dell'utente incaricato

#### 🛠 Opzioni disponibili nel tasto `(...)` accanto al riferimento:
- **Seleziona cartella** → Apri dialogo di selezione
- **Copia link** → Copia il riferimento
- **Incolla link** → Incolla un testo dagli appunti
- **Cancella link** → Rimuovi il riferimento

#### ✅ Caselle di selezione disponibili:
- **Contrassegnato** → Permette agli altri di consultare titolo e scadenza
- **Archiviato** → Nasconde il compito agli altri, incluso l'utente incaricato
- **Fatto** → Segna il completamento del compito

### 🔧 Modifica dettagli del compito  

I dettagli modificabili nel **pannello dei dettagli del compito** riguardano:  

- **Per i compiti ricevuti** → Impostazione della data e dell'ora **prevista** per il completamento, con la possibilità di **spuntare il completamento** del compito e, eventualmente, lasciare una **risposta** al responsabile.  

- **Per i compiti inviati** → Inserimento del **titolo** (obbligatorio), della **descrizione**, della data e dell'ora di **scadenza** per il completamento del compito, con la possibilità di **contrassegnare** o **archiviare** il compito, ove necessario.  

- I dettagli modificabili per i compiti da inviare nuovi sono gli stessi di quelli già inviati, **ad eccezione** della possibilità di impostare la data e l'ora prevista per il completamento come suggerimento per l'utente destinatario.
- Per i compiti da inviare, **di default viene impostata la data e l'ora del mezzogiorno lavorativo successivo**.

#### 🔄 Aggiornamento dettagli:
- Tutti i dettagli possono essere aggiornati in qualsiasi momento, in base alle competenze dell'utente.
- La **data e l'ora di scadenza** verranno evidenziate in **rosso** se:
  - Il giorno cade di **sabato, domenica o festivo nazionale**
  - L'orario è **fuori dagli orari lavorativi aziendali** (9:00 - 18:59)

## 🏷 Barra dei comandi (in alto)
- **Utente > Dati Utente** → Visualizza e modifica i dati utente (nome, cognome, email, PIN)
  - L'indirizzo email modificato **non deve coincidere con un altro già registrato**.
  
- **Esporta > Contrassegnati** → Genera report Excel (`report.xlsx`) contenente:
  - **ID del compito**
  - **Ultima modifica**
  - **Nome e cognome del responsabile**
  - **Nome e cognome dell'incaricato**
  - **Titolo del compito**
  - **Data e ora di scadenza**
  - **Ritardo in giorni**

- **Info > App, Guida** → Informazioni sull'applicazione e guida utente.

### 📊 Esportazione Excel
- Il **foglio Excel** viene esportato nella stessa cartella dell'applicazione con il nome `report.xlsx`.  
- Al foglio esportato viene aggiunta **una pagina** nominata con la **data e l'ora** ogni volta che viene eseguito il comando.  
- Se il **file Excel è aperto**, **non** è possibile aggiungere una nuova pagina, quindi l'esportazione **non** verrà eseguita finché il file non verrà chiuso.  

## 📌 Barra di stato (in basso)
- Mostra le azioni su testo: selezionato, copiato, incollato o cancellato
- Indica il successo della creazione o modifica di un compito, mostrando l'ID relativo

## ⚠️ Avviso  
🔹 Questo software gestisce un **database aperto**, esponendolo al rischio di **modifiche esterne** o **danneggiamenti**.  
🔹 Si consiglia di **non condividere** informazioni sensibili o riservate.  
🔹 Il software è fornito **senza alcuna garanzia** di prestazioni, affidabilità o risultati.  

## 💡 Aiuto?  
Per suggerimenti, domande o supporto, contatta **eslam.anter@outlook.com**  
Visita il repository dell'applicazione su GitHub **https://github.com/eslamanter/kompitinus-ita/** per gli aggiornamenti.  

