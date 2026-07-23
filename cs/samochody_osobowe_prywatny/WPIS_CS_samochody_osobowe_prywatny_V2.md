# Samochody osobowe — nabywca prywatny — Category Standard v1.0

*Budowa wg `METODOLOGIA_CS_v3.1_RICH.md` + format 16 sekcji wzorzec `WPIS_CS_pompa_ciepla_V2.md`. Projekt: Audi_Plichta / CS-Automotive. Źródła FAZY 0: badanie VW PHD (24 IDI, 2020) + VW Customer Journey Updated + VW DCJ qual+quant. Oś nadrzędna: nabywca PRYWATNY (B2C), wszystkie marki — CS-1 z planowanej architektury 5 CS-ów automotive. CS-2 (Biznes/JDG), CS-3 (Leasing CEP), CS-4 (EV), CS-0 (Zbiorczy) — osobne dokumenty.*

---

## 0. Opis kategorii

Samochód osobowy to pojazd mechaniczny przeznaczony do przewozu max. 8 osób, kupowany przez osoby prywatne do użytku osobistego, rodzinnego lub codziennego. Zakup odbywa się przez salon dealerski (nowe) lub rynek wtórny (używane/CPO). W Polsce nowe auto kosztuje 60 000–400 000+ PLN; używane 20 000–200 000+ PLN. Cykl decyzji wynosi 2–6 miesięcy dla prywatnych nabywców — dłuższy przy finansowaniu pozagotówkowym i wyższym zaangażowaniu emocjonalnym. **To nie jest zakup e-commerce: wymaga jazdy próbnej, negocjacji, weryfikacji finansowania, często trade-in'u istniejącego auta.** Kategoria podlega silnemu zakłóceniu ze strony chińskich marek elektrycznych (BYD, MG, OMODA, Xpeng) oferujących bogate wyposażenie w segmencie 90–140k PLN — tradycyjnie zarezerwowanym dla europejskich marek mid-range.

## 0b. Problemy, które kategoria załatwia

**🎯 Primary (rdzeń):** *Bezpieczne, niezawodne i odpowiednie dla stylu życia przemieszczanie się — z poczuciem spokoju, kontroli i (często) statusu.*

**Secondary — rozbite na sytuację (każda = zalążek CEP):**

- frustracja awaryjnym / drogim w utrzymaniu autem → `cep_awaria_frustracja`
- zmiana sytuacji rodzinnej (dziecko, rozwód, puste gniazdo, nowa praca) → `cep_zmiana_zyciowa`
- odkrycie że leasing = nowe auto za ratę jak czynsz → `cep_leasing_odkrycie`
- rosnące koszty eksploatacji (paliwo, przeglądy, naprawy) → `cep_koszty_eksploatacji`
- nagroda dla siebie / zmiana modelu na nowszy (awans, premium) → `cep_self_gift_awans`
- ciekawość elektryka i rynek tanieje (chińskie EV) → `cep_elektryk_ciekawostka`
- koniec umowy leasingowej / wynajmu → `cep_koniec_leasingu` *(bridge do CS-2 Biznes)*
- pierwsze auto po prawie jazdy → `cep_pierwsze_auto`

> ⚠️ Moc silnika, skrzynia biegów, pojemność bagażnika, kolor — to NIE problemy, to atrybuty → KCF/preselekcja, nie CEP.

---

## 1. CEV — Category Emotional Valuation

**Pasek profilu emocjonalnego kategorii (10 cech) — nabywca prywatny:**

| ryzyko | lęk | widoczność | impuls | sexy | aspiracja | tożsamość | zmysłowość | pilność | moralność |
|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| .90 | .80 | .85 | .05 | .75 | .85 | .80 | .75 | .50 | .30 |

