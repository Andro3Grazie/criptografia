# CRIPTOGRAFIA

## Indice

- [Introduzione](#Introduzione)
- [Storia](#Storia)
- [Informatica](#Informatica)
- [Chiave simmetrica](#Chiave-simmetrica)
  - [Funzionamento](#Funzionamento)
  - [Utilizzo](#Utilizzo) 
  - [Forzatura](#Forzatura)
- [Chiave asimmetrica](#Chiave-asimmetrica)
- [Fonti](#Fonti)


## Introduzione

La criptografia è una branca della crittologia, ovvero la disciplina che si occupa delle scritture nascoste. Questa scienza cifra un messaggio in modo da renderlo incomprensibile a tutti coloro che non possiedono il codice di decriptazione, anche detto chiave.


## Storia

Sin dall'antichità ci fu un ampio utilizzo di questa tecnica, il militare e dittatore romano Giulio Cesare, lo utilizzò per nascondere messaggi strategici ai nemici attraverso il così detto cifrario di Cesare. Questo sistema si basava su una sostituzione monoalfabetica, ogni lettera veniva cambiata con quella un numero di posizioni avanti nell'alfabeto. Nacque poi un sistema formato da due dischi concentrici, rotanti uno rispetto all'altro, contenenti un alfabeto ordinato per il testo in chiaro e un alfabeto disordinato per il testo cifrato. È da questa tecnica che si sviluppò l'arma tecnologica che svolse un ruolo di primaria importanza durante la seconda guerra mondiale, la macchina Enigma. La Germania, grazie a questa innovazione, riusciva a comunicare con le potenze dell'asse senza essere intercettata. Il dispositivo elettromeccanico veniva utilizzato per cifrare e decifrare messaggi, la sua facilità d'uso e l'iniziale indecifrabilità furono le maggiori ragioni del suo ampio utilizzo. Ma nonostante fu modificata durante il suo utilizzo, un gruppo di esperti polacchi riuscì a violarla nel 1932 dopo aver lavorato a lungo con questo obbiettivo. 
Questa fu modificata durante il suo utilizzo, ma questo non impedì ad Alan Turing, partendo dalla macchina Bomba, di decifrare i messaggi scambiati da diplomatici e militari delle potenze dell'Asse, sviluppandone un'altra chiamata Colosus. Grazie all'aiuto di scienziati come Turing, le forze alleate riuscirono a ottenere informazioni che influenzarono l'esito della guerra. <br />


## Informatica

La criptografia nel mondo informatico viene utilizzata per garantire la riservatezza dei dati e delle informazioni che viaggiano in rete, questa materia infatti è in costante evoluzione. 

In base al genere di chiave utilizzata è possibile suddividere in due tipologie la crittografia informatica: chiave simmetrica e asimmetrica. Nel primo caso la chiave con cui cifreremo il messaggio sarà la stessa con la quale lo decifreremo, per questo motivo dovremo fornire al nostro destinatario la suddetta chiave. Nel secondo caso, invece, vengono utilizzate due chiavi asincrone, con quella con cui criptiamo non possiamo decriptare. Con questo sistema la cifratura sarà pubbilca, mentre la decriptazione necessariamente privata, in questo modo non bisognerà munire il destinatario di questo codice di sblocco.


## Chiave simmetrica

Questo sistema, prevedendo l'uso della stessa chiave in entrambe le direzioni è molto facile e veloce da implementare. L'algoritmo più diffusso venne sviluppato nel 1998 da due crittografi belgi e prese il nome di *Advanced Encryption Standard (AES)*. Nel novembre del 2001 dopo studi, standardizzazioni e selezione tra i vari algoritmi proposti il *NIST*, ovvero il *National Institute of Standards and Technology* decise di adottarlo come standard. La *National Security Agency (NSA)*, ovvero l'organismo che si occupa della difesa degli stati uniti d'America scelse invece il Rijndael per via della sua maggior flessibilità.

#### Funzionamento
L'AES ha un blocco di dimensione fissa pari a 128 bit e, la chiave può essere di eguali misure, di 192 o 256 bit. 
Il Rijndael invece, gestisce differenti dimensioni di blocchi e di chiave, questi ultimi devono essere un multiplo di 32 bit con 128 come minimo e e 256 come massimo.

#### Utilizzo
Questi due sistemi vengono utilizzati per proteggere informazioni secretate. Per il livello **secret** è sufficente una chiave a 128 bit, mentre per il livello **top secret** si consiglia l'uso di chiavi a 192 o 256 bit. L'utilizzo di chiavi più lunghe da parte di NSA per documenti così importanti portò alcuni a pensare che avevano individuato un potenziale attacco che potrebbe forzare una chiave relativamente corta, gli esperti dicnono invece che semplicemente è un piano a lungo termine per garantire un elevato margine di sicurezza per i prossimi decenni. 

#### Forzatura
Qeusti algoritmi vengono forzati riducendo il numero di round, i migliori attacchi, effettuati nel 2006, sono riusciti a forzare l'AES con 7 round a 128 bit, 8 round  a 192 bit e 9 round con chiave di 256 bit.
I crittografi hanno fatto notare che la differenza tra i round effettuati e quelli prima dei quali l'algoritmo non sia più forzabile è ridotta, in particolare con chiavi corte. Attualmente una chiave a 128 bit produce 3,4 x 10^38 combinazioni, considerato il progressivo aumento delle potenze di calcolo delle CPU e il miglioramento delle tecniche di analisi, per forzare una chiave di quel tipo con attacchi Brute Force servirà sempre meno tempo. Tramite un progetto di [distributed.net](https://www.distributed.net/Main_Page) che prevedeva l'utilizzo del tempo libero di CPU di volontari, è stata forzata una chiave a 64 bit per l'algoritmo RC5, uno dei candidati all'AES, in quasi 5 anni.
Nel 2002 venne lanciato un attacco, teorico in quanto impraticabile per via dell'enorme quantità di tempo macchina richiesto, chiamato XSL, che ha mostrato un potenziale punto debole di questo algoritmo. Alcuni esperti hanno mosso delle osservazioni agli autori dell'attacco, affermando che sono stati commessi errori teorici e che le loro stime sono ottimistiche.<br />
Allo stato attuale, la reale pericolosità di questo attacco è un incognita, l'AES è comunque considerato un algoritmo veloce, sicuro e gli attacchi, fin ora presentati, si sono rivelati degli interessanti studi teorici ma con scarsa utilità nella pratica. 


## Chiave asimmetrica

Gli algoritmi asimmetrici utilizzano due chiavi interdipendenti, una per cifrare e l'altra per decodificare, la prima è pubblica mentre la seconda privata. Il fatto di essere a conoscenza di una delle due chiavi non permette di risalire a quella a noi sconosciuta. L'algoritmo che viene maggiormente utilizzato, soprattutto in ambito di commercio elettronico nei protocolli SSL, è chiamato *RSA*, prende il nome dai ricercatori del MIT che nel 1977 lo svilupparono , *Rivest, Shamir e Adleman*.


## Fonti

- Progettazione tecnologie in movimento (ISBN 9788874853953)

- https://it.wikipedia.org/wiki/Crittografia

- https://it.wikipedia.org/wiki/Crittologia

- https://www.zerounoweb.it/techtarget/searchdatacenter/la-crittografia-quando-nasce-come-funziona-perche-e-alleata-della-sicurezza-informatica/

- https://it.wikipedia.org/wiki/Advanced_Encryption_Standard.
