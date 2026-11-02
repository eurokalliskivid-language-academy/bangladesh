================================================================
  SCUOLA GUIDA TEAMILY
  Patente A e B — Questionario ufficiale commentato
  Italiano / বাংলা  ·  Ed. 2026/11 · rev. 6
================================================================

CONTENUTO DELLA CARTELLA
----------------------------------------------------------------
  scuola-guida-patente-ab-it-bn.html   il corso (file principale)
  richiesta-credenziali.html           modulo di iscrizione e credenziali
  LEGGIMI.txt                          questo file

Tieni i tre file nella stessa cartella: il corso richiama il modulo
con un link relativo e, se il modulo viene spostato, il pulsante
"Richiedi credenziali" non funziona più.


1. COME APRIRE IL CORSO
----------------------------------------------------------------
  Doppio clic su  scuola-guida-patente-ab-it-bn.html

Si apre nel browser predefinito. Funziona senza internet, senza
installare nulla e senza server: tutto (domande, figure, QR) è
dentro il file.

Se il doppio clic apre un editor di testo invece del browser:
tasto destro sul file  >  "Apri con"  >  Chrome / Edge / Firefox.


2. LE DUE PASSWORD
----------------------------------------------------------------
  Password del corso .............. Patente2026
      Serve al titolare e come accesso di servizio: funziona con
      qualsiasi username.

  Password del pannello titolare .. Admin2026
      Si apre dall'icona ingranaggio (⚙) in alto a destra.

Entrambe si cambiano in cima al file HTML, dentro CONFIG
(ADMIN_HASH è l'impronta SHA-256 della password, non la password
in chiaro).


3. LE CREDENZIALI DEGLI STUDENTI
----------------------------------------------------------------
Ogni studente ha username e password personali. Il file HTML è
UNO SOLO, identico per tutti: la password è calcolata dallo
username, quindi lo stesso file riconosce ogni studente.

  Come si creano (due modi):

  a) LO STUDENTE SE LE FA DA SOLO  (consigliato)
     Nella pagina di accesso, sotto il pulsante "Accedi", c'è il
     riquadro "Richiedi le tue credenziali": nome, cognome, email,
     username desiderato (o vuoto = nome.cognome) e un clic.
     Username e password compaiono subito a schermo, con il
     pulsante Copia e il pulsante "Entra ora".
     Lo stesso modulo è nella pagina richiesta-credenziali.html.

  b) IL TITOLARE LE CREA
     ⚙ > sezione 3.2 "Credenziali studenti":
       - scrivi nome e cognome, lascia vuoto lo username per
         generarlo automaticamente (nome.cognome, con 2, 3... se
         già esiste);
       - "Crea credenziali" mostra la coppia pronta;
       - pulsanti: Copia utente / Copia password /
         Copia messaggio WhatsApp / Apri email pronta.

  L'elenco degli studenti creati è nella stessa sezione, con
  Copia ed Elimina per ciascuno, e il pulsante "Esporta CSV"
  scarica  credenziali-studenti.csv  (nome, username, password,
  email, data) apribile con Excel.

  ATTENZIONE: eliminare uno studente dall'elenco NON gli toglie
  l'accesso. La password resta valida perché è calcolata dallo
  username. Per chiudere un accesso bisogna cambiare
  UNLOCK_SECRET (vedi punto 6).


4. VERSIONE GRATUITA E PAGAMENTO
----------------------------------------------------------------
Sono gratuite le prime 10 domande di ciascuno dei 31 argomenti:
310 domande in tutto. Finito il decimo quesito di un argomento
compare il blocco con il pagamento di 39 € e le domande
successive restano chiuse.

  Dati per il bonifico (l'unico metodo accettato):
      Importo ......... € 39,00  (una volta sola)
      Beneficiario .... Credenziali Scuola Guida
      Banca ........... Wise
      IBAN ............ BE84 9672 1289 5259
      BIC / SWIFT ..... TRWIBEB1XXX
      Causale ......... precompilata (Patente A e B — username)

Il QR code SEPA è dentro la pagina: inquadrandolo con l'app della
banca si compilano da soli IBAN, importo e causale.

  Pulsante "Paga con Wise":
      non è attivo finché non incolli il tuo link "Richiedi
      denaro" di Wise nella riga, in cima al file:

          WISE_REQUEST_LINK:''

      cioè:  WISE_REQUEST_LINK:'https://wise.com/pay/...'
      Finché è vuoto la pagina lo dice chiaramente e resta
      attivo il bonifico con IBAN e QR.


5. LO SBLOCCO È MANUALE (solo tu puoi farlo)
----------------------------------------------------------------
Non esiste nessuno sblocco automatico: nessun pulsante apre il
corso senza il codice del titolare. Il percorso è questo:

  a) lo studente paga 39 € con bonifico sul conto Wise;
  b) dal blocco del corso preme "Invia richiesta di sblocco":
     si apre l'email già compilata verso
     eurokalliskivid@gmail.com  con username, nome, data e
     riferimento del bonifico;
  c) TU verifichi l'incasso effettivo sul conto Wise;
  d) generi il codice e lo invii (vedi "GENERARE E INVIARE IL CODICE");
  e) lo studente lo incolla nel campo "Inserisci codice di
     sblocco" e il corso si apre, in modo permanente, su quel
     dispositivo.

  GENERARE E INVIARE IL CODICE
     ⚙ > password admin > sezione 3.1 "Sblocco studenti":
       - scrivi lo username e l'email dello studente;
       - "Genera e invia codice": il codice PATENTE-XXXX-XXXX è
         creato e l'email parte subito, già compilata (destinatario,
         oggetto e corpo bilingue con il codice e le istruzioni);
       - in alternativa: "Copia codice", "Copia messaggio
         WhatsApp", oppure "Sblocca ora" se lo studente è davanti
         a te.

  Il codice è legato allo username e funziona su qualsiasi
  dispositivo. Il pannello tiene il registro di tutto (codici
  generati, destinatari, sblocchi, revoche, credenziali create,
  richieste ricevute).

  Revocare uno sblocco: sezione 3.4 "Utenti su questo dispositivo"
  > "Revoca".