- **ryzyko .90** — DRUGIE NAJWIĘKSZE RYZYKO PO NIERUCHOMOŚCI. Błąd zakupowy = 30–400k PLN stracone + 3–7 lat życia ze złą decyzją + brak wyjścia bez dużej straty (resale, utrata kaucji leasingowej). Wyjątkowość: commitowanie z odroczoną możliwością korekty (nie jak ubranie, które oddasz).
- **lęk .80** — wielowarstwowy: (1) czy nie przepłacam vs rynek, (2) czy dealer mnie nie kręci (presja salonu, opcje które nie są worth it), (3) czy finansowanie to nie pułapka, (4) przy używanym — co ukryli, (5) czy wybór marki/modelu nie okaże się żenujący za 3 lata. Pik lęku przy podpisywaniu umowy.
- **widoczność .85** — samochód to NAJWIĘKSZY widzialny wyraz statusu w Polsce (mieszkanie/dom schowany za bramą, auto widać codziennie: praca, szkoła, rodzina, sąsiedzi). Szczególnie silne w miastach gdzie auto = wizytówka i pierwszy sygnał statusowy.
- **aspiracja .85** — „w końcu na to stać" jest RDZENIEM kategorialnym dla mid/premium. Samochód jako materializacja osiągnięcia życiowego (awans, własna firma, spłata kredytu, dorosłe dzieci). Silniejszy niż dla większości kategorii — nie ma analogu „aspirować do pralki".
- **tożsamość .80** — marka = deklaracja tożsamości. Audi = profesjonalizm/sukces. BMW = dynamika/sport. VW = rozsądek/solidność. Tesla/BYD = nowoczesność/postawa ekologiczna. Pytanie „jakim autem jeździsz" = pytanie „kim jesteś". Zmiana marki = deklaracja zmiany tożsamości.
- **sexy .75** — samochód jako obiekt pragnienia (design zewnętrzny, wnętrze premium, dźwięk silnika, osiągi). Szczególnie silny przy segmencie E/F i sportowych wariantach. Test drive jest RYTUAŁEM inicjacji — „sprzedaje" ten wymiar.
- **zmysłowość .75** — multisensoryczny: zapach nowego auta (ikonicznie silny, punkt sprzedaży), faktura skóry, dźwięk zamykania drzwi (BMW inżynieruje go latami), dźwięk silnika (exhaust note w sportowych), wibracje fotela. Jeden z nielicznych zakupów gdzie zmysłowość jest jawna i oczekiwana.
- **pilność .50** — zmienna: niska przy planowanym zakupie premiumowym (3-6 mies. research), wysoka przy trigger `cep_awaria_frustracja` (stary się psuje → musisz mieć transport już). Asymetria per CEP.
- **impuls .05** — faktycznie zero impulsu. Nawet „okazja" (koniec roku, promocja) wymaga tygodnia deliberacji. To planowana, rozciągnięta w czasie decyzja z punktem wejścia (CEP) ale długim łukiem.
- **moralność .30** — rosnące: ekologia jako motywacja przy EV. Silne u millenialsów + Gen Z. Ale w Polsce 2026 wciąż mniejszościowy driver vs ekonomia/status.

→ Fork **EMOCJA + POTRZEBA**, research **wysoki (3–5 mies.)**. Garby: **Nowy vs Używany**, **Finansowanie**, **Wybór marki/modelu**, **Negocjacja/Trade-in**, **Oczekiwanie na dostawę**.

---

## 2. CEP — Consumer Entry Points *(weryfikator: sytuacja-nie-atrybut / realny verbatim / nie-sierota)*

