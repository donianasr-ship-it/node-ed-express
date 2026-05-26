# Node-ed-Express

**Il file in questione simula un che codice serve a creare un server web minimale utilizzando Node.js e il framework Express**

```javascript
const express = require('express');
const app = express();
const port = 8080;
```
**In queste brevi linee di codice e racchiusa l'inizializzazione del server, dove nella prima linea viene importata la libreria express nella seconda
invece viene creata un'istanza dell'applicazione express**

**Nell'ultima linea di codice dell'immagine precedente viene definita la porta nel quale il server rimarra in ascolto (di solito la porta 8080)**

**Dopo la richiesta di porta Express crea due oggetti:**
+ req (contiene i dati di chi sta navigando)
+ res (gli strumenti per rispondergli).

## Logica
```javascript
// Respond to GET request on the root route
app.get('/', (req, res) => {
  res.send('GET request to the homepage');
});

// Respond to POST request on the root route
app.post('/', (req, res) => {
  res.send('POST request to the homepage');
});

// Respond to GET request on the /about route
app.get('/about', (req, res) => {
  res.send('About page');
});

// Gestione dell'errore 404 (Valido per Express 5)
app.use((req, res) => {
  res.status(404).send('404 - Page not found');
});
```

**In questo pezzo di codice invece possiamo vedere la parte del routing o instradamento**


**Ogni rotta usa una funzione di callback con due parametri fondamentali: req (la richiesta del client) e res (la risposta del server).**

**app.get('/', ...): Gestisce le richieste di tipo GET (la classica visualizzazione di una pagina) all'indirizzo radice (/, ovvero la homepage). Risponde inviando il testo 'GET request to the homepage'.**

**app.post('/', ...): Gestisce le richieste di tipo POST (usate di solito per inviare dati, come i moduli di login o registrazione) sempre sulla homepage. Risponde con un testo dedicato.**

**app.get('/about', ...): Se l'utente naviga su http://localhost:8080/about, il server intercetta la richiesta e risponde inviando la stringa 'About page'.**

**blocco errori:**
```javascript
// Gestione dell'errore 404 (Valido per Express 5)
app.use((req, res) => {
  res.status(404).send('404 - Page not found');
});
```

**Molto semplicemente questo blocco cattura tutti gli indirizzi sbagliati o inesistenti inseriti dall'utente e
imposta lo stato HTTP 404: Con .status(404) dice al browser che la risorsa non è stata trovata.**



## START DEL SERVER

```javascript
// Start the server
app.listen(port, () => {
  console.log(`Example app listening at http://localhost:${port}`);
});
```

**Infine questo blocco accende ufficialmente il server web Express aprendo la porta ottantaottanta e mettendola in ascolto costante di qualsiasi richiesta in arrivo dal browser. Una volta online, esegue il console log interno che stampa sul terminale un messaggio di conferma per avvisare lo sviluppatore che l'applicazione è attiva e pronta all'uso.**

## AVVIO DEL SERVER TRAMITE IL TERMINALE

**Per consentire l'esecuzione del file, è necessario posizionare il terminale all'interno della directory corretta. Tramite il comando di navigazione, viene specificato il percorso in cui risiede il file sorgente, permettendo così all'ambiente di node.js di individuarlo e avviarlo**

```javascript

PS C:\Users\Stage\Desktop\node_express> cd C:\Users\Stage\Desktop\node_express

```

**avvieremo il server node.js eseguendo il file app.js tramite il seguente comando:**

```javascript

PS C:\Users\Stage\Desktop\node_express> node app.js
Example app listening at http://localhost:8080

```
**"Example app listening at http://localhost:8080" ---> questo sarà il messaggio di conferma stampato nel terminale**

## RiCHIESTA DEL CLIENT E RISPOSTA DEL SERVER 
** uno volta conclusio questi passaggi nel terminare si andrà ad avviare l'applicazione. Da questo momento in poi, il server Node.js entra in uno stato di ascolto attivo sulla porta 8080, rimanendo costantemente in attesa di ricevere le richieste provenienti dal browser. Il processo rimarrà aperto e funzionante nel terminale fino a quando non verrà interrotto manualmente."

<img width="548" height="391" alt="Immagine 2026-05-26 162011" src="https://github.com/user-attachments/assets/a0349851-0e0c-47ba-8952-36cd1aa170c2" />

**se andiamo  sulla homepage all'indirizzo http://localhost:8080 Il server intercetta la chiamata e risponde restituendo il testo "GET request to the homepage". se inevce Effettuando l'accesso alla pagina About tramite l'URL http://localhost:8080/about  In questo caso, il server elabora la richiesta e invia come risposta la stringa "About page".**









