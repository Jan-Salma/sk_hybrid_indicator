# Slovak Hybrid (VWAP, Multi MA) – JS VWAP/MA

Tento indikator som vytvoril ja, **Jan Salma** – mentor Akademie, specialne pre slovensky trh. Je navrhnuty tak, aby ho bolo mozne pouzivat aj na **bezplatnej verzii TradingView** a zaroven aby ostal priestor na pridanie dalsich vlastnych indikatorov.

> Coskoro pribudnu dalsie nastroje v jednom baliku.

---

## Changelog / Historia zmien

| Verzia | Datum | Zmeny |
|--------|-------|-------|
| **v1.1.0** | 2026-04-02 | VWAP Band s multiplikatorom (StdDev / Percentage). Source a Hide on 1D+ pre VWAP. Bilingvalne labels (SK/EN). Farba/hrubka presunutá do Style tab. Oprava VWAP ciary (ta.vwap property = zhodna s TV VWAP). Oprava fill() CE10123. |
| **v1.0.0** | 2025-08-29 | Zaklad: 4x Moving Average (EMA/SMA) + VWAP. |

---

## Funkcie a nastavenia

### Moving Averages (MA)

- Az **4 klzave priemery** — kazdy sa da zapnut/vypnut
- Typ: **EMA** alebo **SMA**
- Nastavitelna dlzka periody a zdroj ceny
- Farba a hrubka ciary sa nastavuju v **Style tab**

**Predvolene nastavenia:**

| MA | Typ | Dlzka | Predvolena farba |
|----|-----|-------|-----------------|
| MA 1 | EMA | 20 | Oranzova |
| MA 2 | EMA | 50 | Modra |
| MA 3 | SMA | 100 | Fialova |
| MA 4 | SMA | 200 | Ruzova |

### VWAP (Volume Weighted Average Price)

- Zapni/vypni
- Source (predvolene HLC3) — zhodny s TV vestanym VWAP
- Hide on 1D+ — skryje VWAP na dennych a vyssich TF
- Farba a hrubka v **Style tab**

### VWAP Band / Pas (v1.1+)

- Zapni/vypni multiplikacny pas okolo VWAP
- Nastavitelny multiplikator (predvolene 1.0, krok 0.5)
- Rezim: **Standard Deviation** alebo **Percentage**
- Farba a priehladnost v **Style tab**

---

## Vyhody

- Bilingvalne nastavenia **(SK/EN)**
- Inputs tab je cisty — len logika, farby v Style tab
- VWAP ciara je identická s vestavanym TradingView VWAP
- Kombinuje viacero nastrojov do jedneho — setri miesto v grafe

---

## Pouzitie

1. Skopiruj kod zo suboru `sk_hybrid_indicator.pine`
2. V TradingView otvor **Pine Editor**
3. Vloz kod a klikni na **Pridat do grafu**
4. Inputs tab — nastav typy a dlzky MA, zapni VWAP/Band
5. Style tab — uprav farby a hrubky podla svojho stylu

---

# Slovak Hybrid (VWAP, Multi MA) – JS VWAP/MA (EN)

This indicator was created by **Jan Salma** – mentor of the Slovak Academy, especially for the Slovak market. Designed for the **free version of TradingView**.

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| **v1.1.0** | 2026-04-02 | VWAP Band with multiplier (StdDev / Percentage). Source & Hide on 1D+ for VWAP. Bilingual labels (SK/EN). Color/width moved to Style tab. Fix: VWAP uses ta.vwap property (matches TV VWAP). Fix: fill() CE10123 error. |
| **v1.0.0** | 2025-08-29 | Initial: 4x Moving Average (EMA/SMA) + VWAP. |

## Features

### Moving Averages (MA)
- Up to **4 MAs** — each toggleable individually
- Type: **EMA** or **SMA**, adjustable length and source
- Color & width in **Style tab**

### VWAP
- Toggleable, source input (default HLC3)
- Hide on 1D+ option
- Identical to TradingView built-in VWAP
- Color & width in **Style tab**

### VWAP Band (v1.1+)
- Toggleable band around VWAP
- Adjustable multiplier (default 1.0)
- Mode: **Standard Deviation** or **Percentage**
- Color & transparency in **Style tab**

---

A clean, flexible indicator combining multiple tools in one — efficiency and clarity for every trader.
