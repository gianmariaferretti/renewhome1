# Renew Home — sito pronto per Vercel

Sito statico (HTML + CSS + JS, con un pannello React compilato nel browser da Babel).

## Come fare il deploy

### Metodo 1 — Drag & drop (più semplice)
1. Vai su https://vercel.com/new
2. Trascina questa cartella (`renew-home-deploy`) nella finestra, oppure caricala come progetto.
3. Quando chiede il "Framework Preset" scegli **Other** (è un sito statico).
4. Lascia vuoti "Build Command" e "Output Directory".
5. Deploy.

### Metodo 2 — Vercel CLI
```bash
npm i -g vercel
cd renew-home-deploy
vercel
```

### Metodo 3 — Git (GitHub/GitLab)
1. Metti il contenuto di questa cartella nella root del repo.
2. Importa il repo su Vercel.
3. Framework Preset: **Other**, niente build command.

## Cosa era rotto prima
- Il file principale si chiamava `Renew Home.html` (con lo spazio): Vercel cerca `index.html` nella root, quindi il dominio mostrava 404 / pagina vuota. Ora è rinominato `index.html`.
- C'erano file inutili (cache di Chrome ~7 MB, screenshot, un PDF da ~7 MB): rimossi.

## Note
- Il pannello "Tweaks" (`tweaks.jsx`) funziona perché React e Babel sono caricati da CDN e il JSX viene compilato nel browser.
- Le "image slot" online sono in sola lettura (la funzione di salvataggio esiste solo dentro l'editor di Claude): non danno errori, restano dei segnaposto.