| id | Trigger (język konsumenta, verbatim) | Kontekst | Primary concern | Bloker decyzji | Routes to | Anchor content |
|---|---|---|---|---|---|---|
| `cep_awaria_frustracja` | „ten samochód miał po prostu 17 lat. Zaczął się mocno psuć i stwierdziłem, że za chwilę wartość napraw przekroczy wartość samochodu" / „nie chcę mieć niespodzianek jak w Nubirze" | stary samochód 10–20 lat, rosnące koszty napraw, coraz mniej zaufania do auta | spokój, niezawodność, koniec stresu z naprawami | **bariera wejścia nowy vs używany** (używany = znowu ryzyko niespodzianek) | nowe auto gwarancja 3–5 lat lub CPO z gwarancją | „gwarancja = spokój na 4 lata bez kosztów" + test drive |
| `cep_zmiana_zyciowa` | „żeby właśnie było wygodniej przy dziecku" / „mam szkolenia, często wyjazdowe — samochód bardzo pomoże" / „nowe samochody pojawiły się, jak córki zaczęły kończyć studia — już nie miałem takich obciążeń finansowych" | narodziny dziecka, zmiana pracy, wyprowadzka dzieci, rozwód, nowa praca z dojazdami | dopasowanie auta do nowej sytuacji życiowej | **czy przy nowej sytuacji życiowej stać mnie na nowe z gwarancją, czy CPO — i jak szybko muszę decydować?** | segment zależny od zmiany: SUV/kombi (dziecko), hatchback (single/city), sedan (praca) | konfiguracja per sytuacja + kalkulator TCO |
| `cep_leasing_odkrycie` | „a można mieć nowe auto za 1200 zł miesięcznie?" / „nie wiedziałem, że leasing jest dostępny dla osób prywatnych" | osoba wcześniej niekupująca nowego, odkrywa że rata leasingowa = dostępna finansowo | czy mnie stać na nowe? czy leasing to nie kredyt pułapka? | **brak wiedzy o leasingu prywatnym** (warunki, koszty całkowite, wartość rezydualna) | mid-range auto leasing 48–60 mies. | „co to jest leasing prywatny — raty, wartość rezydualna, własność" |
| `cep_koszty_eksploatacji` | „benzyna po 7,50 PLN/L, miesięcznie wychodzi mi 900 zł — zaczynam liczyć czy cokolwiek nowszego nie wyszłoby taniej" / „dołożyłem 3000 PLN w przegląd, to może jednak nowe" | rosnące koszty paliwa / serwisu, kalkulacja TCO bez emocji awarii | kiedy opłaca się zmienić auto z powodów ekonomicznych | **payback i TCO** (kiedy nowe jest tańsze niż utrzymanie starego) | hybryda / mild hybrid / diesel zależnie od przebiegu | „kalkulacja kosztu przejazdu 100 km stare vs nowe (spalanie + serwis)" |
| `cep_self_gift_awans` | „no z takiej właśnie próżności — chcę trochę pójść do przodu" / „jak córki skończyły studia i nie miałem już takich obciążeń — czas pomyśleć o sobie" / „w końcu mogę sobie pozwolić na coś lepszego" | awans zawodowy, spłacony kredyt, dzieci usamodzielnione, spadek, jubileusz | nagroda dla siebie, upgrade stylu życia, status | **czy wydanie 280k na auto to nie rozrzutność / czy zasługuję na to** (permission-to-splurge) + **co konkretnie daje droższy model** | segment premium lub wyższy tier dotychczasowej marki | konfiguracja opcji + test drive (emocja przed ceną) |
| `cep_elektryk_ciekawostka` | „kolega kupił BYD Seal za 130k, policzył koszty vs diesel — zaczynam brać to na poważnie" / „mam PV w domu, ładuję za 0 — zacząłem patrzeć na elektryki. Ale serwis gdzie?" | prywatny nabywca który do tej pory uważał EV za „za drogi / za mały zasięg", i odkrywa że chiński elektryk przekroczył jego próg cenowy (130–140k PLN) LUB że PV/ładowarka domowa zmienia rachunek kosztów | czy EV to sensowny wybór dla mnie TERAZ? Czy chiński elektryk nie zostawi mnie bez serwisu? | **chińskie EV vs europejskie** (zasięg, serwis, gwarancja, wstydu test) + infrastruktura ładowania PL | premium EV (Audi Q4/etron, BMW i4) vs chiński EV (BYD, MG, OMODA) | „EV w Polsce 2026 — zasięg, ładowanie, koszty vs spalinowe" + porównanie TCO |
| `cep_koniec_leasingu` | „kończy mi się leasing za 8 miesięcy, zaczynam się rozglądać" / „co robię z autem po leasingu — odkupuję czy zmieniam?" | koniec umowy leasingowej (prywatnej lub firmowej), zaplanowana zmiana | optymalny scenariusz po leasingu: odkup / zwrot / nowy leasing | **wartość rezydualna vs cena rynkowa** + nowe warunki | bridge do CS-2 Biznes, albo nowy leasing prywatny | „co zrobić z autem po leasingu — wykup, zwrot, nowa umowa" |
| `cep_pierwsze_auto` | „zrobiłam prawo jazdy na Aygo i przyzwyczaiłam się — chcę kupić takie samo" / „świeży kierowca — używane żeby nie stresować, czy nowe z gwarancją?" | niedawno zdobyte prawo jazdy, pierwsza samodzielna decyzja zakupowa | niezawodność + niski stres prowadzenia + niewielkie rozmiary | **nowe i bać się każdego zarysowania vs używane i nie boleć** (nowe zbyt cenne = stres zamiast radości) | small segment A/B (nowe lub certyfikowane używane) | „pierwsze auto dla nowego kierowcy — co wziąć pod uwagę" |

---

## 3. Discovery Questions (floor 22, kategoryczne — nie brandowe)

