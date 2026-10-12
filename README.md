# ⚡ Trifitness
*(Precedentemente Metabolic Meal Planner)*

Applicazione web self-hosted, leggera e reattiva, progettata per il monitoraggio integrato della salute metabolica: pianificazione dei pasti familiari, generazione automatica della lista spesa per reparti, meal prep, tracciamento del peso con media mobile e bioimpedenza, e registro attività fisica con stima calorie per tapis roulant / walking pad.

Ideata per girare senza sforzo su home server Linux (Docker) con persistenza pura su file JSON (zero configurazioni complesse di database).

![Trifitness - Calendario Pasti Settimanale](docs/screenshots/01-calendario-pasti.png)

---

## 🚀 Caratteristiche Principali

### 1. 📅 Calendario Pasti (Piano Settimanale Unificato)
* **Piano Settimanale Unificato (7 Giorni):** Visualizzazione rotante compatta e priva di distrazioni, focalizzata sui 7 giorni successivi.
* **Allineamento Orizzontale Perfetto:** Le fasce orarie dei pasti sono allineate al pixel su tutti i giorni per una scansione visiva immediata:
  * ☕ **Colazione** (Tonalità ambra/alba)
  * 🥜 **Spuntino Mattina** (Tonalità lavanda delicato)
  * 🍝 **Pranzo 1 & Pranzo 2** (Tonalità verde mediterraneo)
  * 🍎 **Spuntino Pomeriggio** (Tonalità pesca/arancio)
  * 🍽️ **Cena 1 & Cena 2** (Tonalità blu notte rilassante)
* **Pulsante Ricetta Veloce (`📖`):** Ogni slot pasto ha un'icona diretta per aprire la scheda ricetta completa con le relative dosi ricalcolate.
* **⚡ Yazio 1-Click Quick Log (`+` verde):** Registrazione istantanea del pasto pianificato sul diario Yazio con un clic direttamente dallo slot, con fuzzy matching automatico con le proprie ricette su Yazio.

---

### 2. 🥗 Integrazione Yazio & Diario Nutrizionale
* **Dashboard Giornaliera Yazio:** Monitoraggio in tempo reale di calorie totali assunte, macronutrienti (carboidrati, proteine, grassi) e idratazione/acqua consumata.
* **1-Click Quick Log:** Registrazione con un solo tocco del pasto consumato; se la ricetta pianificata esiste già tra le ricette dell'utente su Yazio, viene registrata come porzione di ricetta.
* **Dettaglio Pasti & Rimozione Rapida:** Elenco chiaro degli alimenti registrati suddivisi per pasto con possibilità di eliminazione diretta da Trifitness.
* **Push Nutrizione su Intervals.icu:** Invio con un clic del totale calorico e dei macro del giorno da Yazio direttamente al profilo Wellness di Intervals.icu.

---

### 3. ⚡ Integrazione Smartwatch con Intervals.icu
* **Sincronizzazione Diretta Attività (Amazfit / Zepp / Garmin):** Importazione automatica o su richiesta degli allenamenti registrati dall'orologio tramite Intervals.icu API.
* **Calcolo Distanza Totale Giornaliera:** Calcolo intelligente che combina passi registrati dal contapassi e attività outdoor/tapis roulant in perfetta coerenza con il display dell'orologio.
* **Metriche Wellness:** Rilevamento automatico di passi giornalieri, calorie attive bruciate e frequenza cardiaca a riposo (RHR).
* **Import File Tracciati:** Supporto al drag & drop e caricamento batch di file fitness `.tcx`, `.gpx` e `.csv` per sessioni manuali o archivi storici.

---

### 4. 👥 Moltiplicatore Dinamico delle Porzioni & Ricettario
* Scheda di lettura dedicata per ciascun piatto con note metabolico-nutrizionali.
* **Stepper Interattivo `[-] [ X persone ] [+]`:** Permette di cucinare solo per 1 persona, per 2, per 3 o per l'intera famiglia.
* Tutte le grammature degli ingredienti si ricalcolano e si moltiplicano istantaneamente in tempo reale.
* **Ricettario Anti-Insulino-Resistenza:** Archivio con tempi di preparazione, filtri per portata, badge per basi congelabili/prep e ricerca per ingredienti usati.

