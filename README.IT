# Sales & Shipments Overview Dashboard

## Descrizione del progetto
Questo progetto implementa una soluzione di Business Intelligence che copre il ciclo **Order → Shipment → Delivery**, partendo da dati grezzi in formato CSV fino alla visualizzazione finale in **Power BI**.

La soluzione include le principali fasi tipiche di un contesto BI:
- ingestione dei dati
- trasformazione e consolidamento
- modellazione dimensionale
- analisi tramite dashboard e KPI

Il progetto è strutturato come un caso realistico di integrazione tra area commerciale e logistica.

---

## Architettura della soluzione

CSV Files  
↓  
Apache Hop (ETL & Workflow)  
↓  
RAW Layer (SQL Server)  
↓  
STAGING Layer  
↓  
DATA WAREHOUSE (Star Schema)  
↓  
Power BI Dashboard

---

## ETL e Orchestrazione

**Tool utilizzato:** Apache Hop

### Funzionalità implementate
- Pipeline dedicate per:
  - Customers
  - Orders
  - Order Lines
  - Shipments
  - Products
- Workflow di orchestrazione che:
  - coordina i caricamenti dei dati RAW
  - esegue controlli di audit
  - avvia il caricamento delle tabelle STAGING e DWH
- Gestione dei metadati di caricamento:
  - Load Date (`load_dt`)
  - Run ID
  - Ingestion Timestamp
  - Source File
- Supporto a ricaricamenti e reprocessing dei dati

---

## Data Warehouse

### Modello
**Star Schema**

### Dimensioni
- `DW.DIM_DATE`
- `DW.DIM_CUSTOMER`
- `DW.DIM_PRODUCT`
- `DW.DIM_CARRIER`

### Tabelle dei fatti
- `DW.FACT_SALES`
- `DW.FACT_SHIPPING`

Le fact sono modellate in modo indipendente e collegate tramite dimensioni conformi, secondo le best practice di modellazione dimensionale.

---

## Dashboard e KPI (Power BI)

### Dashboard principale
**Sales & Shipments Overview Dashboard**

### KPI disponibili
- Total Sales
- Total Orders
- On-Time Delivery Rate (%)
- Outstanding Orders
- Shipments by Carrier
- Delivery Performance Trend (Year-Month)

### Tabelle operative
Shipment Delivery Status:
- Shipment ID
- Order ID
- Carrier
- Shipment Date
- Expected Delivery Date
- Delivered Date
- Delivery Days
- On-Time Flag
- Delivery Status

La tabella utilizza formattazione condizionale per evidenziare ritardi e criticità operative.

---

## Obiettivi di analisi
- Monitorare l’andamento delle vendite
- Analizzare le performance di spedizione e consegna
- Individuare ordini in ritardo o non ancora consegnati
- Supportare analisi operative e di controllo

---

## Tecnologie utilizzate
- Apache Hop
- SQL Server
- Power BI
- GitHub