1. Nowy czy używany samochód — co wybrać w 2026? Kiedy warto nowy, kiedy używany?
2. Jak długo czeka się na nowy samochód z salonu?
3. Leasing prywatny na samochód — jak działa? Czy warto?
4. Ile wynosi rata leasingowa na nowe auto 2026? Kalkulator.
5. Co sprawdzić przed zakupem używanego samochodu? Lista kontrolna.
6. Samochód elektryczny czy spalinowy — co wybrać w Polsce 2026?
7. Czy chińskie samochody elektryczne są bezpieczne / godne zaufania?
8. BYD vs Audi / BMW — co wybrać? Porównanie elektrycznych.
9. Ile kosztuje utrzymanie samochodu miesięcznie (paliwo + ubezpieczenie + serwis)?
10. Jakie auto dla rodziny z dziećmi — ranking 2026?
11. Samochód do 100 000 / 150 000 / 200 000 PLN — co najlepszego?
12. Jak negocjować cenę samochodu w salonie? Ile można wynegocjować?
13. Czy warto kupować samochód na koniec roku / rocznik?
14. Trade-in w salonie — ile dostanę za stare auto?
15. Test drive — na co zwrócić uwagę? Jak go zorganizować?
16. CPO / certified pre-owned — co to jest? Czy warto?
17. Jak sprawdzić historię samochodu używanego (CARFAX, AutoDNA)?
18. Samochód hybryda czy pełny elektryk — co wybrać?
19. Zasięg elektryczny w Polsce — czy to problem zimą?
20. Gdzie ładować elektryk w Polsce — infrastruktura 2026?
21. Ubezpieczenie nowego auta — ile kosztuje OC/AC dla nowego?
22. Samochód na leasing a kredyt bankowy — różnice, co się opłaca?
23. Co zrobić z autem po leasingu — odkupić, zwrócić czy zmienić?
24. Jak długo służy nowy samochód? Ile lat opłaca się trzymać?

> ⭐ Każdy `bloker_decyzji` z §2 → ≥1 Discovery + zaplanowana treść S2 gasząca. „Czy EV sensowny w Polsce" → Q6/Q18/Q19/Q20. „Nowy vs używany" → Q1/Q5/Q16/Q17.

---

## 4. KCF — Key Category Features *(waga per segment: Prywatny=●●●, Opcja=●●, Niszowy=●)*

| Feature | Zakres rynkowy | Tier | Waga Pryw. | Uwaga |
|---|---|:--:|:--:|---|
| Niezawodność / gwarancja | 3–5 lat fabryczna + ASO | T1 | ●●● | **Rdzeń emotional value: spokój, bezpieczeństwo, #brakproblemów** |
| Napęd | benzyna/diesel/mild hybrid/PHEV/BEV | T1 | ●●● | Determinuje TCO, zakres użycia, wizerunek |
| Forma finansowania | gotówka / leasing prywatny / kredyt / wynajem | T1 | ●●● | Zmienia całą logikę decyzji i treść argumentacji |
| Segment/rozmiar | A (city) / B (hatchback) / C (kompakt) / D (sedan/SUV) / E (premium SUV) | T1 | ●●● | Dopasowanie do sytuacji życiowej + garażu |
| TCO — całkowity koszt posiadania | paliwo + ubezpieczenie + serwis + amortyzacja | T1 | ●●● | Często ignorowany przy zakupie, kluczowy post-purchase |
| Czas oczekiwania / dostępność | od ręki vs 3–18 miesięcy (custom order) | T1 | ●●● | Bariera przy pilnym zakupie, argument sprzedażowy |
| Historia serwisowa / przebieg | dla używanych: ASO, km, accidents | T1 | ●●● | Blok lęku przy CPO/używany |
| Bezpieczeństwo NCAP | 5-star / asystent hamowania / lanekeeper | T2 | ●● | Kluczowe dla rodzin z dziećmi, rośnie jako standard |
| Wyposażenie bazowe | klimatyzacja / navi / asystent parkowania / kamera cofania | T2 | ●● | Chiński EV tu wygrywa w mid-range (dużo w cenie) |
| Wartość rezydualna | po 3–4 latach: procent wartości nowego | T2 | ●● | Ważne dla leasingobiorców i planujących dalszą sprzedaż |
| Trade-in / odkup od dealera | wartość oferowana za stare auto | T2 | ●● | Lubricant zakupu — zmniejsza próg wejścia |
| Zasięg EV / infrastruktura ładowania | km WLTP / dostęp do szybkich ładowarek PL | T2 | ●● | Blok lęku dla EV (range anxiety) |
| Customizacja / czas dostawy | kolory, opcje, konfiguracja vs stock | T3 | ● | Ważna dla segmentu SERCE/premium |
| Dealer lokalny / serwis ASO | proximity, opinia, kontakt z handlowcem | T3 | ● | Kluczowa dla retencji i trust — lokalny dealer > brand national |

---

## 5. Typowy produkt — konwencje kategorii

| Cecha | Norma kategorii | Red flag |
|---|---|---|
| Gwarancja | min. 3 lata producent; CPO 1–2 lata na używanym | brak gwarancji na używanym z salonu |
| Przegląd serwisowy | ASO co 12 mies. / 15 000 km | „serwisowany" bez dokumentów ASO |
| Badanie techniczne | ważne przez 2 lata od zakupu nowego | przeterminowane = ukryta bariera |
| Historia | raport AutoDNA / CARFAX lub certyfikat CPO | brak raportu na używanym od dealera |
| Finansowanie | jasne warunki leasingu: rata netto, wartość rezydualna, RRSO | „niska rata" bez podania wartości rezydualnej |
| Test drive | dostępny przed zakupem na każdy model | brak testdrive na model który chcesz kupić |
| Handlowanie | cena zawiera realne rabaty modelowe + opcje promocje | „cena na fakturze" bez rozbicia |
| Czas dostawy | jasna informacja: od ręki / termin produkcji | „około 3 miesięcy" bez daty |

