# Torn Assistant v1.1 — Dollar Bazaars Radar

Jaunums: $1 piedāvājumu radars ar vērtības/darījuma potenciāla kārtošanu, meklēšanu, filtriem, favorītiem, pieejamības atzīmēm un importu.

## Datu statuss

**Sākotnējais saraksts ir publiskās TornW3B lapas 2026-10-12 momentuzņēmums** (20 pirmās rindas). Tas NAV tiešraides pieslēgums. Piedāvājumi var būt izpirkti. Netika atrasta pārbaudāma, dokumentēta publiska $1 saraksta API piekļuve, ko drīkstētu droši pieslēgt statiskai PWA bez servera.

Atver https://weav3r.dev/dollar-bazaars, nokopē aktuālo sarakstu vai sagatavo CSV/JSON, aplikācijā spied **Ielādēt jaunus datus** un ielīmē. Radars izcels jaunās preces, saglabās favorītus un tavu pārbaudīto pieejamības statusu.

CSV kolonnas: `item,seller,id,qty,totalValue,category` (category nav obligāta). JSON masīvs ar `item,seller,id,qty,value` arī der. Vienas preces totalValue ir **visa norādītā daudzuma vērtība**.

## Instalēšana / atjaunināšana

Ja GitHub Pages vēl nav uzstādīts, augšupielādē visus failus repozitorija root un aktivizē Settings → Pages → Deploy from branch → main / root. iPhone Safari → Share → Add to Home Screen.

Ja v1 jau darbojas, aizstāj `index.html`, `sw.js`, `manifest.webmanifest`, `icon.svg` ar jaunajiem failiem, veic commit un pārstartē PWA. Ja vecā versija vēl tiek rādīta, aizver/atver Safari un uzgaidi dažas minūtes (service worker cache).

## Drošība

- Torn API atslēgu ievadi tikai savā PWA. Tā paliek ierīces localStorage. GitHub repozitorijā to nepublicē.
- Dollar Bazaars sadaļai API key **nav vajadzīga**.
- Netiek automātiski veikti pirkumi, pārdošana, uzbrukumi vai citas spēles darbības.
- Pirkšanas tiesības $1 lock gadījumā nosaka Torn. Radars to nevar automātiski pārbaudīt.
- ROI ir teorētisks: `totalValue * 0.95 - qty * $1` (ja visas preces pārdod par norādīto vērtību ar 5% komisiju).
- Kamēr lietotne ir aizvērta, šī versija neveic $1 tirgus uzraudzību vai push brīdinājumus.

Avoti: https://weav3r.dev/dollar-bazaars un https://weav3r.dev/guides/dollar-bazaars
