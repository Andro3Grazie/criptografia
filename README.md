# CRIPTOGRAFIA

La criptografia è una branca della crittologia, ovvero la disciplina che si occupa delle scritture nascoste. Questa scienza cifra un messaggio in modo da renderlo incomprensibile a tutti coloro che non possiedono il codice di decriptazione, anche detto chiave.

## Indice

- [Introduzione](#Introduzione)
- [Storia](#Storia)
- [Informatica](#Informatica)
  - [Chiave simmetrica](#Chiave-simmetrica)
    - [Funzionamento](#Funzionamento)
    - [Utilizzo](#Utilizzo) 
    - [Forzatura](#Forzatura)
  - [Chiave asimmetrica](#Chiave-asimmetrica)
    - [Sicurezza](#Sicurezza)
    - [Implementazione](#Implementazione)
  - [Hash](#Hash)
  - [WhatsApp](#WhatsApp)
- [Redattori](#Redattori)
- [Fonti](#Fonti)


## Storia

Sin dall'antichità ci fu un ampio utilizzo di questa tecnica, il militare e dittatore romano Giulio Cesare, lo utilizzò per nascondere messaggi strategici ai nemici attraverso il così detto cifrario di Cesare. Questo sistema si basava su una sostituzione monoalfabetica, ogni lettera veniva cambiata con quella un numero di posizioni avanti nell'alfabeto. Nacque poi un sistema formato da due dischi concentrici, rotanti uno rispetto all'altro, contenenti un alfabeto ordinato per il testo in chiaro e un alfabeto disordinato per il testo cifrato. È da questa tecnica che si sviluppò l'arma tecnologica che svolse un ruolo di primaria importanza durante la seconda guerra mondiale, la macchina *Enigma*. La Germania, grazie a questa innovazione, riusciva a comunicare con le potenze dell'asse senza essere intercettata. Il dispositivo elettromeccanico veniva utilizzato per cifrare e decifrare messaggi, la sua facilità d'uso e l'iniziale indecifrabilità furono le maggiori ragioni del suo ampio utilizzo. Ma nonostante fu modificata durante il suo utilizzo, un gruppo di esperti polacchi riuscì a violarla nel 1932 dopo aver lavorato a lungo con questo obbiettivo. 
Questa fu modificata durante il suo utilizzo, ma questo non impedì ad Alan Turing, partendo dalla macchina *Bomba*, di decifrare i messaggi scambiati da diplomatici e militari delle potenze dell'Asse, sviluppandone un'altra chiamata Colosus. Grazie all'aiuto di scienziati come Turing, le forze alleate riuscirono a ottenere informazioni che influenzarono l'esito della guerra. <br />


## Informatica

La criptografia nel mondo informatico viene utilizzata per garantire la riservatezza dei dati e delle informazioni che viaggiano in rete, questa materia infatti è in costante evoluzione. 

In base al genere di chiave utilizzata è possibile suddividere in due tipologie la crittografia informatica: chiave simmetrica e asimmetrica. Nel primo caso la chiave con cui cifreremo il messaggio sarà la stessa con la quale lo decifreremo, per questo motivo dovremo fornire al nostro destinatario la suddetta chiave. Nel secondo caso, invece, vengono utilizzate due chiavi asincrone, con quella con cui criptiamo non possiamo decriptare. Con questo sistema la cifratura sarà pubbilca, mentre la decriptazione necessariamente privata, in questo modo non bisognerà munire il destinatario di questo codice di sblocco.


### Chiave simmetrica

Questo sistema, prevedendo l'uso della stessa chiave in entrambe le direzioni è molto facile e veloce da implementare. L'algoritmo più diffusso venne sviluppato nel 1998 da due crittografi belgi e prese il nome di *Advanced Encryption Standard (AES)*. Nel novembre del 2001 dopo studi, standardizzazioni e selezione tra i vari algoritmi proposti il *NIST*, ovvero il *National Institute of Standards and Technology* decise di adottarlo come standard. La *National Security Agency (NSA)*, ovvero l'organismo che si occupa della difesa degli stati uniti d'America scelse invece il Rijndael per via della sua maggior flessibilità.

  - #### Funzionamento
    L'AES ha un blocco di dimensione fissa pari a 128 bit e, la chiave può essere di eguali misure, di 192 o 256 bit. 
    Il Rijndael invece, gestisce differenti dimensioni di blocchi e di chiave, questi ultimi devono essere un multiplo di 32 bit con 128 come minimo e e 256 come massimo.

  - #### Utilizzo
    Questi due sistemi vengono utilizzati per proteggere informazioni secretate. Per il livello **secret** è sufficente una chiave a 128 bit, mentre per il livello **top secret** si consiglia l'uso di chiavi a 192 o 256 bit. L'utilizzo di chiavi più lunghe da parte di NSA per documenti così importanti portò alcuni a pensare che avevano individuato un potenziale attacco che potrebbe forzare una chiave relativamente corta, gli esperti dicnono invece che semplicemente è un piano a lungo termine per garantire un elevato margine di sicurezza per i prossimi decenni. 

  - #### Forzatura
    Qeusti algoritmi vengono forzati riducendo il numero di round, i migliori attacchi, effettuati nel 2006, sono riusciti a forzare l'AES con 7 round a 128 bit, 8 round  a 192 bit e 9 round con chiave di 256 bit.<br />
    I crittografi hanno fatto notare che la differenza tra i round effettuati e quelli prima dei quali l'algoritmo non sia più forzabile è ridotta, in particolare con chiavi corte. Attualmente una chiave a 128 bit produce 3,4 x 10^38 combinazioni, considerato il progressivo aumento delle potenze di calcolo delle CPU e il miglioramento delle tecniche di analisi, per forzare una chiave di quel tipo con attacchi Brute Force servirà sempre meno tempo. Tramite un progetto di [distributed.net](https://www.distributed.net/Main_Page) che prevedeva l'utilizzo del tempo libero di CPU di volontari, è stata forzata una chiave a 64 bit per l'algoritmo *RC5*, uno dei candidati all'AES, in quasi 5 anni. <br />
    Nel 2002 venne lanciato un attacco, teorico in quanto impraticabile per via dell'enorme quantità di tempo macchina richiesto, chiamato *XSL*, che ha mostrato un potenziale punto debole di questo algoritmo. Alcuni esperti hanno mosso delle osservazioni agli autori dell'attacco, affermando che sono stati commessi errori teorici e che le loro stime sono ottimistiche.<br />
    Allo stato attuale, la reale pericolosità di questo attacco è un incognita, l'AES è comunque considerato un algoritmo veloce, sicuro e gli attacchi, fin ora presentati, si sono rivelati degli interessanti studi teorici ma con scarsa utilità nella pratica. 


### Chiave asimmetrica

Gli algoritmi asimmetrici utilizzano due chiavi interdipendenti, una per cifrare e l'altra per decodificare, la prima è pubblica mentre la seconda privata. Il fatto di essere a conoscenza di una delle due chiavi non permette di risalire a quella a noi sconosciuta. L'algoritmo che viene maggiormente utilizzato, soprattutto in ambito di commercio elettronico nei protocolli *SSL*, è chiamato *RSA*, prende il nome dai ricercatori del *MIT* che nel 1977 lo svilupparono , *Rivest, Shamir e Adleman*.<br />
Per garantirne il corretto funzionamento è necessario che ogni utente si crei autonomamente entrambe le chiavi, una da rendere pubblica detta diretta e una da mantere privata, detta inversa. In rete noi possiamo trovare una sorta di elenco telefonico con tutte le chiavi dirette in caso necessitassimo di comunicare con un certo utente.

  - #### Sicurezza
    Per ottenere una discreta sicurezza si consiglia l'utilizo di chiavi binarie pari a un numero minimo di 2048 bit. Le chiavi con un minor numero di bit come quelle a 512 sono ricavabili in poche ora, mentre quelle a 1024, anche se ancora largamente utilizzate sono sconsigliate.<br />
    Con questo metodo è possibile anche conoscere la provenienza del messaggio, in quanto io mittente, cifrandolo con la mia chiave privata e poi con la pubblica del destinatario, quest'ultimo capirà che il messaggio viene da me e poi potrà leggerlo. L'RSA a livello teorico non è completamente sicuro, perché vi è la possibilità che conoscendo la chiave pubblica si possa risalire al messaggio; l'enorme mole di cui questa operazione necessiterebbe fa di questo algoritmo un sistema di affidabilità pressoché assoluta. Questo algoritmo è infatti la base dei sistemi crittografici su cui si fondano i sistemi di sicurezza informatici utilizzati sulla rete per autenticare gli utenti. 

  - #### Implementazione
    Considerate le notevoli esigenze hardware per consentire un efficace utilizzo di tale sistema è consigliabile l'uso combinato di questo e del metodo AES. Con l'RSA il codifica un unico messaggio, contenente una chiave segreta; tale chiave verrà poi utilizzata per scambiarsi suddetti messaggi con l'algoritmo a chiave simmetrica.<br />
    Oggi questo algoritmo è quello maggiormente utilizzato per la cifratura di firme digitali, insieme al DSS; anche questo come l'RSA fa uso di un sistema criptografico a chiave pubblica.


### Hash

La funzione di crittografia di hash trasforma una certa quantità di dati, come un file o un messaggio, in una breve stringa fissa, detta *hash value* o *message digest*. Generalmente questo sistema viene utilizzato per garantire l'integrità di un dato messaggio, ovvero accertarsi che quest'utlimo non abbia subito cambiamenti. Qualsiasi modifica ai dati, sia intenzionale che non, cambierà il valore dell'hash. Questo sistema è unidirezionale e deve risultare estremamente difficile da invertire, non permettendo di risalire al valore originario. Gli algoritmi più utilizzati sono stati per molti tempo *MD5* e *SHA-1*, ora però considerati deboli e sostituiti quindi con, la famiglia degli *SHA-2* (*SHA-224*, *SHA-256*, *SHA-384*, *SHA-512*). Secondo gli esperti, anche non essendoci stati attacchi a favore di questa tesi, le varianti *SHA-2* essendo logicamente simili alla variante precedente *SHA-1*, nei prossimi anni necessiteremo di un nuovo standard *SHA-3*.


### WhatsApp

Un esempio di un tipo di crittografia che la maggior parte di noi utilizzerà per buona parte della giornata è quella end to end. Questo sistema di comunicazione cifrata impedisce a terze parti, compresi internet service provider e gestori delle reti, di leggere o alternare i messaggi scambiati tra due persone. In molti sistemi di messaggistica i messaggi appunto vengono archiviati da terze parti per poi essere recuperati dal destinatario. Solitamente i dati vengono fatti transitare sotto protocolli cifrati, mentre per l'archiviazione non vi è alcun genere di crittografia; questo permetterebbe a chiunque di leggerne il contenuto.<br />
La criptografia end-to-end ha proprio l'obiettivo di impedirne la modifica o la lettura, a ovvia eccezione del reale mittente e destinatari/o. Qualsiasi azienda che utilizza questa teconologia non è in grado di rilasciare, neppure alle autorità, i messaggi delle comunicazioni avvenute tra i loro utenti, se non cifrati. 


## Redattori

Questo documento è stato stilato completamente dalle seguenti persone, in base alle [informazioni recepite nella lista che sussegue](#Fonti)**:** [Alessandro Mieli](https://alessandromieli.it/), Francesco Massimei, Gabriele Muzi e Lorenzo Napoli.


## Fonti

- Progettazione tecnologie in movimento (ISBN 9788874853953)

- https://it.wikipedia.org/wiki/Crittografia

- https://it.wikipedia.org/wiki/Crittologia

- https://www.zerounoweb.it/techtarget/searchdatacenter/la-crittografia-quando-nasce-come-funziona-perche-e-alleata-della-sicurezza-informatica/

- https://it.wikipedia.org/wiki/Advanced_Encryption_Standard.

- https://it.wikipedia.org/wiki/RSA_(crittografia)

- https://it.wikipedia.org/wiki/Digital_Signature_Algorithm

- https://it.wikipedia.org/wiki/Funzione_crittografica_di_hash

- https://it.wikipedia.org/wiki/Crittografia_end-to-end