---

## 6. Tier Specs

**Tier-1 Universal** (musi być przy każdym modelu): napęd · moc [KM] · zużycie paliwa [l/100km] lub zasięg EV [km WLTP] · gwarancja [lata] · segment · cena brutto PLN · dostępność (od ręki/data dostawy).
**Tier-2 Differentiator:** NCAP stars · wyposażenie bazowe lista · opcje leasingowe (rata/mies, parametry) · wartość rezydualna · TCO szacunkowy.
**Tier-3 Niche:** kolory/customizacja · historia serwisowa (CPO) · technologie bezpieczeństwa szczegółowe · połączenia smart (Apple CarPlay, OTA updates).

---

## 7. Tier Pricing — PLN, Polska 2026 *(prywatny nabywca, nowe auto)*

| Tier | Cena zakupu (nowe) | Przykłady | Finansowanie | Typowy kupujący |
|---|---|---|---|---|
| Entry (A/B segment) | 60 000–110 000 PLN | VW Polo, Skoda Fabia, Toyota Yaris, Dacia Sandero | gotówka / kredyt / leasing ~700–1100 zł/mies | pierwsze auto, city, budżet napięty |
| Mid (C segment) | 110 000–180 000 PLN | VW Golf, Toyota Corolla, Skoda Octavia, Hyundai Tucson | leasing ~1100–1800 zł/mies | rodziny, praca z dojazdami |
| Premium (D/E segment) | 180 000–320 000 PLN | Audi A4/Q5, BMW 3/X3, Volvo XC60, MB C-klasa | leasing/gotówka ~1800–3200 zł/mies | awans, samoreward, biznes |
| Ultra Premium (E/F+) | 320 000+ PLN | Audi Q7/Q8/e-tron, BMW X5/7, Porsche | gotówka / leasing flotowy | zamożni prywatni, management |
| Chiński EV (disruptor) | 90 000–160 000 PLN | BYD Seal/Atto3, MG4, OMODA 5 EV, Xpeng G6 | leasing ~900–1600 zł/mies | tech-savvy, ECO-minded, Value hunters |

---

## 8. Consumer Decision Tree

*Oś: nabywca prywatny, nowe auto (kanał primary). CDT wg stratega werdykt (2026-07-23): Q1=nowy/CPO, Q2=finansowanie (sort!), Q3=priorytet/budżet, Q4=napęd (tu EV fork z chińską konkurencją), Q5=lokalność/dostępność.*

### Drzewo — kanał [PRYWATNY NABYWCA]

**L1 — routing: sytuacja (CEP) → typ decyzji**

| Sytuacja (CEP) | → Typ / pierwszy krok |
|---|---|
| Mój stary się psuje i kosztuje za dużo / stwierdziłem że nowe | CPO z gwarancją lub nowe mid — najpierw gwarancja |
| Zmieniła mi się sytuacja rodzinna / zawodowa / potrzebuję innego | segment per sytuacja — najpierw rozmiar/typ |
| Odkryłem że mogę mieć nowe za ratę jak czynsz | leasing prywatny — najpierw zdolność kredytowa |
| Koszty eksploatacji są za duże / liczy mi się oszczędność | hybryda/diesel — najpierw kalkulator TCO |
| Chcę się nagrodzić / stać mnie na więcej | premium segment — najpierw test drive |
| Interesuję się elektrykiem / zastanawiam się nad chińskim EV | EV fork — najpierw zasięg + infrastruktura + porównanie marek |
| Kończy mi się leasing, co dalej | → CS-2 Biznes lub nowy leasing prywatny |
| Pierwsze auto po prawie jazdy | small segment / CPO — bezpieczeństwo + niskie koszty |

**L2 — sekwencja pytań decyzyjnych:**

1. **Nowy vs CPO/Używany** — nowe: gwarancja/spokój/cena; CPO: kompromis; używane: ryzyko lęku
2. **Forma finansowania** — gotówka: zamożni/tradycjonaliści (posiadanie); leasing: rata/nie-moje; kredyt: własność+raty → **zmienia całą argumentację contentową**
3. **Priorytet/Budżet** — rata mies. / całkowity budżet / TCO na 4 lata
4. **Napęd** — benzyna/diesel / mild hybrid / PHEV / BEV
   - **Fork EV → sub-węzeł: Premium EV (Audi/BMW/Volvo 150k+) vs Chiński EV (BYD/MG 90–140k)**
   - Sub-węzeł obiekcja chiński: serwis PL? gwarancja? wstydu test? zasięg zimą?
