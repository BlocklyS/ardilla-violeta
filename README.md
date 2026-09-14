# 🐿️💜 Ardilla Violeta – Geospatial Jobs & Tools Hub

> Hub indipendente di riferimento per opportunità lavorative, bandi, risorse e strumenti per la community GIS, geospaziale e dei geodati in Italia.

Ideato, sviluppato e curato da Sonia Mereu.

---

## 🎯 Obiettivo del Progetto

Il settore geospaziale (GIS, telerilevamento, geologia tecnica, analisi territoriale) soffre spesso di un'eccessiva dispersione delle offerte di lavoro su bacheche
generaliste o portali della Pubblica Amministrazione di difficile navigazione. 

**Ardilla Violeta** nasce per:
- Centralizzare annunci e bandi pubblici specifici per profili geo (GIS Analyst, WebGIS Developer, Geologi, EO Specialist).
- Offrire una **visualizzazione cartografica interattiva** delle opportunità su scala nazionale.
- Mantenere un'architettura leggera, priva di backend complessi o database a pagamento, massimizzando sostenibilità ed efficienza.

---

## 🛠️ Stack Tecnologico & Architettura

Il progetto adotta un'architettura **Jamstack serverless**, semplice e resiliente:

* **Frontend:** HTML5 semantico, CSS3 / [Tailwind CSS CDN](https://tailwindcss.com/), JavaScript (ES6+ Vanilla).
* **Mappatura WebGIS:** [Leaflet.js](https://leafletjs.com/) integrato con [Leaflet.markercluster](https://github.com/Leaflet/Leaflet.markercluster) per raggruppare visivamente le posizioni con coordinate coincidenti o ad alta densità.
* **Database & CMS Headless:** Google Sheets (gestito come database tabellare, esportato e consumato come CSV dinamico via API pubblica).
* **Geocoding:** Script personalizzato in **Google Apps Script** che converte le località testuali in coordinate (`lat`, `lon`) direttamente all'inserimento della riga.
* **Hosting & CI/CD:** Repository su **GitHub** collegata in Continuous Deployment a **Netlify** (ogni `git push` attiva una nuova build automatica in produzione).
* **Privacy-friendly Analytics:** [Umami Analytics](https://umami.is/).

---

## 🗺️ Struttura Dati (Jobs Database)

La bacheca viene alimentata da un Google Sheet strutturato sulle seguenti 11 colonne:

| Colonna | Descrizione | Note / Automazione |
| :--- | :--- | :--- |
| `title` | Ruolo professionale | Obbligatorio |
| `company` | Azienda, Ente o Istituto | Obbligatorio |
| `location` | Città / Modalità (Presenza, Ibrido, Remoto) | Testo usato per il geocoding |
| `contract_type` | Full-Time, Partita IVA, Bando PA, ecc. | Utilizzato per i filtri rapidi |
| `description` | Sintesi tecnica dei compiti | Breve abstract |
| `tags` | Skill (#QGIS, #Python, #LiDAR, ecc.) | Normalizzati e renderizzati come badge |
| `apply_url` | Link diretto alla candidatura o bando | Redirect esterno |
| `date_posted` | Data di pubblicazione | Formato ISO (`YYYY-MM-DD`) |
| `badge` | Etichetta visiva | Es. *Junior*, *Bando PA*, *In evidenza* |
| `lat` | Latitudine WGS84 | Calcolata via Apps Script |
| `lon` | Longitudine WGS84 | Calcolata via Apps Script |

---

## 🤖 Trasparenza sull'uso dell'Intelligenza Artificiale

In linea con i principi di apertura ed etica del progetto, si dichiara che lo sviluppo di **Ardilla Violeta** è supportato da strumenti di intelligenza artificiale generativa (LLM quali Google Antigravity e Gemini).

L'AI è stata impiegata come assistente tecnico per:
- Refactoring e modularizzazione del codice JavaScript/HTML.
- Scrittura e ottimizzazione della logica di clustering Leaflet e del parsing CSV.
- Stesura di routine in Google Apps Script per la geocodifica.

La selezione dei dati, la direzione editoriale, la validazione del codice e la cura delle offerte rimangono sotto il **controllo umano diretto**.

---

## 🚀 Come contribuire o segnalare un'offerta

Hai un'offerta di lavoro da pubblicare, un bando da segnalare o vuoi suggerire un nuovo tool GIS per la directory?

- 💼 Contattami su [LinkedIn](www.linkedin.com/in/sonia-mereu)
- 🛠️ Apri una **Issue** o una **Pull Request** per bugfix o miglioramenti del codice.

---

## 📄 Licenza e Termini d'Uso

Questo progetto adotta una gestione differenziata tra codice sorgente e contenuti:

* **Codice Sorgente (Open Source):** Il codice tecnico di questo repository (HTML, CSS, JavaScript, logiche Leaflet e script di integrazione) è liberamente consultabile,
  utilizzabile e modificabile sotto licenza **MIT**. Puoi prenderlo a riferimento o riutilizzarlo per i tuoi progetti.
* **Marchio, Logo e Contenuti (Riservati):** Il nome *Ardilla Violeta*, il logo, la grafica originale, l'identità del brand e i testi redazionali/curatela del catalogo rimangono sotto **Tutti i diritti riservati (All Rights Reserved)** e non possono essere replicati o utilizzati a fini commerciali senza preventiva autorizzazione.