6. L'AVVISO PIÙ IMPORTANTE
----------------------------------------------------------------
      NON CAMBIARE  UNLOCK_SECRET  DOPO AVER DISTRIBUITO CODICI
      O CREDENZIALI.

Da quel valore derivano DUE cose:
   - i codici di sblocco  (PATENTE-XXXX-XXXX)
   - le password personali degli studenti

Se lo cambi, TUTTI gli studenti restano fuori: non solo i codici
smettono di funzionare, ma le password già inviate diventano
errate. L'unico modo per rimediare è rigenerare e reinviare ogni
password, una per studente.

Si trova in cima al file HTML, dentro CONFIG:

    UNLOCK_SECRET:'PATENTE-SG-2026-7f3a91c4b8e2d05a'

CONFIG deve essere IDENTICO nel corso e in richiesta-credenziali.html,
altrimenti le password generate dal modulo non valgono nel corso.


7. L'EMAIL: COME FUNZIONA DAVVERO
----------------------------------------------------------------
Tutti i pulsanti che "inviano" un'email (richiesta di sblocco,
codice di sblocco, credenziali studente, domanda di iscrizione)
usano un link  mailto:  e aprono il programma di posta del tuo
computer con messaggio, destinatario e oggetto già compilati.
Devi solo premere "Invia".

Questo NON è un invio automatico in background: un file HTML
locale non può inviare email da solo, perché non ha un server.
Se nella macchina non è configurato nessun programma di posta, il
pulsante non apre nulla: in quel caso copia il testo (pulsante
"Copia il testo" / "Copia messaggio") e incollalo nella tua email.

Per un invio davvero automatico (lo studente riceve il codice
senza che tu prema Invia) serve un backend con un servizio di
posta o un piccolo server: è un progetto separato, realizzabile
a parte.


8. SICUREZZA — DICHIARAZIONE ONESTA
----------------------------------------------------------------
Questo è un file HTML che gira sul computer dello studente: non
c'è un server che controlla gli accessi. Chi apre il codice
sorgente può leggere la password del corso, quella del pannello,
il segreto e quindi ricavare le password.

È un filtro d'accesso, adatto a un uso didattico e a studenti
collaborativi. NON è una protezione crittografica e non va usata
per dati sensibili o per impedire copie deliberate.

Se ti serve un controllo reale degli accessi (un account per
studente validato da un server, sblocco verificato dopo il
pagamento, impossibile da aggirare), serve un'applicazione con
backend: posso prepararla.


9. COSA NON TOCCARE
----------------------------------------------------------------
  - Il blocco  const D={...}  contiene le 7.144 domande: non
    modificarlo. SHA-256 atteso:
    6ff7fb30ac2f30a607a84225a926de90f3922d380a53e346c4a50cd66cac25ed
  - La voce di menu "⬇ HTML" scarica una copia del file corrente.
  - La stampa (Ctrl+P) nasconde i pulsanti e impagina il
    questionario per il foglio A4.


10. DOMANDE FREQUENTI
----------------------------------------------------------------
  Ho perso la password personale.
     Non si recupera: si rigenera. Con il tuo username il titolare
     la ricava identica dal pannello (o tu stessa dal modulo, se
     ricordi lo username).

  Posso usare lo stesso file su più computer?
     Sì. Ogni dispositivo ricorda i propri sblocchi; le credenziali
     valgono ovunque perché derivano dallo username.

  Ho pagato ma il corso resta chiuso.
     È normale: lo sblocco è manuale. Invia la richiesta dal blocco
     e attendi il codice dal titolare.

  Ho cambiato UNLOCK_SECRET e ora nessuno entra.
     Vedi il punto 6: le password vanno rigenerate e reinviate.

================================================================
  Recapito della segreteria: eurokalliskivid@gmail.com
  Ed. 2026/11 · rev. 6
================================================================
