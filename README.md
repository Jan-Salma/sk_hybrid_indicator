# Slovak Hybrid (VWAP, Multi MA) – JS VWAP/MA

This indicator was created by **Ján Salma** – mentor of the Slovak Academy, especially for the Slovak market. Designed to work on the **free version of TradingView**, while keeping space for additional indicators on your chart.

> More tools combined in one package coming soon.

🌐 [jan-salma.com](https://jan-salma.com)

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| **v1.2.0** | 2026-04-03 | Critical VWAP source bug fix — `ta.vwap` property ignored source input, replaced with `ta.vwap()` function matching TV original. Added VWMA. Three separate groups: MA → VWMA → VWAP. Source audit of all components. |
| **v1.1.0** | 2026-04-02 | VWAP Band with multiplier (StdDev / Percentage). Source & Hide on 1D+ for VWAP. Bilingual labels (SK/EN). Color/width moved to Style tab. |
| **v1.0.0** | 2025-08-29 | Initial: 4x Moving Average (EMA/SMA) + VWAP. |

---

## Features

### 1. Moving Averages (MA)

- Up to **4 moving averages** — each toggleable individually
- Type: **EMA** or **SMA**
- Adjustable length and source (Close, Open, High, Low, HLC3, etc.)
- Color & width in **Style tab**

**Default settings:**

| MA | Type | Length | Default color |
|----|------|--------|---------------|
| MA 1 | EMA | 20 | Orange |
| MA 2 | EMA | 50 | Blue |
| MA 3 | SMA | 100 | Purple |
| MA 4 | SMA | 200 | Pink |

### 2. Volume Weighted Moving Average (VWMA) — v1.2+

- Toggleable independently (off by default)
- Adjustable length (default 20) and source (default close)
- Uses `ta.vwma()` — identical to TradingView built-in VWMA
- Color & width in **Style tab**

### 3. VWAP (Volume Weighted Average Price)

- Toggleable
- Source input (default HLC3) — **works correctly for all sources** (fixed v1.2)
- Hide on 1D+ — hides VWAP on daily and higher timeframes
- Implementation matches original TradingView VWAP exactly
- Color & width in **Style tab**

### VWAP Band (v1.1+)

- Toggleable band around VWAP
- Adjustable multiplier (default 1.0, step 0.5)
- Mode: **Standard Deviation** or **Percentage**
- Color & transparency in **Style tab**

---

## Source Audit

| Component | Function | Source input | Status |
|-----------|----------|-------------|--------|
| MA 1–4 | `ta.ema()` / `ta.sma()` | `input.source(close)` | ✅ OK |
| VWMA | `ta.vwma()` | `input.source(close)` | ✅ OK |
| VWAP | `ta.vwap(src, isNewPeriod, 1)` | `input.source(hlc3)` | ✅ Fixed v1.2 |

> **Bug in v1.1:** `ta.vwap` property always used `hlc3` regardless of the source setting. Fixed in **v1.2.0** — VWAP now uses `ta.vwap()` function matching the original TV VWAP indicator exactly.

---

## Benefits

- Bilingual settings **(SK/EN)** — clear for everyone
- Clean Inputs tab — logic only, colors in Style tab
- VWAP implementation verified against TV original
- Combines multiple tools into one — saves chart space

---

## How to use

1. Copy the code from `sk_hybrid_indicator.pine`
2. Open **Pine Editor** in TradingView
3. Paste the code and click **Add to chart**
4. Inputs tab — set types, lengths, sources; enable VWMA / Band as needed
5. Style tab — adjust colors and widths to your trading style

---

---

# Slovak Hybrid (VWAP, Multi MA) – JS VWAP/MA

Tento indikátor som vytvoril ja, **Ján Salma** – mentor Akadémie, špeciálne pre slovenský trh. Je navrhnutý tak, aby ho bolo možné používať aj na **bezplatnej verzii TradingView** a zároveň aby ostal priestor na pridanie ďalších vlastných indikátorov.

> Čoskoro pribudnú ďalšie nástroje v jednom balíku.

🌐 [jan-salma.com](https://jan-salma.com)

---

## Changelog / História zmien

| Verzia | Dátum | Zmeny |
|--------|-------|-------|
| **v1.2.0** | 2026-04-03 | Oprava kritického VWAP source bugu — `ta.vwap` property ignoroval source input, nahradený správnou `ta.vwap()` funkciou podľa TV originálu. Pridaný VWMA. Tri oddelené skupiny: MA → VWMA → VWAP. Source audit všetkých komponentov. |
| **v1.1.0** | 2026-04-02 | VWAP Band s multiplikátorom (StdDev / Percentage). Source a Hide on 1D+ pre VWAP. Bilingválne labels (SK/EN). Farba/hrúbka presunutá do Style tab. |
| **v1.0.0** | 2025-08-29 | Základ: 4x Moving Average (EMA/SMA) + VWAP. |

---

## Funkcie a nastavenia

### 1. Moving Averages (MA)

- Až **4 kĺzavé priemery** — každý sa dá zapnúť/vypnúť
- Typ: **EMA** alebo **SMA**
- Nastaviteľná dĺžka periódy a zdroj ceny (close, open, high, low, hlc3 atď.)
- Farba a hrúbka čiary sa nastavujú v **Style tab**

**Predvolené nastavenia:**

| MA | Typ | Dĺžka | Predvolená farba |
|----|-----|-------|-----------------|
| MA 1 | EMA | 20 | Oranžová |
| MA 2 | EMA | 50 | Modrá |
| MA 3 | SMA | 100 | Fialová |
| MA 4 | SMA | 200 | Ružová |

### 2. Volume Weighted Moving Average (VWMA) — v1.2+

- Zapni/vypni VWMA samostatne (predvolene vypnutý)
- Nastaviteľná dĺžka periódy (predvolene 20)
- Nastaviteľný zdroj ceny (predvolene close)
- Používa `ta.vwma()` — identický s TV vstavaným VWMA indikátorom
- Farba a hrúbka v **Style tab**

### 3. VWAP (Volume Weighted Average Price)

- Zapni/vypni
- Source — zdroj ceny (predvolene HLC3) — **funguje správne pre všetky zdroje** (opravené v1.2)
- Hide on 1D+ — skryje VWAP na denných a vyšších TF
- Implementácia zhodná s originálnym TradingView VWAP indikátorom
- Farba a hrúbka v **Style tab**

### VWAP Band / Pás (v1.1+)

- Zapni/vypni multiplikačný pás okolo VWAP
- Nastaviteľný multiplikátor (predvolene 1.0, krok 0.5)
- Režim: **Standard Deviation** alebo **Percentage**
- Farba a priehľadnosť v **Style tab**

---

## Technické poznámky / Source Audit

| Komponent | Funkcia | Source input | Stav |
|-----------|---------|-------------|------|
| MA 1–4 | `ta.ema()` / `ta.sma()` | `input.source(close)` | ✅ OK |
| VWMA | `ta.vwma()` | `input.source(close)` | ✅ OK |
| VWAP | `ta.vwap(src, isNewPeriod, 1)` | `input.source(hlc3)` | ✅ Opravené v1.2 |

> **Bug v1.1:** `ta.vwap` property vždy používala `hlc3` bez ohľadu na nastavený source. Opravené vo **v1.2.0** — VWAP teraz používa `ta.vwap()` funkciu presne podľa TV VWAP originálu.

---

## Výhody

- Bilingválne nastavenia **(SK/EN)**
- Inputs tab je čistý — len logika, farby v Style tab
- VWAP implementácia zhodná s TV VWAP (overená)
- Kombinuje viacero nástrojov do jedného — šetrí miesto v grafe

---

## Použitie

1. Skopíruj kód zo súboru `sk_hybrid_indicator.pine`
2. V TradingView otvor **Pine Editor**
3. Vlož kód a klikni na **Pridať do grafu**
4. Inputs tab — nastav typy, dĺžky, zdroje; zapni VWMA / Band podľa potreby
5. Style tab — uprav farby a hrúbky podľa svojho štýlu

---

## Chceš vedieť, ako používať indikátory správne?

Nauč sa to v mojom kurze:

👉 **[Forex od základov bez chaosu](https://www.jan-salma.com/kurzy/forex-od-zakladov-bez-chaosu/)** — kompletný kurz pre slovenských traderov, kde sa naučíš čítať graf, pracovať s indikátormi a obchodovať bez zbytočného chaosu.

✅ Čistý, flexibilný indikátor pre každého tradera, ktorý chce efektívnosť a prehľadnosť v grafe.
