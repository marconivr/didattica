# CDN ( Content Delivery Network) Surge 

*"CDN is short for content delivery network. A content delivery network (CDN) is a system of distributed servers (network) that deliver pages and other Web content to a user, based on the geographic locations of the user, the origin of the webpage and the content delivery server."*

Vedi anche:

*	Github Pages
*	Amazon S3

## Download e installazione e aggiornamento Node.js e moduli

Download dal sito ufficiale nella versione necessaria

	https://nodejs.org/en/download/
	
Installazione

Esecuzione del file scaricato  .msi o .exe e ok su tutte le richieste

###  Verifica installazione

Eseguire command line CMD (su disco e cartella generica di comodo)

	d:\Temp>node --version
	
### Aggiornamento build tools Node.js

Nell'installazione di applicativi nodejs può essere (a me è capitato) segnalata la presenza di pacchetti deprecati o aggiornabili.
Nel mio caso i due pacchetti da aggiornare erano due e per aggiornarli ho eseguito i due comandi tramite npm (Node Package 

	d:\Temp>npm install --global minimatch@3.0.2
	d:\Temp>npm install --global boom@4.3.1
	
### Uninstall moduli npm Node.js

	d:\Temp>npm uninstall --global <nomemodulo>	
	
	
## Installazione pacchetto Surge

	d:\Temp>npm install --global surge
	
Nonostante l'aggiornamento dei moduli mi segnala che alcuni di essi sono aggiornabili (surge non vede l'aggiornamento) ma per ora va bene cosi.
	

## Surge

Se tutto è andato correttamente (a parte i messaggi di deprecated) siamo pronti per utilizzare Surge.

Scegliere la cartella di sviluppo del sito web (una a scelta)

	d:\wwwroot\htdocs\dev\surge>
	
Creare la prima pagina index.html

	d:\wwwroot\htdocs\dev\surge>notepad index.html
	
### Deploy progetto web

Pubblicarla con Surge

	d:\wwwroot\htdocs\dev\surge>surge
	
Chiede email e password con cui registrarsi e poi successivamente identificarsi su CDN surge.sh 

Suggerisce la cartella attuale come progetto surge, quindi nel caso attuale

	D:\wwwroot\htdocs\dev\surge\
		
Poi chiede il domain con cui pubblicare su CDN Surge (er l'esempio):

	giannibellini.surge.sh
	
Se l'output è:

	Success! - Published to giannibellini.surge.sh
	
FATTO!

## VIsualizzazione deploy

Con un browser web

	http://giannibellini.surge.sh
	
oppure (funziona anche SSL)

	https://giannibellini.surge.sh
	
## Deploy successivi

Nella stessa sessione ogni deploy per modifiche delle pagine del progetto web, viene eseguito senza più richiesta
password, ma solo confermando il progetto da pubblicare

	D:\wwwroot\htdocs\dev\surge>surge -d giannibellini.surge.sh
	
oppure 

	D:\wwwroot\htdocs\dev\surge>surge --domain giannibellini.surge.sh
	
## Cancellare progetto web

	D:\wwwroot\htdocs\dev\surge>surge teardown giannibellini.surge.sh

## Opzioni deploy

### Aggiungere un dominio custom

Per evitare di dover indicare ogni volta il dominio di pubblicazione valorizzare la variabile CNAME

	D:\wwwroot\htdocs\dev\surge>echo giannibellini.surge.sh > CNAME
	
la pubblicazione ora può avvenire con il comando:

	D:\wwwroot\htdocs\dev\surge>surge
	
	

	
	
	


	
	
