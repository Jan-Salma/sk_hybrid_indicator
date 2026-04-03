# Slovak Hybrid (VWAP, Multi MA) – JS VWAP/MA

Tento indikator som vytvoril ja, **Jan Salma** – mentor Akademie, specialne pre slovensky trh. Je navrhnuty tak, aby ho bolo mozne pouzivat aj na **bezplatnej verzii TradingView** a zaroven aby ostal priestor na pridanie dalsich vlastnych indikatorov.

> Coskoro pribudnu dalsie nastroje v jednom baliku.

---

## Changelog / Historia zmien

| Verzia | Datum | Zmeny |
|--------|-------|-------|
| **v1.2.0** | 2026-04-03 | Oprava kritickeho VWAP source bugu (ta.vwap property ignoroval source input — nahradeny spravnou ta.vwap() funkciou podla TV originalu). Pridany VWMA. Tri oddelene skupiny: MA → VWMA → VWAP. Source audit vsetkych komponentov. |
| **v1.1.0** | 2026-04-02 | VWAP Band s multiplikatorom (StdDev / Percentage). Source a Hide on 1D+ pre VWAP. Bilingvalne labels (SK/EN). Farba/hrubka presunutá do Style tab. |
| **v1.0.0** | 2025-08-29 | Zaklad: 4x Moving Average (EMA/SMA) + VWAP. |

---

## Funkcie a nastavenia

### 1. Moving Averages (MA)

- Az **4 klzave priemery** — kazdy sa da zapnut/vypnut
- Typ: **EMA** alebo **SMA**
- Nastavitelna dlzka periody a zdroj ceny (close, open, high, low, hlc3, atd.)
- Farba a hrubka ciary sa nastavuju v **Style tab**

**Predvolene nastavenia:**

| MA | Typ | Dlzka | Predvolena farba |
|----|-----|-------|-----------------|
| MA 1 | EMA | 20 | Oranzova |
| MA 2 | EMA | 50 | Modra |
| MA 3 | SMA | 100 | Fialova |
| MA 4 | SMA | 200 | Ruzova |

### 2. Volume Weighted Moving Average (VWMA) — v1.2+

- Zapni/vypni VWMA samostatne (predvolene vypnuty)
- Nastavitelna dlzka periody (predvolene 20)
- Nastavitelny zdroj ceny (predvolene close)
- Pouziva `ta.vwma()` — identicky s TV vestavanym VWMA indikatorom
- Farba a hrubka v **Style tab**

### 3. VWAP (Volume Weighted Average Price)

- Zapni/vypni
- Source — zdroj ceny (predvolene HLC3) — **funguje spravne pre vsetky zdroje**
- Hide on 1D+ — skryje VWAP na dennych a vyssich TF
- Implementacia zhodna s originalnym TradingView VWAP indikatorom
- Farba a hrubka v **Style tab**

### VWAP Band / Pas (v1.1+)

- Zapni/vypni multiplikacny pas okolo VWAP
- Nastavitelny multiplikator (predvolene 1.0, krok 0.5)
- Rezim: **Standard Deviation** alebo **Percentage**
- Farba a priehladnost v **Style tab**

---

## Technicke poznamky / Source Audit

| Komponent | Funkcia | Source input | Stav |
|-----------|---------|-------------|------|
| MA 1–4 | `ta.ema()` / `ta.sma()` | `input.source(close)` | OK |
| VWMA | `ta.vwma()` | `input.source(close)` | OK |
| VWAP | `ta.vwap(src, isNewPeriod, 1)` | `input.source(hlc3)` | OK (opravene v1.2) |

> **Bug v1.1:** `ta.vwap` property vzdy pouzivala `hlc3` bez ohladu na nastaveny source. Opravene v **v1.2.0** — VWAP teraz pouziva `ta.vwap()` funkciu presne podla TV VWAP originalu.

---

## Vyhody

- Bilingvalne nastavenia **(SK/EN)**
- Inputs tab je cisty — len logika, farby v Style tab
- VWAP implementacia zhodna s TV VWAP (overena)
- Kombinuje viacero nastrojov do jedneho — setri miesto v grafe

---

## Pouzitie

1. Skopiruj kod zo suboru `sk_hybrid_indicator.pine`
2. V TradingView otvor **Pine Editor**
3. Vloz kod a klikni na **Pridat do grafu**
4. Inputs tab — nastav typy, dlzky, zdroje; zapni VWMA / Band podla potreby
5. Style tab — uprav farby a hrubky podla svojho stylu

---

# Slovak Hybrid (VWAP, Multi MA) – JS VWAP/MA (EN)

This indicator was created by **Jan Salma** – mentor of the Slovak Academy, especially for the Slovak market. Designed for the **free version of TradingView**.

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| **v1.2.0** | 2026-04-03 | Critical VWAP source bug fix (ta.vwap property ignored source input — replaced with ta.vwap() function matching TV original). Added VWMA. Three separate groups: MA → VWMA → VWAP. Source audit of all components. |
| **v1.1.0** | 2026-04-02 | VWAP Band with multiplier (StdDev / Percentage). Source & Hide on 1D+ for VWAP. Bilingual labels (SK/EN). Color/width moved to Style tab. |
| **v1.0.0** | 2025-08-29 | Initial: 4x Moving Average (EMA/SMA) + VWAP. |

## Features

### 1. Moving Averages (MA)
- Up to **4 MAs** — each toggleable individually
- Type: **EMA** or **SMA**, adjustable length and source
- Color & width in **Style tab**

### 2. Volume Weighted Moving Average (VWMA) — v1.2+
- Toggleable (off by default)
- Adjustable length (default 20) and source (default close)
- Uses `ta.vwma()` — identical to TradingView built-in VWMA
- Color & width in **Style tab**

### 3. VWAP
- Toggleable, source input (default HLC3) — **works correctly for all sources**
- Hide on 1D+ option
- Implementation matches original TradingView VWAP exactly
- Color & width in **Style tab**

### VWAP Band (v1.1+)
- Toggleable band around VWAP
- Adjustable multiplier (default 1.0), mode: Standard Deviation or Percentage
- Color & transparency in **Style tab**

## Source Audit

| Component | Function | Source input | Status |
|-----------|----------|-------------|--------|
| MA 1–4 | `ta.ema()` / `ta.sma()` | `input.source(close)` | OK |
| VWMA | `ta.vwma()` | `input.source(close)` | OK |
| VWAP | `ta.vwap(src, isNewPeriod, 1)` | `input.source(hlc3)` | OK (fixed v1.2) |

---

A clean, flexible indicator combining multiple tools in one — efficiency and clarity for every trader.
