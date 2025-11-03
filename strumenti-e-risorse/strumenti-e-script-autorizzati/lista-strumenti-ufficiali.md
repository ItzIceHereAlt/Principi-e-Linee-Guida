---
icon: wrench
---

# Lista Strumenti Ufficiali

Per mantenere coerenza, sicurezza e affidabilità durante i controlli, si raccomanda che ogni team definisca una propria lista ufficiale di strumenti. L'uso di software non verificato o sconosciuto può compromettere l'integrità del controllo e la validità delle prove.

Quelli elencati di seguito rappresentano una selezione di software affidabili, efficaci e ampiamente utilizzati nella community, che costituiscono una base solida per qualsiasi team di ScreenShare.

***

#### Strumenti di Analisi di Sistema e Processi

* **System Informer**
  * **Descrizione:** Un potente task manager avanzato che permette l'analisi in tempo reale di processi, thread, servizi, connessioni di rete e utilizzo della memoria. Fondamentale per ispezionare la memoria dei processi alla ricerca di tracce di cheat.
* **Search Everything**
  * **Descrizione:** Un'utility di ricerca per file e cartelle estremamente rapida. Indicizza i volumi NTFS quasi istantaneamente, permettendo di trovare file per nome, data, dimensione o attributi in tempo reale.

***

#### Suite di Strumenti Forensi di Eric Zimmerman

* **Registry Explorer**
  * **Descrizione:** Un visualizzatore avanzato per il Registro di Sistema di Windows. È in grado di leggere i file "hive" del registro, mostrare chiavi e valori cancellati e include bookmark per le posizioni forensi più importanti.
* **PECmd (Prefetch Explorer Command Line)**
  * **Descrizione:** Un tool a riga di comando per analizzare in profondità i file Prefetch (.pf). Estrae tutte le informazioni di esecuzione, inclusi gli ultimi 8 orari di avvio e i file caricati.
* **MFTECmd (MFT Explorer Command Line)**
  * **Descrizione:** Un tool a riga di comando per analizzare la Master File Table (MFT) del file system NTFS. Permette di ricostruire la cronologia dei file, inclusi quelli cancellati, e di rilevare il timestomping.
* **JLECmd (JumpList Explorer Command Line)**
  * **Descrizione:** Un tool a riga di comando per analizzare le Jump List di Windows, che contengono informazioni sui file e le applicazioni a cui si è avuto accesso di recente.
* **SrumECmd (SRUM Explorer Command Line)**
  * **Descrizione:** Un tool a riga di comando per analizzare il database del System Resource Usage Monitor (SRUM), che traccia l'attività dei processi e l'uso della rete per un periodo fino a 30-60 giorni.
* **bstrings**
  * **Descrizione:** Un'utility avanzata per l'estrazione di stringhe da file o dump di memoria, con capacità di ricerca e filtraggio superiori rispetto a tool standard.
* **RecentFileCacheParser (.bcf parser)**
  * **Descrizione:** Analizza il file `RecentFileCache.bcf`, un artefatto che memorizza i percorsi dei file eseguiti di recente. Può contenere tracce di esecuzione anche se altri log sono stati cancellati.

***

#### Suite di Strumenti di NirSoft

* **WinPrefetchView**
  * **Descrizione:** Strumento fondamentale per analizzare i file di Prefetch (`.pf`). Mostra quali programmi sono stati eseguiti, quando e quante volte. È cruciale per stabilire una timeline di esecuzione e per analizzare quali file (`.dll`, `.jar`) sono stati caricati da un processo.
* **LastActivityView**
  * **Descrizione:** Aggrega in un'unica interfaccia cronologica le attività recenti del sistema. Raccoglie dati da Prefetch, chiavi di registro (come `RecentDocs` e `UserAssist`), log degli eventi e altro, fornendo una rapida panoramica delle azioni dell'utente.
* **ExecutedProgramsList**
  * **Descrizione:** Si concentra sull'analisi di diverse chiavi di registro (tra cui `UserAssist`) per elencare i programmi che sono stati eseguiti sul computer. Utile per corroborare le prove di esecuzione trovate con altri strumenti.
* **UserAssistView**
  * **Descrizione:** Decodifica e visualizza le informazioni contenute nelle chiavi di registro `UserAssist`. Queste chiavi tracciano l'avvio di applicazioni tramite l'interfaccia grafica.
* **AlternateStreamView**
  * **Descrizione:** Scansiona il file system alla ricerca di file che contengono Alternate Data Streams (ADS), una tecnica comune per nascondere file malevoli.
* **HashMyFiles**
  * **Descrizione:** Calcola gli hash (MD5, SHA1, SHA256) dei file. Indispensabile per verificare l'integrità di un file e confrontarlo con database di cheat noti.
