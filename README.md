# WHALETRACE BIST Tracker — FinTech Analytics Case Study

> **Notice:** This repository is an **Architectural Case Study & Engineering Showcase**. Live market trading scripts remain private.

---

## 🏛️ Executive Summary

**WHALETRACE BIST Tracker** is a specialized FinTech monitoring system designed to track high-volume transactions ("whale moves") on the Istanbul Stock Exchange (BIST) in real-time, detecting unusual volume spikes and rapid price swings.

---

## ⚡ Key Engineering & Algorithmic Achievements

- **Real-Time BIST Data Ingestion:** Fast polling engine monitoring ceiling/floor price changes, order book imbalance, and high-volume transactions.
- **Whale Transaction Classifier:** Algorithmic filter isolating institutional-grade trade orders from retail noise.
- **Telegram Notification Bridge:** Telethon microservice dispatching instant alerts to subscribers upon detecting volume spikes.

---

## 📐 System Architecture

```
   ┌────────────────────────────────────────────────────────┐
   │               BIST Live Market Data Stream             │
   └───────────────────────────┬────────────────────────────┘
                               │
                               ▼
   ┌────────────────────────────────────────────────────────┐
   │           Whale Volume Detection & Classifier          │
   └───────┬───────────────────┬────────────────────┬───────┘
           │                   │                    │
           ▼                   ▼                    ▼
  ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
  │ Ceiling/Floor   │ │ Imbalance Calc  │ │ SQLite Log      │
  │ Monitor         │ │ (Orderbook Spike│ │ (Tick History)  │
  └────────┬────────┘ └────────┬────────┘ └─────────────────┘
           │                   │
           └───────────────────┼────────────────────┐
                               ▼                    ▼
                   ┌──────────────────────┐ ┌──────────────┐
                   │ Telegram Alert Bot   │ │ REST API UI  │
                   └──────────────────────┘ └──────────────┘
```

---

## 📊 Technical Performance Benchmarks

| Metric | Benchmark Value |
|--------|-----------------|
| **Tick Processing Speed** | < 15 ms |
| **Monitored BIST Equities** | 500+ Stocks |

---

## 🛠️ Tech Stack & Tooling

- **Backend:** Python 3.12, FastAPI, SQLite3
- **Bot Engine:** Telethon, Telegram Bot API
- **Containerization:** Docker, Docker Compose

---
*Architected and engineered by **Enes Teke (tekedev)**.*
