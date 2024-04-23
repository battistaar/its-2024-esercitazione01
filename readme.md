# Simulazione esercitazione 2023

## API server
A partire dalla struttura di questa repo andare a sviluppare le api necessarie a soddisfare le specifiche del file `sim-todo.yaml` (aprire il file con [swagger editor](https://editor.swagger.io/)).

### Descrizione
- L'app gestisce liste di todo associate agli utenti
- Ogni todo è automaticamente collegato alla persona che l'ha creato
- Ogni todo può essere assegnato ad un'altra persona al momento della creazione o in seguito tramite una apposita API
- Ogni todo può avere una data di scadenza
- Se passata la data di scadenza un todo non è ancora stato completato la proprietà `expired` viene tornata a true
- Ogni utente vede solo i todo creati o assegnati a lui
- Di default la lista dei todo non torna quelli già completati, c'è un queryparam per includerli
- I todo vengono segnati come completati o non completati tramite apposite api
- Al momento della creazione un todo è non completato
- L'app fornisce una api per tornare la lista degli utenti registrati, utile per assegnare i todo

### Indicazioni
- Tutte le api ad eccezione di quelle di autenticazione sono protette tramite token JWT
- Non salvare più dati del necessario nelle collezioni, utilizzare `virtual` e `ref` quando possibile
- Fare attenzione ai queryparam, di default vengono mandati come stringa
- La repo ha già una serie di dipendenze dichiarate (penso tutte quelle che vi serviranno)
- Leggere bene le definizioni delle api tramite swagger, contengono campi required, condizioni di errore e descrizioni sul comportamento.
- Non abbiate paura di fare copia incolla dal codice scritto a lezione, possibilmente prima accertatevi di averlo capito. Diverso è fare copia incolla da un compagno, non è apprezzato.


## APP Angular
Questa va generata usando angular cli, niente codice di partenza. Tutti i passaggi iniziali sono coperti dalla documentazione del corso, in particolare come impostare il proxy per fare le richieste al server.

L'app si comporra di sole due pagine
- login
- lista dei todo

### Descrizione
- Installare e utilizzare ngboostrap e i suoi componenti (documentazione del corso)
- Aggiungere la navbar alla pagina con l'utente loggato e il logout (come fatto in classe)
- Alla lista dei todo si accede solo previa autenticazione
- Sopra la lista dei todo c'è una checkbox che se spuntata chiama l'API in modo da tornare anche i todo completati
- Sopra la lista dei todo è presente un pulsante di aggiunta che apre un [modal](https://ng-bootstrap.github.io/#/components/modal/examples), il modal presenta il form di creazione del todo e la lista degli utenti a cui è possibile assegnarlo (l'assegnazione è opzionale).
- Per gestire la selezione della dueDate usare [datepicker](https://ng-bootstrap.github.io/#/components/datepicker/overview)
- Ogni elemento della lista dei todo deve presentare
  - titolo dell'attività da svolgere
  - nome e profile picture dell'utente che ha creato il todo
  - nome e profile picture dell'utente a cui è assegnato (se presente)
  - duedate formattata correttamente (se presente)
- Se un todo non è assegnato a una persona al posto del nome dell'assegnatario è presente un pulsante che apre una modale con la lista del utenti e permette di assegnarlo
- Ogni todo cambia visualizzazione per evidenziare il fatto che è expired
- Ogni todo cambia visualizzazione per evidenzare il fatto che è completato
- Per ogni todo è presente una checkbox che, quando premuta, segna lo stato come completato o da completare (commuta a ogni click)

### Indicazioni
- Non vi preoccupate troppo dello stile, ma datemi almeno l'impressione di averci provato
- Guardate bene la documentazione di [ng-bootstrap](https://ng-bootstrap.github.io/) e cercate componenti che vi possano essere utili
- Guardate in particolare gli esempi e cercate di capire dalle api della libreria se ci sono delle configurazioni da applicare per ottenere i risultati che desiderate
- Suddividete quanto più possibile in componenti, se un comportamento si ripete fare in modo di avere qualcosa di riutilizzabile
- Non abbiate paura di fare copia incolla dal codice scritto a lezione, possibilmente prima accertatevi di averlo capito. Diverso è fare copia incolla da un compagno, non è apprezzato.