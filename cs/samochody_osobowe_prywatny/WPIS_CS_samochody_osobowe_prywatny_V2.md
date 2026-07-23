# Samochody osobowe — nabywca prywatny — CS v1.0

*Źródła: VW PHD Research 24 IDI (2020) + VW Customer Journey Updated + VW DCJ + audi-strateg werdykt 2026-07-23. CS-1 z 5 automotive CS-ów.*

## 0. Opis kategorii
Samochód osobowy to pojazd dla osób prywatnych do użytku osobistego/rodzinnego. Cena PLN 60k–400k+. Cykl decyzji 2–6 mies. Kluczowe zakłócenie: chińskie EV (BYD, MG, OMODA) 90–140k PLN vs europejskie premium.

## 1. CEV
| ryzyko | lęk | widoczność | impuls | sexy | aspiracja | tożsamość | zmysłowość | pilność | moralność |
|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| .70 | .55 | .65 | .10 | .60 | .65 | .55 | .50 | .40 | .25 |

## 2. CEP (8 punktów wejścia)
| id | Trigger | Typ | Bloker | Routes to |
|---|---|---|---|---|
| cep_awaria_frustracja | Stary auto się psuje i kosztuje | POTRZEBA | nowe vs używane | nowe z gwarancją lub CPO |
| cep_zmiana_zyciowa | Dziecko / nowa praca / rozstanie | POTRZEBA | który model | segment per sytuacja |
| cep_leasing_odkrycie | Nowe za ratę jak czynsz | EMOCJA | brak wiedzy o leasingu | mid-range leasing 48–60 mies. |
| cep_koszty_eksploatacji | Stare auto za droże | POTRZEBA | TCO payback | hybryda / mild hybrid |
| cep_self_gift_awans | Nagroda dla siebie | EMOCJA | cena premium vs wartość | segment premium |
| cep_elektryk_ciekawostka | Chińskie EV taniej i lepiej wyposażone | EMOCJA | chińskie vs europejskie | premium EV vs chiński EV |
| cep_koniec_leasingu | Kończy mi się umowa | POTRZEBA | wartość rezydualna | nowy leasing |
| cep_pierwsze_auto | Świeży kierowca | POTRZEBA | nowe vs używane | small segment CPO |

## 3. Discovery Questions (24)
1. Nowy czy używany samochód — co wybrać w 2026?
2. Jak długo czeka się na nowy samochód z salonu?
3. Leasing prywatny na samochód — jak działa? Czy warto?
4. Ile wynosi rata leasingowa na nowe auto 2026?
5. Co sprawdzić przed zakupem używanego samochodu?
6. Samochód elektryczny czy spalinowy — co wybrać w Polsce 2026?
7. Czy chińskie samochody elektryczne są bezpieczne / godne zaufania?
8. BYD vs Audi / BMW — co wybrać?
9. Ile kosztuje utrzymanie samochodu miesięcznie?
10. Jakie auto dla rodziny z dziećmi 2026?
11. Samochód do 100 000 / 150 000 / 200 000 PLN — co najlepszego?
12. Jak negocjować cenę samochodu w salonie?
13. Czy warto kupować samochód na koniec roku?
14. Trade-in w salonie — ile dostanę za stare auto?
15. Test drive — na co zwrócić uwagę?
16. CPO / certified pre-owned — co to jest?
17. Jak sprawdzić historię samochodu używanego?
18. Samochód hybryda czy pełny elektryk?
19. Zasięg elektryczny w Polsce — czy to problem zimą?
20. Gdzie ładować elektryk w Polsce 2026?
21. Ubezpieczenie nowego auta — ile kosztuje OC/AC?
22. Samochód na leasing a kredyt bankowy — różnice?
23. Co zrobić z autem po leasingu?
24. Jak długo służy nowy samochód?

## 4. KCF (12 feature)
niezawodnosc_gwarancja | naped | forma_finansowania | segment_rozmiar | tco_calkowity | dostepnosc_czas | historia_serwisowa | bezpieczenstwo_ncap | wyposazenie_bazowe | wartosc_rezydualna | trade_in | zasieg_ev

## 7. Tier Pricing
| Tier | PLN | Przykłady | Leasing/mies |
|---|---|---|---|
| Entry A/B | 60k–110k | VW Polo, Yaris, Sandero | 700–1100 PLN |
| Mid C | 110k–180k | VW Golf, Corolla, Octavia | 1100–1800 PLN |
| Premium D/E | 180k–320k | Audi A4/Q5, BMW 3/X3, MB C | 1800–3200 PLN |
| Ultra Premium | 320k+ | Audi Q7/Q8/e-tron, BMW X5 | gotówka/flota |
| Chiński EV | 90k–160k | BYD Seal/Atto3, MG4, OMODA 5 | 900–1600 PLN |

## 8. CDT
1. Nowy vs CPO/Używany
2. Finansowanie (gotówka / leasing / kredyt) — KEY SORTER
3. Priorytet/Budżet
4. Napęd → Fork EV: Premium EV vs Chiński EV (sub-obiekcje: serwis/gwarancja/wstyd/zasięg)
5. Segment/Rozmiar A–E
6. Dostępność/czas dostawy

## 9. Forbidden Patterns
- ❌ "niezawodne i ekonomiczne auto" → ✅ Konkretne dane gwarancji + koszty
- ❌ "niska rata od 999 zł" → ✅ Rata + okres + wpłata + rezydualna + RRSO
- ❌ "chiński elektryk gorszej jakości" → ✅ Bateria CATL + gwarancja 8 lat + serwis PL
- ❌ "EV to przyszłość" → ✅ Warunki opłacalności: km/rok + ładowanie + cena kWh

*Pełna wersja 16 sekcji (CEP×ścieżka×etap): WPIS_CS_samochody_osobowe_prywatny_V2.md w GEO_PDP_Optimizer/*