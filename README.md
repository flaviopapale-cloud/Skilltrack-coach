# SkillTrack Coach — Prototipo navigabile (v0.1)

Questa è una **demo locale con dati fittizi**, non un prodotto multiutente. Mostra il flusso coach → programmazione → atleta → allenamento → progressi → feedback.

## Cosa puoi provare

- Dashboard coach e profilo di ciascun atleta demo.
- Editor flessibile con giornate configurabili e blocchi per serie, statiche, volume a tempo, superserie, combo, EMOM, power move, circuiti.
- Tre strategie di programmazione: stessa scheda per tutto il ciclo; progressioni già definite W1–Wn; modifiche settimana per settimana.
- Creazione di nuove schede da 1 a 7 giorni e 1 a 12 settimane (modificabili successivamente), duplicazione di programmi.
- Parametri personalizzati per esercizio: nome/abbreviazione, unità, serie, target, propedeutica, loop, carico, recupero.
- Assegnazione di una **copia individuale** del programma all’atleta (demo, stesso browser). Le modifiche alla copia non modificano il modello condiviso.
- Vista atleta su telefono: risultati delle singole serie, note, RPE, salvataggio sessione.
- Progressioni settimanali reali nel profilo atleta e nella vista Progressi, con percentuali solo su dati comparabili.
- Feedback testuale del coach, CRM di esempio con scadenze e importi manuali, esportazione JSON della demo.

## Come aprirla

**Computer:** apri `index.html` con un browser, oppure pubblica i file su GitHub Pages.

**GitHub Pages:** crea un *nuovo* repository pubblico, ad esempio `SkillTrack-Coach-Demo` (non modificare il repository dell'app personale `SkillTrack`), carica il contenuto di questa cartella nella radice del repository, attiva *Settings → Pages → Deploy from a branch → main → /(root)*. L'indirizzo sarà `https://<username>.github.io/SkillTrack-Coach-Demo/`.

**iPhone:** apri l'URL con Safari e usa *Condividi → Aggiungi alla schermata Home*.

## Limiti e dati

- Tutti gli atleti sono fittizi (Atleta A, B, C, D).
- I dati modificati sono salvati nel `localStorage` del browser **su quel dispositivo**.
- La vista coach e quella atleta condividono i dati perché sono nello **stesso browser**, non perché esista un vero account o backend.
- Nessuna autenticazione, isolamento tra coach, sincronizzazione multi-dispositivo, storage privato per video, pagamento, AI o conformità operativa GDPR.
- **Non inserire informazioni reali dei clienti, dati sanitari o video personali nella demo pubblicata su GitHub Pages.**
- Il JSON scaricato dal pulsante "Esporta dati demo" serve a ispezionare il modello; non è disponibile un comando di importazione in questa demo.

## Struttura

- `index.html` — shell del sito
- `styles.css` — interfaccia responsive
- `app.js` — logica del prototipo e dati demo
- `manifest.webmanifest`, `icon.svg`, `sw.js` — installazione PWA e cache della versione demo

## Architettura futura (da implementare, non presente nella demo)

PWA/React + autenticazione + PostgreSQL/Supabase con isolamento organizzazioni (RLS), schede versionate, sincronizzazione offline, storage privato per video, automazioni, AI Copilot e, solo in seguito, pagamenti. In questa fase non è necessario collegare servizi esterni.
