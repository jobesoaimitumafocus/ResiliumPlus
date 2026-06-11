# Sito vetrina — Resilium+

Sito di presentazione di **Resilium+** (landing page ufficiale). Non è operativo:
serve a **presentare l'app**, raccogliere interesse e portare le persone a
scaricarla. È **statico** (solo HTML/CSS/JS), **trilingue** Italiano / English /
Español, e pronto per **GitHub Pages** sul dominio **resiliumplus.com**.

## Cosa c'è

| File | Cosa |
|------|------|
| `index.html` | Landing page completa (hero, metodo 80/20, 4 pilastri, funzioni, giuramento, privacy, prezzi). |
| `privacy.html` | Privacy Policy (coordinata col sito). |
| `terms.html` | Termini d'uso. |
| `robots.txt` · `sitemap.xml` | SEO. |
| `assets/` | Immagini/logo (opzionali). |

## Caratteristiche

- **Light / Dark automatico**: segue le impostazioni del client (`prefers-color-scheme`)
  con **toggle manuale** (☾/☀) che ricorda la scelta.
- **Trilingue IT / EN / ES**: selettore in alto a destra; rileva la lingua del
  browser e ricorda la scelta. Tutti i testi sono nel dizionario `I18N` dentro
  `index.html` — per modificarli, basta cambiare lì.
- **Un solo file, zero dipendenze** (a parte il font Playfair Display da Google
  Fonts). Niente build, niente framework: si carica e funziona.
- **Responsive**, accessibile (contrasto, `prefers-reduced-motion`, contenuto
  visibile anche senza JS).

## Come aggiornarlo

- **Testi**: ogni pagina (`index.html`, `privacy.html`, `terms.html`) ha il suo
  dizionario `I18N` (it/en/es) in fondo al file — modifica lì le tre lingue.
- **Colori/brand**: le variabili CSS in cima a `<style>` (`--gold`, `--ink`,
  i 4 colori dei pilastri, ecc.).
- **Prezzi**: cerca `€4,99` / `€39,99` nei testi.

## Dominio

Tutto allineato su **resiliumplus.com** — sia il sito sia l'app iOS (link
privacy/termini nel paywall, email `support@resiliumplus.com`). Il bundle id
`com.resiliumplus.app` NON è un dominio: resta invariato.

## Da fare prima della pubblicazione

- [x] ~~Dati legali in `privacy.html`/`terms.html`~~ — **fatti**: il titolare è
      indicato come "progetto Resilium+" (nome personale NON esposto sul sito),
      data 2026-06-11, foro = residenza del consumatore, e una sezione
      "Cookie e dati del sito" aggiornata (nessun cookie di tracciamento).
      Nota: l'identità legale completa resta comunque pubblica sulla scheda
      sviluppatore dell'App Store (Apple la richiede) — quindi sei a norma GDPR.
- [ ] Crea la casella **support@resiliumplus.com** (Hostinger → Email → crea
      account, oppure un semplice forwarding verso la tua Gmail).
- [ ] (Opzionale) Inserisci il logo reale in `assets/` e referenzialo nell'header.

## Deploy (GitHub Pages)

1. Carica nella **root** del repo Pages: `index.html`, `privacy.html`,
   `terms.html`, `robots.txt`, `sitemap.xml`, **`CNAME`** (già pronto, contiene
   `resiliumplus.com`) e `assets/`.
2. Nel repo → **Settings → Pages → Custom domain** → `resiliumplus.com` → Save.
   Dopo la propagazione DNS, spunta **Enforce HTTPS**.

## Collegare il dominio (Hostinger → GitHub Pages)

In **hpanel.hostinger.com → Domini → resiliumplus.com → DNS/Nameserver**, nella
zona DNS aggiungi questi record (apex + www):

```
Tipo   Nome   Valore
A      @      185.199.108.153
A      @      185.199.109.153
A      @      185.199.110.153
A      @      185.199.111.153
CNAME  www    jobesoaimitumafocus.github.io
```

(Facoltativi IPv6 — record AAAA per `@`: 2606:50c0:8000::153, 2606:50c0:8001::153,
2606:50c0:8002::153, 2606:50c0:8003::153.)

La propagazione richiede da pochi minuti ad alcune ore. Verifica con
`dig resiliumplus.com` o dnschecker.org.