![Scheda Ricetta con Moltiplicatore Porzioni](docs/screenshots/04-scheda-ricetta-porzioni.png)

![Ricettario Anti-Insulino-Resistenza](docs/screenshots/03-ricettario.png)

---

### 5. 🛒 Lista della Spesa Intelligente (Spesa della Domenica)
* **Calcolo Settimanale Dinamico:** Calcola la spesa per i 7 giorni del piano settimanale.
* **Raggruppamento e Somma Automatica:** Tutti gli ingredienti identici tra ricette diverse vengono aggregati e sommati in un'unica riga.
* **Suddivisione per Reparto del Supermercato:**
  * 🥬 *Ortofrutta*
  * 🥩 *Macellaio sotto casa*
  * 🧀 *Banco Frigo & Latticini*
  * ❄️ *Surgelati*
  * 🥫 *Dispensa, Scatolame & Secco*
  * 🍕 *Pizzeria / Forno*
* **Link Interattivi:** Ogni ingrediente mostra i badge cliccabili delle ricette in cui è utilizzato (*"Usato in: ..."*).
* **Ridenominazione Globale Ingredienti:** Modifica rapida del nome ingrediente con propagazione automatica su tutte le ricette correlate.
* **📲 Condivisione WhatsApp in 1 Clic:** Formatta l'intera lista della spesa divisa per reparti con emoji e la copia negli appunti pronta da incollare in chat.

![Lista della Spesa per Reparti del Supermercato](docs/screenshots/02-lista-spesa.png)

---

### 6. 🍳 Meal Prep Domenicale
* Rilevamento automatico e dinamico delle preparazioni da anticipare la domenica in base al piano pasti della settimana (cereali lessati, passati di verdura, uova sode, basi carne).
* Checkbox interattive per spuntare i compiti completati durante la sessione di preparazione.

![Meal Prep Domenicale & Freezer](docs/screenshots/05-meal-prep.png)

---

### 7. ⚖️ Monitoraggio Peso & Composizione Corporea
* **Tracciamento Peso & Media Mobile (7gg):** Algoritmo integrato che calcola la media mobile per smussare le fluttuazioni d'acqua e mostrare il reale andamento del dimagrimento.
* **Stima Tasso di Dimagrimento:** Calcolo automatico del ritmo settimanale (kg/settimana) con indicazione dello stato rispetto al target sano (0.5 - 1.0 kg/sett.).
* **Grafico SVG Interattivo:** Rappresentazione grafica vettoriale leggera e offline (zero CDN o librerie esterne) con griglia e tooltip dettagliati al passaggio del mouse.
* **Supporto Bioimpedenza & Misure:** Campi opzionali per % massa grassa, massa muscolare (kg), livello grasso viscerale, % idratazione, girovita e fianchi (cm).

![Monitoraggio Peso & Composizione Corporea](docs/screenshots/06-monitoraggio-peso.png)

---

### 8. 🏃 Attività Fisica & Walking Pad
* **Preset Rapidi in 1 Clic:** Pulsanti dedicati per sessioni standard (*15 min @ 3.5 km/h Post-Pranzo*, *20 min @ 4.0 km/h Stacco Serale*, *30 min @ 4.0 km/h Sessione Lunga*).
* **Stima Metabolica Automatica delle Calorie:** Calcolo energetico proporzionato in tempo reale al peso corporeo attuale e alla velocità media, con flag per disattivazione e inserimento manuale.
* **Barra di Avanzamento Obiettivo OMS:** Monitoraggio settimanale dei minuti di attività rispetto al target raccomandato di 150 minuti/settimana.
* **Integrazione Smartwatch:** Storico attività arricchito con battito cardiaco medio, calorie e distanza sincronizzati da Intervals.icu.

![Registro Attività Fisica & Walking Pad](docs/screenshots/07-attivita-fisica.png)

---

