## **Obiettivo del Progetto**

Ogni anno tonnellate di materiali tessili, cartacei, plastici e compositi vengono scartati dalle aziende manifatturiere e destinati alle discariche, mentre artigiani, designer e startup sostenibili faticano a reperire materie prime a costi sostenibili. La piattaforma mette in contatto diretto questi due attori, creando un marketplace dedicato al riutilizzo degli scarti industriali.

## **Funzionalità Principali**

* **Gestione Ruoli e Autenticazione (RBAC):** Sistema di registrazione e login differenziato tra **Aziende** (fornitori) e **Artigiani/Designer** (acquirenti), con gestione delle sessioni PHP, stato utente persistente in header (username e saldo) e funzionalità *"Ricordami"* tramite cookie con validità di 72 ore.  
* **Catalogo e Filtri Dinamici (`lista.php`):** Visualizzazione pubblica dei materiali disponibili, con dettagli avanzati (quantità e prezzo unitario) riservati agli artigiani autenticati e filtro temporale per data di inserimento.  
* **Area Aziende (`offerta.php`):** Dashboard riservata alle aziende per pubblicare nuovi lotti di materiali e modificare descrizione, disponibilità e prezzo unitario di quelli esistenti.  
* **Flusso d'Acquisto e Gestione Credito (`domanda.php`, `conferma.php`, `fine.php`):** Carrello interattivo per gli artigiani con filtro per data, verifica della disponibilità economica rispetto al saldo dell'utente, riepilogo dell'ordine e aggiornamento atomico di inventario e credito su database.  
* **Sicurezza e Principio del Minimo Privilegio:** Separazione degli accessi al database tramite utenze dedicate (`lettore` per le query di sola lettura e `modificatore` per le operazioni di scrittura/aggiornamento), validazione rigorosa degli input lato client e lato server (espressioni regolari per formattazione prezzi, indirizzi, credenziali e date) e percorsi relativi portabili su qualsiasi web server.

## **Stack Tecnologico**

* **Back-end:** PHP (gestione sessioni, cookie, validazione form, interazione MySQL)  
* **Database:** MySQL (schema relazionale normalizzato su 4 tabelle: `utenti`, `dati_aziende`, `dati_artigiani`, `materiali`)  
* **Front-end:** HTML5 (standard W3C), CSS3 (layout modulare con header, menu di navigazione dinamico e footer generato automaticamente), JavaScript (validazione client-side e interattività UI)