* **JumpListsView**
  * **Descrizione:** Analizza i file delle Jump List di Windows, che contengono la cronologia dei file aperti di recente da specifiche applicazioni.
* **OpenSaveFilesView**
  * **Descrizione:** Elenca i file aperti o salvati tramite le finestre di dialogo standard di Windows. Utile per scoprire se un injector ha "aperto" una `.dll`.
* **USBDeview**
  * **Descrizione:** Fornisce una cronologia dettagliata dei dispositivi USB collegati al sistema, mostrando data di connessione e disconnessione.
* **TurnedOnTimesView**
  * **Descrizione:** Analizza i log degli eventi per determinare gli intervalli di tempo in cui il computer è stato acceso.
* **RegScanner**
  * **Descrizione:** Un'utility di ricerca per il Registro di Sistema più veloce e potente del `regedit` integrato.

***

#### Strumenti della Community (Sviluppatore: Spokwn)

Questa sezione elenca gli strumenti sviluppati da **Spokwn**, approvati per l'uso. Questi tool sono noti per la loro efficacia e per l'integrazione di molteplici tecniche di analisi forense.

* **JournalTrace:** Un'interfaccia grafica (GUI) per l'analisi del USN Journal, fondamentale per ricostruire la cronologia delle operazioni sui file con filtri avanzati.
* **Paths Parser:** Un tool versatile che analizza una lista di percorsi di file, verificando esistenza, firma digitale e applicando regole euristiche ("generics") per identificare caratteristiche sospette.
* **BAM Parser:** Un parser con interfaccia grafica per le voci del Background Activity Moderator (BAM), che integra controlli sulla firma digitale ed euristiche di rilevamento.
* **Prefetch Parser:** Un'utility per l'analisi dei file Prefetch che integra funzionalità aggiuntive come la verifica della firma, l'analisi del BAM e la scansione con regole YARA.
* **pcasvc-executed:** Un tool specifico per analizzare gli artefatti di esecuzione lasciati dal Program Compatibility Assistant Service (PcaSvc).
* **ActivitiesCache-execution:** Analizza il database della Windows Activities Cache (`ActivitiesCache.db`, la "Timeline") per estrarre la cronologia delle attività dell'utente.
* **Replaceparser:** Un parser focalizzato esclusivamente sul rilevamento delle operazioni di sostituzione di file (file replacement) tramite USN Journal.
* **Kernel-Live-Dump-Analyzer:** Uno strumento avanzato che analizza i dump della memoria del kernel, automatizzando la ricerca di comandi e script associati a tecniche di bypass comuni.

***

#### Strumenti Aggiuntivi Ufficiali

Questi strumenti, provenienti da vari sviluppatori o dalla stessa Microsoft, coprono aree specifiche dell'analisi forense.

**Analisi Forense del File System**

* **FTK Imager (AccessData/Exterro):** Uno strumento essenziale per l'analisi a basso livello del file system, per accedere a file bloccati e per analizzare partizioni non-NTFS come **FAT32** ed **exFAT**.
* **Recuva:** Un'utility specializzata nel recupero di file cancellati, particolarmente utile su drive che non supportano il journaling (come le chiavette USB).

**Analisi di File Eseguibili e Codice**

* **Detect It Easy (DiE):** Rileva se un file eseguibile è stato "impacchettato" (packed) o protetto, analizza l'**entropia** e identifica il compilatore.
* **HxD Hex Editor:** Un editor esadecimale per l'analisi a basso livello del contenuto binario di un file, utile per cercare stringhe o identificare modifiche manuali.
* **PEStudio:** Un potente strumento per l'analisi statica di file eseguibili (PE) che raccoglie un'enorme quantità di informazioni su un file.
* **Strings (Sysinternals):** Un'utility a riga di comando per estrarre le stringhe di testo da file binari.

**Analisi di Mod (Specifico per Minecraft)**

* **Luyten:** Un decompilatore Java semplice e ampiamente utilizzato, essenziale per un'analisi rapida del contenuto di file `.jar`.
* **Recaf:** Un moderno decompilatore ed editor di bytecode Java, considerato un'alternativa più potente a Luyten per analisi approfondite.

**Analisi di Sistema e Rete (Sysinternals Suite)**

* **Process Explorer:** Un'alternativa molto più potente al Task Manager, che mostra informazioni dettagliate sui processi, incluse le `.dll` caricate e le connessioni di rete.
* **Autoruns:** Lo strumento più completo per analizzare le posizioni di avvio automatico in Windows, fondamentale per scovare meccanismi di persistenza.
* **ProcMon (Process Monitor):** Uno strumento di monitoraggio in tempo reale per l'attività del file system, del registro e dei processi (per utenti esperti).
* **TCPView:** Mostra un elenco dettagliato di tutte le connessioni di rete TCP e UDP attive e il processo associato.