5. **Segment/rozmiar** — A-B (city/pierwsze) / C (family/kompakt) / D-E (premium/SUV)
6. **Dostępność/czas** — od ręki vs termin produkcji (pilność zakupu determinuje wybór)

**Kluczowe info wyjścia (mandatory w treści/PDP):** napęd · cena brutto · gwarancja [lata] · rata leasingowa [PLN/mies] · czas dostawy/dostępność · wyposażenie bazowe · zasięg [EV: km WLTP]

---

## 9. Forbidden Patterns

| ❌ Zakazane | ✅ Poprawne |
|---|---|
| „niezawodne i ekonomiczne auto" | „Gwarancja 5 lat ASO + bezpłatne przeglądy do 100 000 km — 4 lata bez nieplanowanych kosztów" |
| „niska rata od 999 zł" | „Rata leasingowa 1 190 PLN/mies. netto (48 mies., wpłata 10%, wartość rezydualna 35%, RRSO 6,9%)" |
| „szybka dostawa" | „Dostępność: 3 sztuki na placu / zamówienie indywidualne: ok. 14 tygodni (stan 2026-07)" |
| „bogate wyposażenie w standardzie" | Lista funkcji bazowych: klimatyzacja automatyczna / Apple CarPlay / kamera cofania / asystent hamowania awaryjnego" |
| „najlepsze auto w klasie" | „5 gwiazdek Euro NCAP 2025 + wynik Adult Occupant Protection 87%" |
| „chiński elektryk gorszej jakości" | „BYD Seal: bateria CATL 82 kWh / zasięg 570 km WLTP / gwarancja 8 lat na baterię / serwis: [X] punktów w PL" |
| „EV to przyszłość" | „Elektryk opłaca się gdy: roczny przebieg >15 000 km + dostęp do ładowania w domu/pracy + cena energii <1,0 PLN/kWh" |
| „test drive możliwy do umówienia" | „Test drive: umów online w 2 minuty — wybierz datę i model, potwierdzenie SMS w 1h" |

---

## 10. Ścieżki percepcji & pole pytań

**Tyle ścieżek ile CEP** (każda = osobna ścieżka etapy świadomości × pytania). Etapy wg CEV (fork EMOCJA+POTRZEBA, garby na Finansowaniu/Wyborze modelu/Negocjacji). 🛡️ = bloker decyzji. Intent: ⚪ info · 🔵 komerc · 🟢 transakc.

### [PRYWATNY NABYWCA]

**Ścieżka A — `cep_awaria_frustracja`** (stare auto się psuje)
- *Świadomość:* Kiedy opłaca się kupić nowe auto zamiast naprawiać stare? ⚪ · Mój samochód ciągle się psuje — nowy czy remont? ⚪
- *Orientacja:* Nowy samochód gwarancja — ile lat i co obejmuje? 🔵 · 🛡️ Nowe auto vs CPO/używane — który spokojniejszy? 🔵
- *Nauka:* Co to jest CPO (Certified Pre-Owned) i czy warto? ⚪ · Koszty utrzymania nowego vs używanego w pierwszych 4 latach? ⚪
- *Decyzja:* Test drive przed zakupem — jak umówić w salonie? 🔵 🟢 · 🛡️ Jak negocjować cenę i czy warto handlować? 🔵

**Ścieżka B — `cep_zmiana_zyciowa`** (dziecko, nowa praca, rozstanie)
- *Świadomość:* Jakie auto dla rodziny z dziećmi — co jest najważniejsze? ⚪
- *Orientacja:* SUV czy kombi dla rodziny — różnice praktyczne? 🔵 · Samochód z dużym bagażnikiem — ranking 2026? 🔵
- *Nauka:* Bezpieczeństwo NCAP — jak porównywać wyniki? ⚪ · Asystenty bezpieczeństwa — co jest w standardzie? ⚪
- *Decyzja:* 🛡️ Czy stać mnie na nowe z gwarancją czy lepiej używane? 🔵 · 🟢 Konfiguracja + rezerwacja przez salon online

**Ścieżka C — `cep_leasing_odkrycie`** (leasing = nowe za ratę)
- *Świadomość:* Leasing prywatny na samochód — jak działa? ⚪ · Czy osoba prywatna może wziąć leasing na auto? ⚪
- *Orientacja:* Ile kosztuje leasing na nowe auto 2026 — kalkulator? 🔵 · 🛡️ Leasing vs kredyt — co bardziej opłaca przy prywatnym zakupie? 🔵
- *Nauka:* Co to jest wartość rezydualna leasingu? ⚪ · Czy po leasingu mogę odkupić auto? ⚪
- *Decyzja:* Jaka rata leasingowa na [model]? 🔵 · Jakie dokumenty do leasingu prywatnego? 🟢

