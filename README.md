# Node-ed-Express

**Il file in questione simula un che codice serve a creare un server web minimale utilizzando Node.js e il framework Express**

<img width="295" height="65" alt="immagine" src="https://github.com/user-attachments/assets/443b354c-31de-41e0-9ef0-273e15a155e6" />

**In queste brevi linee di codice e racchiusa l'inizializzazione del server, dove nella prima linea viene importata la libreria express nella seconda
invece viene creata un'istanza dell'applicazione express**

**Nell'ultima linea di codice dell'immagine precedente viene definita la porta nel quale il server rimarra in ascolto (di solito la porta 8080)**

**Dopo la richiesta di porta Express crea due oggetti:**
+ req (contiene i dati di chi sta navigando)
+ res (gli strumenti per rispondergli).

## Logica

<img width="417" height="383" alt="foto" src="https://github.com/user-attachments/assets/fc72a4e7-a12a-4cc1-98b4-4a9aff4adae3" />

**In questa immagine invece possiamo vedere la parte del routing o instradamento**
                                       
                                       ⇩ 

**Ogni rotta usa una funzione di callback con due parametri fondamentali: req (la richiesta del client) e res (la risposta del server).**

**app.get('/', ...): Gestisce le richieste di tipo GET (la classica visualizzazione di una pagina) all'indirizzo radice (/, ovvero la homepage). Risponde inviando il testo 'GET request to the homepage'.**

**app.post('/', ...): Gestisce le richieste di tipo POST (usate di solito per inviare dati, come i moduli di login o registrazione) sempre sulla homepage. Risponde con un testo dedicato.**

**app.get('/about', ...): Se l'utente naviga su http://localhost:8080/about, il server intercetta la richiesta e risponde inviando la stringa 'About page'.**


**blocco errori:**
<img width="402" height="84" alt="image" src="https://github.com/user-attachments/assets/541ab596-01cf-4c20-80ab-62373889976e" />

**Molto semplicemente questo blocco cattura tutti gli indirizzi sbagliati o inesistenti inseriti dall'utente e
imposta lo stato HTTP 404: Con .status(404) dice al browser che la risorsa non è stata trovata.**



## START DEL SERVER

<img width="541" height="87" alt="screen" src="https://github.com/user-attachments/assets/213d3c50-c1b4-4932-8bfc-9110bb6ae847" />

**Infine questo blocco accende ufficialmente il server web Express aprendo la porta ottantaottanta e mettendola in ascolto costante di qualsiasi richiesta in arrivo dal browser. Una volta online, esegue il console log interno che stampa sul terminale un messaggio di conferma per avvisare lo sviluppatore che l'applicazione è attiva e pronta all'uso.**


## CODICE COMPLETO
<img width="566" height="540" alt="completo" src="https://github.com/user-attachments/assets/7b3def89-4197-4470-96e0-ef25582d3b41" />





