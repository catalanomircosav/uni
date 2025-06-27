# Specifiche Design – Reel Wheel
---
## 1. Palette Colori – “Atmosfera da Cinema”

| Colore           | Uso Principale                | Codice Hex |
| ---------------- | ----------------------------- | ---------- |
| Viola Profondo   | Sfondo, componenti principali | `#2C003E`  |
| Nero Grafite     | Background, testo secondario  | `#121212`  |
| Arancio Bruciato | CTA, Highlights, Hover        | `#FF6F3C`  |
| Ambra Calda      | Accenti, Badge, Grafici       | `#FFB74D`  |
| Bianco Neutro    | Testo, icone su sfondi scuri  | `#F5F5F5`  |

---
## 2. Mockup e Scelte UX – Descrizione per ciascuna pagina
### 🟣 Login / Registrazione
- Layout a doppia scheda con toggle fluido tra Login e Registrazione.
- Sfondo full-screen con immagine in bassa opacità (popcorn, pellicola).
- Form essenziale con icone inline.
- Pulsante “Continua con Google” colorato e coerente con branding.
- Logo “Reel Wheel” centrato con icona clapperboard animata al focus.

**Micro-interazioni:**
- Hover su “Continua con Google”: animazione lieve glow arancione.
- Toggle password: animazione di transizione occhio / icon-off.

---
### 🔶 Home Page
- Hero Section prominente con titolo: “La prossima serata cinema?”
- Due CTA principali:
  - Primario: “Crea nuova sessione” (colore ambra, hover → arancio vivo).
  - Secondario: “Unisciti a sessione” (bordo viola, riempimento on-hover).
- Sezione “Sessioni attive”:
  - Card dinamiche con carosello poster e badge partecipanti.
  - Bottone “Unisciti” con animazione lenta su hover.
- Footer con icone social in stile neon sottile.

---
### 📊 Dashboard Personale
- Sidebar con icone monocromatiche, attivate con effetto “highlight pellicola”.
- Grafici con colori tematici:
  - Barre arancio / ambra.
  - Doughnut con segmenti viola / nero.
- Lista film:
  - Card mini-poster con rating a stelle animate on-hover.
  - Differenza visiva tra voto personale e voto medio gruppo (barra divisa).
- Card statistiche rapide con mini-illustrazioni a tema (popcorn, clapper).

---
### 🎬 Dashboard Gruppo
- Header con avatar circolari e background sfocato del film selezionato.
- Sezione “Film della serata”:
  - Ruota interattiva con animazione spin (sound cinematografico opzionale).
  - Card film proposti con pulsante “Vota” che si illumina on-hover.
- Storico serate:
  - Timeline scorrevole con rating visivi.
  - Mini-avatar partecipanti.
- Chat laterale:
  - UI tipo “messenger dark mode”.
  - Indicatori presenza in tempo reale.

---
## 3. Nota sul Design Responsive
- Approccio **mobile-first** per ogni componente.
- Varianti per tablet e desktop definite.
- Menu hamburger su mobile con animazione a comparsa.
- Carosello swipeabile nella sezione “sessioni attive”.
- Bottoni grandi e facilmente cliccabili su mobile.

---
## 4. Annotazioni Visive (per mockup e immagini)
- Tooltip esplicativi su hover per descrivere micro-funzionalità.
- Etichette visibili nei mockup evidenziano:
  - Stati attivi / inattivi.
  - Comportamento su modalità dark vs. light.
  - Punti focali delle interazioni utente.
---