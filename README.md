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
  - Il file del database, se esiste già uno,
  - oppure, in caso contrario, la cartella del nuovo database da creare nuovo.
- Le credenziali di accesso se sei già registrato oppure i dati per registrarti come nuovo utente.

A conclusione della definizione del percorso e l'accesso viene creato un file di configurazione nominato config.json utile per ricordare l'accesso senza la necessità ri ripetere l'accesso nelle successive volte.

L'interfaccia principale è divisa verticalmente in tre sezioni così divise:
- Gestione corrispondenza:
  - Seleziona per visualizzare il riepilogo della corrispondenza dei compiti personali oppure i compiti assegnati agli utenti registrati.
    - Le corrispondenze personali sono divise in:
       - Inbox, per tutti i compiti ricevuti, 
       - Outbox, per tutti i compiti inviati.
         entrambi ulteriormente possono essere filtrati in:
           - Contrassegnati, per i compiti contrassegnati, 
           - Scaduti, per i compiti, in quel momento risultano, scaduti.
    - Le corrispondenze degli altri utenti relativamente ai compiti contrassegnati ricevuti.
  - Doppia clicca sul nome dell'utente al quale vuoi inviare un nuovo compito inserendo successivamente i dati del compito nel pannello dei dettagli del compito.
    
- Riepilogo compiti:
  - Visualizza l'elenco dei compiti realtivi alla corrispondenza scelta.
  - Dalla tabella puoi selezionare il compito da visualizzare o modificare nel pannello dei dettagli del compito.
  - I dati dei compiti rappresentati sono relative alle seguenti colonne:
    ID del compito,
    la data e l'ora dell'ultima modifica,
    il nome e il cognome dell'utente responsabile,
    il nome e il cognome dell'utente incaricato,
    il titolo del compito,
    la data e l'ora della scadenza,
    le note sullo stato del compito.
  
  - I compiti visualizzati sono, in generale, ordinati in base al tempo dell'ultima modifica, dal più recente al più lontano.
  - I compiti scaduti sono, invece, ordinati in base al tempo di scadenza dal più lontano al più recente.
 
  - I compiti rappresentati vengono rappresentati con sfondo colorato in base allo stato del compito come segue:
    - Grigio: Archiviato,
    - Blu: Fatto,
    - Rosso: Scaduto & Contrassegnato,
    - Arancione: Scaduto,
    - Verde: In progress.
      
      - Lo stato del compito viene rappresentato nella colonna note.
      - Da specificare che per un compito, quando risulta contemporaneamente in due stati (es. fatto e archiviato) viene associato al colore di ordine superiore tra quelli precedentemente elencati.
      
- Pannello dettagli:
  - Contiene i dettagli del compito selezionato oppure da compilare per l'invio relativamente a:
    - Titolo del compito (max 160 caratteri), descrizione, riferimento locale (es. percorso cartella) o esterno (es. link web), data e ora di scadenza, data e ora prevista dal utente incaricato per svolgere il compito e la sua risposta.
      - Nel tasto (...) a destra del riferimento è possibile:
          - Selezionare cartella: per aprire il dialogo per selezionare una cartella,
          - Copiare link: per copiare il link già aggiunto come riferimento,
          - Incollare link: per incollare un testo da appunti,
          - Cancellare link: per cancellare un testo già aggiunto come riferimento.
    
    - Inoltre, sono disponibili tre caselle con la possibilità di spuntare, relativi a:
      - Contrasseganto: per permettere agli altri di consultare il titolo e la scadenza
      - Archiviato: per nascondere agli altri, incluso l'utente incaricato del compito
      - Fatto: per segnare il completamento del compito
  - Inserisci, visualizza e modifica i dettagli del compito selezionato relativamente alla parte di competenza dell'utente.
    - I dettagli modificabili nel pannello dei detagli del compito sono relativi:
      - all'impostare la data e l'ora prevista per il completamento con la possibilità di spuntare il completamento del compito e, eventualmente, lasciare una risposta al responsabile.
      - all'inserimento, obbligatoriamente, del titolo, la descrizione, la data e l'ora di scadenza per il completamento del compito con la possibilità di contrassegnare o archiviare il compito ove vi è necassario.
        - I dettagli modificabili per i compiti da inviare nuovi sono gli stessi di quelli già inviati, tranne, l'aggiunta della possibilità di impostare la data e l'ora prevista per il completamento come suggerimento per l'utente che deve ricevere il compito.
          Inoltre, per i compiti da inviare vengono di default selezionate la data e l'ora del mezzogiorno lavorativo successivo.
    - Tutti i dettagli del compito possono essere aggiornati in qualsiasi momento, ogni parte dal suo competente.
    - La data e l'ora impostata per la scadenza o prevista per il completamento verranno evidenziati in rosso se:
      - La data risulta nei giorni di sabato, domenica o festivi nazionali.
      - L'ora risulta fuori dagli orari lavorativi aziendali (dalle ore 09:00 alle ore 18:59).

Nel lato superiore della finestra principale, nella barra dei comandi, sono disponibili i comandi:

- Utente > Dati Utente: per visualizzare i dati dell'utente relativi a: nome, cognome, email e PIN con la possibilità di modificarli o eventualmente di uscire, eliminando la configurazione dell'utente presente nella cartella dell'applicazione.
  - L'indirizzo email modificato non deve coincidere con un altro indirizzo già registrato.
- Esporta > Contrassegnati: per esportare un report riepilogativo in fogli Excel di tutti i compiti contrassegnati includendo:
    ID del compito,
    la data e l'ora dell'ultima modifica,
    il nome e il cognome dell'utente responsabile,
    il nome e il cognome dell'utente incaricato,
    il titolo del compito,
    la data e l'ora della scadenza,
    il ritardo in giorni
      - Il foglio Excel viene esportato nella stessa cartella dell'applicazione con il nome report.xlsx
      - Al foglio esportato viene aggiunta una pagina nominata con la data e l'ora ogni volta viene eseguito il comando.
      - Una nuova pagina di Excel non può essere aggiunta al foglio se risulta aperto per cui non viene eseguito il comando di esportazione finchè non si chiude il file.
  
- Info > App, Guida: per le informazioni sull'applicazione e la guida.

Nel lato inferiore della finestra principale, nella barra dello stato, viene rappresentato:
- il testo selezionato, copiato, incollato o cancellato del riferimento.
- il successo della creazione o della modifica effettuata al compito indicando l'ID relativo.

## ⚠️ Avviso
🔹 Questo software gestisce un **database aperto**, il che significa che potrebbe essere soggetto a **modifiche esterne o danneggiamenti**.  
🔹 Alcuni compiti non contrassegnati potrebbero **non essere visibili** agli altri utenti.  
🔹 Si consiglia **di non condividere informazioni sensibili o riservate**.  
🔹 Il software è fornito **senza alcuna garanzia** di prestazioni o risultati.  

## 💡 Aiuto?
Per domande o supporto, contatta eslam.anter@outlook.com  