**Ścieżka D — `cep_koszty_eksploatacji`** (ekonomika TCO)
- *Świadomość:* Ile kosztuje utrzymanie samochodu miesięcznie? ⚪ · Czy hybryda jest tańsza w utrzymaniu niż diesel? ⚪
- *Orientacja:* 🛡️ Kiedy opłaca się zmienić stare auto na nowe (TCO kalkulacja)? 🔵 · Kalkulator kosztów leasingowych vs gotówkowych? 🔵
- *Nauka:* Hybryda vs diesel — kiedy hybryda się opłaca? ⚪ · Ile prądu zużywa elektryk vs litrów benzyny 100 km? ⚪
- *Decyzja:* Samochód hybrydowy — ranking ekonomiczny 2026? 🔵 🟢

**Ścieżka E — `cep_self_gift_awans`** (nagroda, premium)
- *Świadomość:* Na jakie auto mogę sobie pozwolić po awansie / kiedy mnie stać? ⚪
- *Orientacja:* Różnica między Audi A4 a BMW 3 — co wybrać? 🔵 · Co daje wyższy segment — czy warto dopłacać? 🔵
- *Nauka:* Wartość rezydualna auta premium — czy traci mniej? ⚪ · Jakie opcje warto dokupić a jakie przepłacać? ⚪
- *Decyzja:* Test drive premium — jak zarezerwować + co sprawdzić? 🔵 · 🛡️ Konfiguracja vs auto dostępne — ile czekam na custom? 🟢

**Ścieżka F — `cep_elektryk_ciekawostka`** (EV fork, kluczowy disruptor)
- *Świadomość:* Czy warto kupić elektryka w Polsce 2026? ⚪ · BYD vs Audi / BMW elektryczne — co wybrać? ⚪
- *Orientacja:* 🛡️ Zasięg elektryka zimą w Polsce — ile realnie? ⚪ · Gdzie ładować elektryk — infrastruktura 2026? ⚪ · Chiński elektryk — czy bezpieczny / godny zaufania? ⚪
- *Nauka:* TCO elektryk vs benzyna — kiedy się opłaca? 🔵 · Serwis chińskiego auta elektrycznego w Polsce — gdzie? ⚪ · 🛡️ Gwarancja na baterię elektryczną — ile lat? ⚪
- *Decyzja:* Który elektryk do 150 000 PLN — porównanie BYD/MG/Audi/BMW? 🔵 · 🟢 Test drive elektryka + jazda autostradowa

**Ścieżka G — `cep_pierwsze_auto`** (nowy kierowca)
- *Świadomość:* Jakie pierwsze auto dla nowego kierowcy? ⚪ · Nowe czy używane jako pierwsze auto? ⚪
- *Orientacja:* 🛡️ Małe auto do miasta — ranking bezpiecznych dla początkujących? 🔵 · Ubezpieczenie pierwszego auta — ile kosztuje OC/AC? 🔵
- *Nauka:* Czy można wziąć leasing jako młody kierowca? ⚪ · Co sprawdzić przy odbiorze nowego auta z salonu? ⚪
- *Decyzja:* 🟢 Konfiguracja entry + OC kalkulacja + rezerwacja jazdy próbnej

---

## 11. Cross-Category Triggers

| Kategoria źródłowa | Trigger | CEP aktywowany | Fraza wejściowa w AI |
|---|---|---|---|
| Fotowoltaika / energia | „mam PV, może elektryk i ładuję za darmo?" | `cep_elektryk_ciekawostka` | „elektryk z fotowoltaiką — oszczędności" |
| Ubezpieczenia | „muszę ubezpieczyć nowe auto — ile kosztuje?" | `cep_zmiana_zyciowa` | „ubezpieczenie nowego samochodu OC AC" |
| Kredyt / finanse osobiste | „mam zdolność kredytową — czy brać kredyt czy leasing?" | `cep_leasing_odkrycie` | „leasing prywatny vs kredyt samochodowy" |
| Nieruchomości / przeprowadzka | „kupuję dom z garażem — może czas na większe auto?" | `cep_zmiana_zyciowa` | „jakie auto przy domu na przedmieściach" |
| Rynek pracy / awans | „dostałem podwyżkę — co zmieniam: mieszkanie, auto?" | `cep_self_gift_awans` | „na co wydać premię / podwyżkę — auto premium" |
| Serwis samochodowy | „dałem 5000 do serwisu — może czas na zmianę?" | `cep_awaria_frustracja` | „kiedy lepiej kupić nowe niż naprawiać stare" |