### 9. 🍳 Vista Cucina & Kiosk Tablet (`/kitchen`)
Interfaccia read-only dedicata a tablet da cucina e schermi a parete (`/kitchen`, `/cucina`, `/tablet`), ottimizzata per consultazione rapida e modalità stampa:
* **Vista Giornaliera (Oggi):** Tutti i pasti della giornata su una riga orizzontale pulita; ogni scheda riporta dosi e grammature già ricalcolate per il numero di porzioni del pasto, con supporto a piatti multipli raggruppati armoniosamente.
* **Vista Settimanale (Piano Settimanale):** Calendario a 7 giorni compatto e pulito, pronto per la stampa su carta tramite il pulsante rapido `🖨️ Stampa`.
* **Auto-Aggiornamento in Background:** Si sincronizza periodicamente per riflettere le modifiche apportate dal PC o dallo smartphone.

#### Pasti e Ingredienti del Giorno (Oggi)
![Vista Kiosk Cucina - Oggi](docs/screenshots/08-cucina-tablet-today.png)

#### Calendario Settimanale Compatto per Tablet / Stampa
![Vista Kiosk Cucina - Settimanale](docs/screenshots/09-cucina-tablet-week.png)

---

## 🐳 Avvio Rapido con Docker Compose

Il modo più semplice per eseguire l'applicazione è tramite Docker Compose (porta predefinita **9999**):

1. **Clona la repository:**
   ```bash
   git clone https://github.com/Trifase/trifitness.git
   cd trifitness
   ```

2. **Avvia il container:**
   ```bash
   docker compose up -d --build
   ```

3. **Apri il browser:**
   ```text
   http://localhost:9999
   # oppure http://<IP-DEL-TUO-SERVER>:9999
   ```

> **💾 Persistenza Dati:** La directory `./data/` è montata come volume all'interno del container. Qualsiasi modifica apportata tramite l'interfaccia web viene salvata direttamente nei file JSON locali (`data/recipes.json`, `data/plan.json`, `data/weight.json`, `data/activities.json`), rendendo backup e migrazioni facilissimi (`cp -r data/ backup/`).

---

## 💻 Esecuzione Locale (Senza Docker)

Requisiti: Python 3.10+

```bash
# Installa le dipendenze
pip install -r requirements.txt

# Avvia l'applicazione
python main.py
```

L'applicazione risponderà all'indirizzo `http://localhost:9999`.

---

## 🛠️ Stack Tecnologico

* **Backend:** [FastAPI](https://fastapi.tiangolo.com/) (Python) con [Uvicorn](https://www.uvicorn.org/).
* **Frontend:** Vanilla HTML5, CSS Grid / Flexbox moderno (senza framework pesanti, caricamento istantaneo).
* **Storage:** JSON File Store con Pydantic validation (portabile, versionabile, zero overhead).
* **Container:** Docker con immagine base `python:3.12-slim`.

---

## 📂 Struttura del Progetto

```text
trifitness/
├── data/
│   ├── recipes.json       # Database ricette con porzioni e ingredienti
│   ├── plan.json          # Stato del calendario dei pasti (settimana singola)
│   ├── weight.json        # Storico misurazioni peso e bioimpedenza
│   ├── activities.json    # Storico sessioni di attività fisica
│   ├── settings.json      # Configurazione API Intervals, Yazio e obiettivi
│   └── activity_presets.json # Preset personalizzati attività fisica
├── docs/
│   └── screenshots/       # Screenshot dell'interfaccia utente
├── scripts/
│   └── capture_screenshots.py # Script headless per rigenerare gli screenshot
├── static/
│   ├── index.html         # Interfaccia grafica SPA principale
│   ├── kitchen.html       # Vista read-only Kiosk per tablet da cucina
│   ├── style.css          # Design responsive e colori delle sezioni
│   └── app.js             # Logica frontend (moltiplicatore, slot, spesa)
├── Dockerfile             # Definizione container Docker
├── docker-compose.yml     # Configurazione Docker Compose (porta 9999)
├── main.py                # API backend FastAPI
├── requirements.txt       # Dipendenze Python
└── README.md              # Documentazione del progetto
```

---

## 📄 Licenza

Rilasciato sotto licenza [MIT](LICENSE). Libero da usare, modificare e distribuire per uso personale o homelab.
