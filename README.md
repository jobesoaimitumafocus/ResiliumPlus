# ResiliumBeta — sito v3 (versione di prova)

Versione **beta** del sito di Resilium+. Serve a vedere e approvare il nuovo sito dal vivo,
**senza toccare** il sito attuale su `resiliumplus.com` (repo `ResiliumPlus`, che resta invariato).

Indirizzo di prova: `https://jobesoaimitumafocus.github.io/ResiliumBeta/`

---

## Come si attiva

1. Crea un repository nuovo chiamato **ResiliumBeta**, pubblico.
2. Carica il contenuto di questa cartella (tutti i file e le cartelle, non la cartella stessa).
3. Vai su **Settings → Pages** e imposta *Source: Deploy from a branch*, ramo `main`, cartella `/ (root)`.
4. Dopo circa un minuto il sito è online all'indirizzo qui sopra.

Il file `CNAME` **non** va aggiunto: il dominio `resiliumplus.com` deve restare collegato al sito attuale.

---

## Cosa c'è

| File | Cosa contiene |
|---|---|
| `index.html` | Il sito completo: trilingue IT/EN/ES, tema chiaro/scuro, demo animata dell'app, quattro pilastri, giuramento, privacy, sezione fondatore, prezzi, FAQ. Un solo file, zero dipendenze oltre al font. |
| `privacy.html` · `terms.html` | Pagine legali. |
| `assets/intro.mp3` | La musica, che parte solo se la persona preme il tasto audio. Mai in automatico. |
| `assets/img/` | Le foto dei quattro pilastri e il ritratto del fondatore, già ottimizzate. |
| `assets/icons/` | Favicon e icone. |
| `robots.txt` | Impedisce ai motori di ricerca di indicizzare la beta. |

Le immagini sono **incorporate dentro `index.html`**: il sito si vede correttamente ovunque,
anche aprendo il file da solo. I file in `assets/img/` servono per la versione definitiva.

---

## Quando la beta sarà approvata

Per portare il sito in produzione su `resiliumplus.com`, nel repo `ResiliumPlus`:

1. Sostituisci `index.html` con quello di questa cartella.
2. Elimina questa riga dal `<head>`:
   `<meta name="robots" content="noindex, nofollow">`
3. Rimetti i percorsi assoluti (`/assets/...`, `/privacy.html`, `/terms.html`) al posto di quelli
   relativi, oppure lascia i relativi: alla radice del dominio funzionano entrambi.
4. Copia le foto di `assets/img/` nella stessa cartella del repo di produzione.
5. Lascia `robots.txt` e `sitemap.xml` del repo di produzione come sono.

---

*Disciplina oggi. Libertà domani.*
