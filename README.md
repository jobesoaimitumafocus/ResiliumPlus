# Sito vetrina — Resilium+

Sito di presentazione di **Resilium+** (landing page ufficiale). Non è operativo:
serve a **presentare l'app**, raccogliere interesse e portare le persone a scaricarla.
È **statico** (solo HTML/CSS/JS), trilingue **Italiano / English / Español**, e pronto
per **GitHub Pages** sul dominio **resiliumplus.tech**.

---

## 📁 Cosa c'è dentro

```
resiliumplus-site/
├── index.html          ← TUTTO il sito (testi, stile e logica in un unico file)
├── CNAME               ← dominio personalizzato (resiliumplus.tech)
├── robots.txt          ← istruzioni per i motori di ricerca
├── sitemap.xml         ← mappa del sito per Google
├── .nojekyll           ← dice a GitHub di non processare i file
├── README.md           ← questo file
├── privacy.html        ← pagina Privacy (richiesta da Apple)
├── terms.html          ← pagina Termini d'uso
└── assets/
    ├── img/            ← logo + foto dei 4 pilastri (ottimizzati per il web)
    └── icons/          ← favicon e icona social
```

---

## 👀 Vederlo subito sul tuo computer

Fai **doppio click su `index.html`**: si apre nel browser. Tutto qui.
Cambia lingua con i pulsanti **IT / EN / ES** in alto a destra.

---

## 🚀 Pubblicarlo su GitHub Pages (gratis)

1. Vai su **https://github.com** e crea un nuovo repository (es. `resiliumplus-site`).
   Può essere anche **privato**? No: per GitHub Pages gratuito serve **pubblico**.
2. Carica **tutti i file di questa cartella** dentro il repository
   (pulsante **"Add file" → "Upload files"**, poi trascina tutto, infine **Commit**).
3. Nel repository vai su **Settings → Pages**.
4. Alla voce **"Build and deployment" → Source**, scegli **"Deploy from a branch"**,
   ramo **`main`**, cartella **`/ (root)`** → **Save**.
5. Dopo 1-2 minuti il sito è online all'indirizzo `https://<tuo-utente>.github.io/resiliumplus-site/`.

---

## 🌐 Collegare il dominio resiliumplus.tech

Il file **`CNAME`** è già pronto con `resiliumplus.tech`. Devi solo configurare il DNS
dal pannello dove hai registrato il dominio:

**Dominio principale (resiliumplus.tech)** → aggiungi 4 record di tipo **A**:
```
A   @   185.199.108.153
A   @   185.199.109.153
A   @   185.199.110.153
A   @   185.199.111.153
```
**Sottodominio www** → un record **CNAME**:
```
CNAME   www   <tuo-utente>.github.io
```
Poi in **Settings → Pages → Custom domain** scrivi `resiliumplus.tech` e attiva
**"Enforce HTTPS"** (può richiedere qualche ora la prima volta).

> Il TLD `.tech` funziona perfettamente con HTTPS. Aspetta che il DNS si propaghi
> (di solito 10-30 minuti, max 24 ore). Verifica su https://dnschecker.org.

---

## ✏️ Come modificare i contenuti (facile)

Apri **`index.html`** con un editor di testo. Tutti i testi sono nel blocco
**`const I18N = { ... }`** (verso la fine del file), divisi per lingua: `it`, `en`, `es`.

### Link agli store (App Store / Google Play)
In cima allo `<script>` trovi:
```js
const CONFIG = {
  email: 'info@resiliumplus.tech',
  appStoreUrl: '',   // ⬅️ incolla qui l'URL App Store quando l'app è pubblicata
  playStoreUrl: '',  // ⬅️ incolla qui l'URL Google Play quando esce la versione Android
};
```
- Finché `appStoreUrl` è vuoto, il badge iOS mostra **"In arrivo"**.
- Appena incolli il link reale, il badge diventa **cliccabile** automaticamente.
- Stessa cosa per Android con `playStoreUrl` (oggi mostra **"Presto disponibile"**).

### Novità (sezione "Novità")
Cerca `"news"` dentro `I18N` → modifica gli oggetti in `items`
(`date`, `tag`, `title`, `text`). Ricordati di aggiornarli in **tutte e 3 le lingue**.

### Eventi (sezione "Eventi")
Cerca `"events"` → modifica `items` (`day`, `month`, `title`, `place`, `text`).
Gli eventi attualmente presenti sono **esempi**: sostituiscili con i tuoi.

---

## 📧 Email di contatto

Tutto punta a **info@resiliumplus.tech** (footer, sezione Contatti, modulo "Avvisami").
Per cambiarla, modifica `email` dentro `CONFIG`.

> ⚠️ Ricorda di far funzionare davvero la casella **info@resiliumplus.tech**
> (anche un semplice inoltro verso la tua Gmail va benissimo).

---

## 🧩 Note

- **Logo e foto** vengono dai tuoi asset originali (`_ASSET_DA_JOSE`), ottimizzati per il web.
- Il sito è **responsive** (bello su telefono, tablet e desktop) e **accessibile**.
- Le pagine **privacy.html** e **terms.html** usano i testi legali del progetto adattati a
  `resiliumplus.tech`. Prima di pubblicare, sostituisci i segnaposto
  `[Nome cognome / Ragione sociale]` e `[Città]` con i tuoi dati reali.