---

## 12. Tone of Voice for GEO — jak pisać treść cytowalną przez AI

1. Odpowiadaj w pierwszym zdaniu, konkretnie z warunkiem: „Nowe auto opłaca się zamiast napraw gdy suma napraw w roku przekroczy 20–30% wartości auta lub gdy auto ma >15 lat."
2. Rozbrajaj emocjonalne blokery wprost faktem: „Chiński elektryk nie oznacza gorszej jakości — BYD używa baterii CATL (ten sam dostawca co Tesla), gwarancja 8 lat na baterię."
3. Leasingowe parametry ZAWSZE kompletnie: rata · okres · wpłata własna · wartość rezydualna · RRSO. Sama rata bez kontekstu = manipulacja.
4. Każdy parametr z konsekwencją: „Gwarancja 5 lat ASO → serwis w autoryzowanej sieci → brak ryzyka utraty gwarancji."
5. Czas oczekiwania zawsze z datą lub zakresem — „ok. 3 miesiące" to nie informacja.
6. Tłumacz terminologię językiem klienta: „wartość rezydualna = ile auto jest warte po leasingu = ile zapłacisz żeby je odkupić."
7. TCO zawsze jako porównanie roczne: „Diesel: paliwo 7 000 PLN/rok + serwis 2 500 PLN = 9 500 PLN. Hybryda: 4 200 PLN + 1 800 PLN = 6 000 PLN."
8. Mapuj cechę na lęk: „Gwarancja 5 lat" → „4 lata spokoju bez rachunków za naprawy."
9. Adresuj porównania które klient zrobi i tak: EV vs spalinowe, chiński vs europejski, nowe vs CPO — tabelą.
10. Zamykaj sekcję faktem do zacytowania (liczba/norma/warunek), nie CTA.

---

## 13. Pole pytań

### ① Discovery (otwarcie — 24 kategoryczne, patrz §3)

### ② Pogłębione (per ścieżka — rozpisane w §10, A–G, etap × pytanie × intent)
7 ścieżek CEP, pytania pogrupowane po etapach świadomości, intent oznaczony (⚪/🔵/🟢).

### ③ Blokery 🛡️ (ekstrakcja FAQ — obiekcje, każda wymaga S2 gaszącej)

- 🛡️ **„Nowy czy używany — co lepsze dla mnie?"** ← NAJWIĘKSZY bloker kategorii (bifurkacja CEP) → S2: warunki kiedy nowe ma sens (gwarancja, TCO, spokój) vs CPO (certyfikat, sprawdzona historia).
- 🛡️ **„Chiński elektryk — czy warto mu zaufać?"** ← NOWY KRYTYCZNY BLOKER (2025–2026) → S2: bateria CATL, gwarancja 8 lat, sieć serwisowa w PL, porównanie TCO.
- 🛡️ **„Leasing — czy to nie pułapka? Czy na końcu nic nie mam?"** → S2: wartość rezydualna jako opcja wykupu, nie obowiązek; porównanie kosztów z kredytem.
- 🛡️ **„Zasięg elektryka zimą — czy mnie nie zostawi na drodze?"** → S2: realne dane zimowe -20°C, sieć szybkich ładowarek PL, backup planowanie.
- 🛡️ **„Jak sprawdzić czy używane auto nie jest powypadkowe?"** → S2: AutoDNA/CARFAX + certyfikat CPO + co sprawdzić okiem.
- 🛡️ **„Ile faktycznie można wynegocjować w salonie?"** → S2: realistyczne rabaty (3–10% przy nowym, wyższe przy demonstracyjnym), kiedy pytać.
- 🛡️ **„Ile faktycznie czekam na nowe auto?"** → S2: modele dostępne vs zamówienie (aktualny czas produkcji per producent).
- 🛡️ **„Co mi się bardziej opłaci — gotówka czy leasing?"** → S2: kalkulator z konkretnymi parametrami, warunki każdego scenariusza.

> Render docelowy: widok łączony CS + mapa percepcji (3-tab: mapa / CS / łączony). Pipeline: `python3 render_cs_mapa.py samochody_osobowe_prywatny --all`

---

*Status: CS-1 v1.0 zbudowany na podstawie VW PHD research (24 IDI, 2020) + VW Customer Journey Updated + werdyktu audi-strateg (2026-07-23). Czeka na wzbogacenie: dane GA4 Plichty (proporcje segmentów, top queries) + dane CRM (leasing vs gotówka proporcja) + rozmowy handlowców Plichty (główne obiekcje z salonu). Chińskie EV (§9 + Ścieżka F) = nowa zmienna 2025–2026 — wymaga monitoring co 6 mies.*
