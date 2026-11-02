# SkillTrack Coach — documento di progettazione 0.1

**Obiettivo:** gestionale per coach di calisthenics e app atleta, estensibile a altre discipline. Si parte da una demo navigabile, non da un prodotto commerciale.

## Problema da risolvere

Molti coach preparano schede in Word, Canva, Excel o PDF; raccolgono risultati e video su WhatsApp. SkillTrack deve ridurre il lavoro manuale senza imporre uno stile di programmazione unico.

## Due esperienze

### Coach

- Home con atleti attivi, sedute, feedback da controllare e rinnovi.
- Anagrafica atleti: obiettivi, livello, programma, storico, feedback, promemoria amministrativi.
- Libreria di programmi riutilizzabili, programmi individuali e schede versionate.
- Editor a blocchi con giornate e settimane configurabili.
- Progressi per esercizio, giornata, settimana e mesociclo; comparabilità verificata prima di calcolare percentuali.
- Modulo feedback: commenti su sessioni ed esercizi, video con riferimenti temporali (futuro).
- Gestione commerciale: clienti, scadenze, servizi e rinnovi; integrazione pagamenti in fase futura.

### Atleta

- Scheda prescritta, risultati effettivi, registro serie one-tap e varianti realmente eseguite.
- Calendario che può essere automatico o modificato con motivazione, pause e inizio cicli personalizzabile.
- RPE, qualità tecnica, note e richieste di feedback.
- Progressi leggibili W1–Wn, report sintetici e confronto tra cicli.
- Modalità offline con sincronizzazione differita (futuro).

## Schede: supportare metodi differenti

Ogni programma definisce `duration_weeks`, `days[]` e `progression_mode`:

1. **Identica (`same`)**: stessi target ed esercizi ogni settimana, a prescindere dai risultati effettivi.
2. **Preprogrammata (`planned`)**: il coach configura da subito i target della W1, W2, W3, …; le giornate e gli esercizi potranno differire tra settimane.
3. **Aggiornamento periodico (`rolling`)**: la settimana eredita la programmazione precedente finché il coach non la modifica.

Un giorno contiene `blocks[]`. Tipologie previste: serie tradizionali, superserie, lavoro a tempo, statiche, combo, power move, EMOM/AMRAP, circuiti, blocchi liberi. Ogni esercizio prevede `name`, `unit`, `sets`, `target`, `progression`, `assistance`, `load`, `rest`, `notes`.

**Nota sulla demo:** attualmente consente target settimanali differenti per gli stessi esercizi; l'aggiunta/rimozione *di blocchi ed esercizi solo in una settimana* è una funzione del prossimo sviluppo. In modalità `rolling`, i target della settimana più recente vengono ereditati dalle successive.

## Dati e logica

- **Modelli** di programma distinti dalle **assegnazioni** personali agli atleti. La demo già genera una copia indipendente al momento dell’assegnazione, ma non possiede ancora versionamento immutabile.
- Prescrizione distinta da esecuzione. Il risultato di una serie conserva il target prescritto e il valore reale, più informazioni su variante, assistenza e carico.
- Ogni sessione ha `athlete_id`, `assignment_id`, `day_id`, `week_number`, `actual_date`, `completed_at`, `entries[]`, `notes` e `perceived_effort`.
- Il programma deve supportare versionamento e data di efficacia delle modifiche. Le sessioni completate non si riscrivono retroattivamente.
- Un atleta può avere più coach e viceversa, con diritti di accesso espliciti.
- Percentuali di progresso su valori quantitativi equivalenti: stessa unità, propedeutica, assistenza, carico e contesto comparabile. Se la variante cambia, confronto descrittivo invece di percentuale arbitraria.

## Architettura proposta per la versione multiutente

- Frontend responsive: React / Next.js, PWA athlete-first.
- Backend: PostgreSQL, autenticazione, Row Level Security, storage privato con URL temporanei per video.
- Organizzazioni e membership: `organizations`, `profiles`, `coach_athlete_links`, `exercise_library`, `program_templates`, `program_assignments`, `program_versions`, `workout_sessions`, `set_logs`, `media`, `feedback`, `payments_metadata`.
- Cache e coda offline con sincronizzazione idempotente; gestione dei conflitti.
- Funzioni AI lato server, con supervisione del coach. Nessuna credenziale segreta nel frontend.

## AI — roadmap di valore

1. Importazione da file Excel/PDF/testo di schede esistenti; estrazione con controllo manuale di abbreviazioni e ambiguità.
2. Sintesi settimanali verificabili, ricerca nei dati, bozze di feedback e segnalazioni di scarsa aderenza.
3. Supporto alla revisione di video, **senza** generare diagnosi né giudizi tecnici automatici non validati.

## Sequenza di sviluppo raccomandata

- **Demo 0.1**: interfaccia e flusso locale, dati dimostrativi.
- **MVP 0.2**: autenticazione, ruoli, organizzazioni, assegnazioni individuali e versionamento.
- **MVP 0.3**: editor con struttura diversa per ogni settimana, serie effettive, dashboard e sincronizzazione live.
- **MVP 0.4**: feedback/video, report sintetici e offline.
- **Beta**: prove con 5–10 coach, misure su tempo risparmiato, retention e completamento delle sessioni.
- **Commerciale**: abbonamenti, fatturazione e gestione privacy/sicurezza verificate.

## Cosa NON è stato implementato nel prototipo

Accesso reale coach/atleta, separazione delle organizzazioni, sincronizzazione tra dispositivi, schede versionate per singolo atleta, upload video, notifiche, analisi AI, pagamenti. Non usare la demo con dati personali reali.
