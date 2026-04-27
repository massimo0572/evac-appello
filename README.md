# EVAC — Sistema Appello Evacuazione

App web per la gestione dell'appello durante le prove di evacuazione aziendale.  
Funziona interamente nel browser, con database condiviso su GitHub.

## 🚀 Come pubblicare su GitHub Pages

### 1. Carica i file nel repository

Carica questi file nella root del repository:
- `index.html` — l'applicazione principale
- `db.json` — il database delle presenze

### 2. Abilita GitHub Pages

- Vai su **Settings → Pages**
- Source: **Deploy from a branch**
- Branch: **main** / root
- Clicca **Save**

Dopo 1-2 minuti l'app sarà disponibile su:  
`https://TUO-USERNAME.github.io/NOME-REPO/`

### 3. Configura il database alla prima apertura

All'apertura apparirà una finestra di configurazione. Inserisci:

1. **Username GitHub** — il tuo username
2. **Nome Repository** — il nome di questo repo
3. **Personal Access Token** — genera su [GitHub → Settings → Developer Settings → Tokens (classic)](https://github.com/settings/tokens/new), seleziona scope `repo`

La configurazione viene salvata nel browser e non serve reinserirla.

---

## 🔄 Come funziona il database

- Le presenze vengono salvate nel file `db.json` tramite **GitHub API**
- Tutti i dispositivi connessi si sincronizzano automaticamente ogni **5 secondi**
- Le modifiche di altri utenti appaiono con un **flash colorato** sulla riga aggiornata
- Il badge **LIVE** in alto indica che la sincronizzazione è attiva

## 📋 Funzionalità

- ✅ Toggle presenza per ogni dipendente
- 🔍 Ricerca per nome
- 🔎 Filtri: Tutti / Presenti / Assenti
- 📊 Dashboard con statistiche live
- 📂 Caricamento lista da file Excel (.xlsx)
- 🖨️ Stampa verbale evacuazione
- 🔄 Reset appello
- 💾 Database condiviso su GitHub (sincronizzazione multi-dispositivo)

## 📁 Struttura file

```
evac-app/
├── index.html   ← applicazione web
└── db.json      ← database presenze (aggiornato automaticamente)
```

## 🔐 Sicurezza

Il Personal Access Token viene salvato solo nel `localStorage` del browser e non viene mai inviato a server terzi — solo alle API ufficiali di GitHub (`api.github.com`).

Si consiglia di creare un token con **scadenza** (es. 90 giorni) e scope limitato a `repo`.
