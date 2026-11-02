# SkillTrack Coach — Gap analysis della demo v0.2

## Presente e provabile

- Dashboard demo, navigazione desktop/mobile.
- Profili atleti, obiettivi, programma assegnato e scadenze manuali.
- Modelli e copie indipendenti delle schede.
- Tre approcci di programmazione: fissa, preprogrammata, aggiornabile.
- Blocchi configurabili, esercizi, unità, set, target, variante, loop, kg, riposo.
- Registrazione delle singole serie nella vista atleta; note, RPE, riepilogo coach.
- Progressioni W1–Wn per esercizio; feedback testuale; JSON della demo.

## Criticità funzionali da risolvere prima della beta

1. **Editor non totalmente libero per settimana.** W2 e W3 possono variare target dello stesso esercizio, ma non ancora aggiungere/rimuovere giorni, blocchi, esercizi solo in una settimana.
2. **Tipologie di blocco non hanno ancora logiche dedicate.** Superserie, EMOM, AMRAP e combo sono per ora forme di rappresentazione; servono timer, sequenze, criteri di completamento, modifiche e logica per singolo elemento.
3. **Programmazione ed esecuzione.** Servono prescrizione e risultato effettivo per singola serie, insieme a un versionamento sicuro delle schede, pubblicazione con data di efficacia e storico inalterabile.
4. **Calendario.** Mesocicli variabili, pause, recuperi, riassegnazione settimane, modifiche alla programmazione senza modificare i dati già completati.
5. **Analytics.** Comparazioni a parità di assistenza, variante, ripetizioni, durata; trend su fatica, compliance, e record; analisi che segnala i dati non confrontabili.
6. **Coach workflow.** Inbox prioritaria dei feedback da fare, richieste, scadenze, alert, report e comunicazioni contestuali.
7. **Mobile atleta.** Registro one-tap, gesti rapidi, offline, sincronizzazione affidabile, check-in e registrazione di combo composte da elementi tecnici.

## Funzioni commerciali da progettare, non ancora implementate

- Onboarding coach/atleta, account, organizzazioni, team e ruoli (coach, collaboratore, atleta, admin).
- Login, inviti, passaggio tra coach, accessi e diritti sui programmi/dati.
- Messaggi, upload/video streaming, timestamp annotations, notifiche.
- CRM clienti, pacchetti, piani, rinnovi, abbonamenti, solleciti, dashboard di ricavi e pagamenti; integrazioni Stripe.
- Libreria esercizi, video demo, import Excel/PDF/Word/Canva, dizionario abbreviazioni e AI Copilot.
- Multi-tenant Postgres con RLS, backup server, audit log, controllo modifiche, storage video privato, privacy by design e futura conformità GDPR.

## Esito del controllo

**La demo non ha tutte le funzioni di un gestionale professionale.** È una prova di flusso e design. La v0.2 modifica principalmente UI/UX, senza introdurre un backend reale. Testato in browser con dati simulati; non testata direttamente su iPhone fisico.
