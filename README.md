# Node-ed-Express

Una volta avviata l'applicazione tramite terminale, il server Node.js entra in uno stato di ascolto attivo sulla porta 8080, rimanendo costantemente in attesa di ricevere le richieste HTTP provenienti dal browser.
Il progetto in questione simula un che codice serve a creare un server web minimale utilizzando Node.js e il framework Express


<div align="center">
  <img width="548" height="391" alt="Immagine 2026-05-26 162011" src="https://github.com/user-attachments/assets/a0349851-0e0c-47ba-8952-36cd1aa170c2" />
</div>

+ Gestione della Homepage (http://localhost:8080): Quando il client effettua una richiesta alla pagina principale, il server restituisce in output il testo "GET request to the homepage".
+ Gestione della pagina About (http://localhost:8080/about): Effettuando l'accesso all' indirizzo secondario, il server elabora la richiesta specifica e invia come risposta "About page".


## Installazione di node.js
L'installazione di Node.js viene eseguita direttamente tramite il Prompt dei comandi. Per procedere, è necessario avviare il terminale come amministratore. Andremo a inserire il seguente comando:


```javascript
winget install OpenJS.NodeJS.LTS
```
Fatto questo passaggio si può chiudere la finestra del prompt dei comandi e riaprine una nuova, questo serve a Windows per aggiornare i comandi disponibili.

Passiamo poi alla **verifica di installazione**. Nel nuovo terminale, digita questo comando per verificare che tutto sia a posto:


```javascript
node -v
```

## Avvio del server tramite il terminale

Per consentire l'esecuzione del file, è necessario posizionare il terminale all'interno della directory corretta. Tramite il comando di navigazione, viene specificato il percorso in cui risiede il file sorgente, permettendo così all'ambiente di node.js di individuarlo e avviarlo

```javascript

cd C:\Users\Stage\Desktop\node_express

```

avvieremo il server node.js eseguendo il file app.js tramite il seguente comando:

```javascript

node app.js
```
SE nel terminale esce il messaggio "Example app listening at http://localhost:8080" ---> questo sarà la conferma che è andato tutto a buon fine

## Analisi del codice

```javascript
const express = require('express');
const app = express();
const port = 8080;
```
In queste prime tre linee di codice è racchiusa l'inizializzazione del server:

- Nella prima riga viene importata la libreria express.

- Nella seconda riga viene creata un'istanza dell'applicazione Express.

- Nella terza riga viene definita la porta sulla quale il server rimarrà in ascolto (in questo caso, la porta 8080).

A ogni richiesta ricevuta dal browser, Express genera automaticamente due oggetti fondamentali all'interno delle funzioni di risposta:

+ req (contiene i dati inviati dall'utente che sta navigando).

+ res (fornisce gli strumenti e i metodi per rispondergli).
---
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

In questo pezzo di codice invece possiamo vedere la parte del routing o instradamento


Ogni rotta usa una funzione di callback con due parametri fondamentali: req (la richiesta del client) e res (la risposta del server).

+ app.get('/', ...): Gestisce le richieste di tipo GET (la classica visualizzazione di una pagina) all'indirizzo radice (/, ovvero la homepage). Risponde inviando il testo 'GET request to the homepage'.

+ app.post('/', ...): Gestisce le richieste di tipo POST (usate di solito per inviare dati, come i moduli di login o registrazione) sempre sulla homepage. Risponde con un testo dedicato.

+ app.get('/about', ...): Se l'utente naviga su http://localhost:8080/about, il server intercetta la richiesta e risponde inviando la stringa 'About page'.

**blocco errori:**
```javascript
// Gestione dell'errore 404 (Valido per Express 5)
app.use((req, res) => {
  res.status(404).send('404 - Page not found');
});
```

**Molto semplicemente questo blocco cattura tutti gli indirizzi sbagliati o inesistenti inseriti dall'utente e
imposta lo stato HTTP 404: Con .status(404) dice al browser che la risorsa non è stata trovata.**



**Start del server**

```javascript
// Start the server
app.listen(port, () => {
  console.log(`Example app listening at http://localhost:${port}`);
});
```

Infine questo blocco accende ufficialmente il server web Express aprendo la porta ottantaottanta e mettendola in ascolto costante di qualsiasi richiesta in arrivo dal browser. Una volta online, esegue il console log interno che stampa sul terminale un messaggio di conferma per avvisare lo sviluppatore che l'applicazione è attiva e pronta all'uso.











