# SkillTrack Coach — Premium Studio v0.2

Nuova proposta grafica di SkillTrack Coach, basata sul prototipo v0.1. **Non è una piattaforma multiutente**: è una demo HTML/CSS/JS con dati fittizi salvati nel browser locale.

## Design

- **Sidebar** grafite/nero notte `#181929`, con navigazione vettoriale coerente.
- **Canvas** perla `#F4F5F9`, superfici bianche e bordi sottili.
- **Accent** viola elettrico `#6254E8`, impiegato per pulsanti, selezioni e grafici.
- **Hero** notte/indaco con geometrie sottili; KPI con migliore gerarchia tipografica.
- Nuovo grafico reale di distribuzione delle sessioni registrate per atleta.
- Restyling coerente di editor, atleti, progressi, feedback, amministrazione e vista atleta.
- Responsive per desktop e iPhone. Non richiede librerie o font a pagamento.

## Come provarla

1. Apri `index.html` da computer per una prova veloce, oppure carica **tutti i file nella radice di un nuovo repository GitHub Pages** per provarla da iPhone.
2. Se hai già pubblicato il prototipo coach v0.1 e vuoi sostituirlo, effettua prima `Esporta dati demo`. Puoi poi sostituire `styles.css`, `app.js`, `index.html`, `sw.js`, `icon.svg` e `manifest.webmanifest` nel repo della demo coach. **Non sostituire mai i file del repository della tua app personale.**
3. L'interfaccia è volutamente dimostrativa. Non inserire dati reali di clienti, filmati, informazioni su infortuni o pagamenti veri.

Le modifiche estetiche conservano la chiave `localStorage` della v0.1 (`skilltrack-coach-demo-v1`) per non cancellare i dati della demo. **Questo non è ancora un sistema di backup affidabile.**

## Flusso testato in browser

- Dashboard e grafico per atleta;
- Libreria programmi ed editor;
- Passaggio a vista atleta;
- Registrazione serie e completamento sessione;
- Ritorno al profilo atleta nel coach.

## Stato delle funzionalità

**Funzionanti nella sola demo locale:** dashboard; gestione atleti fittizi; editor blocchi, esercizi e target; 3 modalità di programmazione; copia individuale di schede; risultati inseriti dall'atleta nello stesso browser; confronti settimanali di base; feedback testuali; scadenze e importi manuali; export JSON demo.

**Solo parziali:** struttura di allenamento differente tra settimane (modifica target, non ancora blocchi differenti per W2/W3); logica specifica per combo/superserie/EMOM; controllo rigoroso comparabilità; editor mobile a livello premium; gestione dei mesocicli e pause; gestione dei feedback e CRM reale.

**Non presenti:** login e ruoli veri; database multiutente; sincronizzazione coach-atleta; storage privato, video, annotazioni su frame; offline con coda sync; notifiche; importazione Excel/Canva/PDF; AI; calendario programmazione e check-in; abbonamenti, incassi e fatturazione; GDPR/compliance e gestione professionale dei dati.

Prossima tappa consigliata: sviluppare editor settimanale completo + versioni immutabili delle schede + prototipo di analisi feedback coach prima di integrare backend e pagamenti.
