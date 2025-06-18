---
campaign: EOS - l'Eredita' Perduta
tags:
  - campaign-hub
  - rules
---
---
## 🔮 **Panoramica della Campagna**
- **Trama Principale**: Gli dei sono stati sconfitti da un'entità ancora sconosciuta.  Riusciranno i giocatori a reclamare ciò che li spetta di diritto?
- **Stato Attuale**: [[Sessione 3 - Il Corvo e il Segreto del Cataclisma]]
- **Link Utili**:
  - [[Regole Homebrew]]
  - [[Pantheon degli Dei]]
---
### 🏰 **Luoghi Chiave**
[[Locanda del Drago Nero]]
[[Grimerfell]]
___
### 👥 **NPC**
```dataview
TABLE WITHOUT ID
  file.link AS "Nome",
  race AS "Razza",
  occupation AS "Ruolo",
  alignment AS "Allineamento"
FROM "NPCs" AND #npc 
SORT file.name
```
___
### 🎯 **Quest Attive**
[[Sessione 4 -]]
___
### ⚔️ **Fazioni & Organizzazioni**
```dataview
TABLE WITHOUT ID
  file.link AS "Fazione",
  alignment AS "Allineamento",
  influence AS "Influenza"
FROM #faction 
SORT influence DESC
```
___
### 🧰 **Oggetti Rilevanti**
```dataview
TABLE WITHOUT ID
  file.link AS "Oggetto",
  rarity AS "Rarità",
  owner AS "Possessore"
FROM "Items" AND #item 
SORT rarity
```
___
### 📅 **Sessioni Recenti**
```dataview
TABLE WITHOUT ID
  file.link AS "Sessione",
  date AS "Data"
FROM "Sessioni"
SORT date DESC
LIMIT 3
```
___