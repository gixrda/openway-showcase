# OpenWay · Freedom to move

![La parola OpenWay ritagliata sulla mappa di Pisa](assets/og-cover.png)

OpenWay è un prototipo per orientarsi in sedia a rotelle nella zona universitaria di Pisa, nato all'Hacktoberfest del GDG Pisa (ottobre 2026), dove si è classificato secondo come miglior progetto open source. Calcola un percorso, lo confronta con i dati di OpenStreetMap e con le segnalazioni degli utenti, e dice in chiaro cosa si sa, cosa è solo probabile e cosa manca. Non definisce mai un percorso «accessibile» o «sicuro».

- **Landing page:** https://gixrda.github.io/openway/
- **Codice dell'app e della landing:** https://github.com/gixrda/openway
- **Bozza del post LinkedIn:** [POST_LINKEDIN.md](POST_LINKEDIN.md)

Questo repository raccoglie immagini e testi per presentare il progetto. Il codice vive nel repository `openway`.

## La landing

| | |
|---|---|
| ![Apertura: il nome come finestra sulla mappa](assets/01-apertura.png) | ![Hero con ricerca, percorso e scheda](assets/02-hero.png) |
| L'apertura: la mappa reale di Pisa si vede attraverso le lettere. Scorrendo, il nome si apre e lascia spazio alla mappa. | La hero: ricerca, percorso di esempio con i punti di attenzione numerati, scheda con i limiti dei dati. |
| ![Le quattro funzioni in breve](assets/03-in-breve.png) | ![Come funziona, con le interfacce dell'app](assets/04-come-funziona.png) |
| In breve: quattro icone a goccia, una per funzione. | Come funziona: piccole interfacce ricostruite con i testi e gli stati veri dell'app. |
| ![Demo con i cinque tragitti](assets/05-demo.png) | ![Benefici](assets/06-benefici.png) |
| La demo: i cinque tragitti usati per presentare il progetto. | Più informazioni, meno incertezza. |
| ![Il progetto e i dati della zona](assets/07-progetto.png) | ![Chiusura](assets/08-chiusura.png) |
| Il progetto: dati OpenStreetMap della zona, tecnologie, cosa non fa ancora. | La chiusura. |

<p>
  <img src="assets/09-mobile-apertura.png" alt="Apertura su smartphone" width="260">
  <img src="assets/10-mobile-hero.png" alt="Hero su smartphone" width="260">
</p>

## The Living Line

<img src="assets/living-line.gif" alt="Una linea blu percorre via Roma a Pisa, si apre su due strade vicine e arriva a destinazione" width="336">

La linea della hero percorre la geometria reale del percorso. A un incrocio si aprono per un attimo le strade vicine, prese da OpenStreetMap, poi la linea arriva a destinazione e ricomincia. Le diramazioni sono solo animazione e la pagina lo dice. Se tocchi la mappa l'animazione si ferma; con «riduci movimento» attivo il percorso resta fermo.

## Come è fatta

- **Interfaccia:** React, Leaflet, GSAP e Motion; carattere Atkinson Hyperlegible Next.
- **Dati:** snapshot OpenStreetMap del 24/10/2026, 1158 elementi della zona universitaria.
- **Percorsi:** Valhalla con profilo per sedia a rotelle, OSRM come ripiego dichiarato.
- **Segnalazioni:** Gemma 4 legge la descrizione e fa una domanda; chi segnala conferma o corregge.
- **Voce:** dettatura e guida vocale con ElevenLabs.

La landing pubblicata su GitHub Pages è statica: i percorsi della demo sono registrati con la data. Quando sono stati registrati il servizio Valhalla non rispondeva, quindi la pagina mostra il percorso a piedi di ripiego e lo dichiara.

## Limiti dichiarati

- Copre solo la zona universitaria di Pisa.
- Nessun percorso è stato controllato di persona.
- Le segnalazioni restano «da controllare» finché un moderatore non le verifica.
- Usa servizi pubblici gratuiti, che possono essere lenti o non rispondere.

## Sicurezza

Le chiavi restano sul server e non sono nel repository; il sito pubblicato ha una Content Security Policy e parla solo con le tile di OpenStreetMap e con Nominatim. Dettagli e segnalazioni di vulnerabilità: [SECURITY.md del progetto](https://github.com/gixrda/openway/blob/main/SECURITY.md).

## Crediti

Mappe e dati © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright) (ODbL). Percorsi: Valhalla e OSRM (FOSSGIS e.V.). Ricerca: Nominatim. Carattere: Atkinson Hyperlegible Next (Braille Institute, OFL). Le immagini di questo repository sono schermate della landing.
