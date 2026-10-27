# Istituto Caso 3D + Gestione LIM: come metterlo online con GitHub

Contenuto della cartella:
- `index.html`: pagina iniziale con i tre collegamenti
- `caso.html`: passeggiata 3D
- `halloween.html`: versione Halloween
- `gestione.html`: pannello per scegliere immagine e sito di ogni LIM
- `lim-config.json`: qui il pannello scrive la scelta delle 3 LIM (non toccarlo a mano)
- `images/`: qui il pannello salva le immagini
- `.nojekyll`: file vuoto che serve a GitHub Pages

## 1. Crea il repository
1. Vai su https://github.com e accedi (o registrati, è gratis).
2. In alto a destra: **+ → New repository**.
3. Nome, per esempio `lim-istituto-caso`. Scegli **Public** (con l'account gratuito GitHub Pages lo richiede).
4. Clicca **Create repository**.

## 2. Carica i file
1. Nella pagina del repository clicca **uploading an existing file**.
2. Trascina dentro **tutti i file e la cartella `images`** di questo pacchetto (non lo zip).
   Se il file `.nojekyll` non si vede nella cartella, crealo dopo con **Add file → Create new file**, nome `.nojekyll`, contenuto vuoto.
3. In fondo clicca **Commit changes**.

## 3. Attiva il sito
1. **Settings → Pages**.
2. In *Build and deployment* scegli **Deploy from a branch**, ramo **main**, cartella **/ (root)**, poi **Save**.
3. Dopo 1-2 minuti l'indirizzo compare in alto: `https://TUO-UTENTE.github.io/lim-istituto-caso/`.
   - Passeggiata: `.../caso.html`
   - Halloween: `.../halloween.html`
   - Gestione LIM: `.../gestione.html`

## 4. Crea il token per il pannello (una volta sola)
1. Su GitHub: foto profilo → **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
2. Nome `gestione-lim`, scadenza a scelta (massimo 1 anno).
3. *Repository access*: **Only select repositories** → scegli `lim-istituto-caso`.
4. *Permissions → Repository permissions → Contents*: **Read and write**.
5. **Generate token** e copialo subito (inizia con `github_pat_`).

## 5. Usa il pannello
1. Apri `gestione.html` dal sito pubblicato.
2. Apri "Collegamento a GitHub", controlla utente e repository, incolla il token, premi **Salva collegamento** e **Prova il collegamento**.
3. Per ogni LIM scegli un'immagine e/o scrivi il sito, poi **Salva**.
4. Dopo circa un minuto le due passeggiate mostrano il cambiamento. Le passeggiate controllano le novità ogni minuto e quando torni sulla scheda.

## Note importanti
- Il token resta solo nel browser di chi lo inserisce. Chi lo ha può modificare il repository: non condividerlo. Se lo perdi, revocalo su GitHub e creane un altro.
- Il repository è pubblico: non caricare foto di studenti o materiale riservato.
- Le modifiche fatte toccando lo schermo dentro la passeggiata restano solo su quel dispositivo e vengono sostituite alla prossima modifica fatta dal pannello. Per tutti, usa `gestione.html`.
- Aprendo i file dal computer (doppio clic) la passeggiata funziona, ma non legge `lim-config.json`: serve il sito pubblicato.
- Altri hosting (Netlify, Cloudflare Pages) pubblicano senza problemi le pagine, ma il pannello salva solo su GitHub: se li usi, tieni comunque il repository su GitHub e collega l'hosting al repository.
