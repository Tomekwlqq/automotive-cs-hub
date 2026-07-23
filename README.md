# Automotive CS Hub

Repozytorium Category Standards + Consumer Question Framework dla branży motoryzacyjnej.
Projekt: **Audi Plichta** — największy dealer Audi w Polsce (Trójmiasto + Bydgoszcz).

## Architektura CS (5 dokumentów)

| Slug | Segment | Status |
|---|---|---|
| `samochody_osobowe_prywatny` | CS-1: Nabywca prywatny (B2C, wszystkie marki) | ✅ v1.0 |
| `samochody_osobowe_leasing` | CS-2: Leasing prywatny CEP | 🔜 |
| `samochody_osobowe_biznes_jdg` | CS-3: Biznes/JDG | 🔜 |
| `samochody_elektryczne_ev` | CS-4: Elektryki (nowe vs chińskie) | 🔜 |
| `samochody_osobowe_zbiorczy` | CS-0: Benchmark kategoryjny | 🔜 |

## Renderowane widoki (GitHub Pages)

- [CS-1 Widok łączony — Nabywca Prywatny](https://tomekwlqq.github.io/automotive-cs-hub/docs/samochody_osobowe_prywatny_cs_mapa.html)
- [CS-1 Category Standard](https://tomekwlqq.github.io/automotive-cs-hub/docs/cs_samochody_osobowe_prywatny.html)
- [CS-1 Mapa Percepcji (79 pytań, 8 ścieżek)](https://tomekwlqq.github.io/automotive-cs-hub/docs/MAPA_PERCEPCJI_samochody_osobowe_prywatny_v5.5.html)

## Struktura repo

```
cs/
  {slug}/
    WPIS_CS_*_V2.md      -- źródło (16 sekcji)
    cs_v2_meta.json      -- meta (slug, CEPs, CDT, CDT disruption)
competitive/             -- analizy konkurencji z mapami percepcji
docs/                    -- rendered HTML (GitHub Pages)
```

## Źródła CS-1

- VW PHD Research (24 IDI, 2020)
- VW Customer Journey Updated
- VW DCJ qual+quant
- Audi-strateg werdykt 2026-07-23

---
*Metodologia: CS-CQF (Category Standards + Consumer Question Framework)*
