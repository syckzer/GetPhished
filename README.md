# GetPhished! 🎣

> Interaktivní webová hra pro rozpoznávání phishingových e-mailů

![HTML](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![No dependencies](https://img.shields.io/badge/závislosti-žádné-brightgreen?style=flat)

| | |
|---|---|
| **Autor** | Petr Přibyl |
| **Škola** | Academic School |
| **Typ práce** | Maturitní projekt |
| **Vedoucí práce** | Pavel Valášek |

---

## O projektu

**GetPhished!** je jednostránková webová aplikace (SPA), která simuluje reálné prostředí e-mailové schránky a učí uživatele rozpoznávat phishingové útoky. Hráč prochází 20 e-maily — 10 phishingových a 10 legitimních — a u každého rozhoduje, zda jde o podvod nebo důvěryhodnou zprávu. Po každé odpovědi dostane okamžité vysvětlení, co ho prozradilo.

Cílem projektu je zvýšit povědomí o phishingu interaktivní formou, která je prokazatelně efektivnější než pasivní čtení bezpečnostních příruček.

---

## Co je phishing?

Phishing je jedna z nejrozšířenějších forem kybernetického útoku. Útočník se vydává za důvěryhodnou osobu nebo instituci — banku, státní úřad, technologickou firmu nebo kolegu — a snaží se oběť přimět k vyzrazení citlivých údajů nebo ke kliknutí na škodlivý odkaz.

**Typické znaky phishingového e-mailu:**

| Znak | Příklad |
|---|---|
| 🔗 Podezřelá doména odesílatele | `support@bankaltd-secure.cz` místo `support@bankaltd.cz` |
| 🔤 Typosquatting | `micros0ft-support.com` (číslice 0 místo písmene o) |
| ⚠️ Naléhavý tón a časový tlak | „do 24 hodin", „OKAMŽITĚ", „URGENTNÍ" |
| 🌐 Falešné URL adresy | odkaz nevede na oficiální web firmy |
| 🎁 Příliš lákavé nabídky | výhry, slevy, vrácení peněz |
| 🔑 Žádosti o hesla nebo platby | legitimní firmy toto e-mailem nikdy nežádají |
| 📝 Pravopisné chyby | zejména u automaticky přeložených textů |

Hra pokrývá nejčastější typy phishingových útoků v českém prostředí: bankovní phishing, zásilkové podvody (DHL, Česká pošta), falešné státní úřady (ČSSZ, Úřad práce), technologické společnosti (Microsoft, PayPal) i výherní podvody.

---

## Jak spustit

Projekt nevyžaduje žádnou instalaci, server ani závislosti.

```bash
git clone https://github.com/tvuj-username/getphished.git
cd getphished
```

Poté stačí otevřít soubor `main.html` v libovolném moderním prohlížeči.

> Alternativně si soubor `main.html` stáhni přímo a otevři ho dvojklikem — žádná instalace není potřeba.

---

## Jak se hraje

```
1. Na úvodní obrazovce si přečti základní informace o phishingu
2. Klikni na ▶ SPUSTIT HRU
3. V levém panelu uvidíš seznam 20 e-mailů — klikni na libovolný
4. Přečti si e-mail pozorně — všimni si adresy odesílatele a URL odkazů
5. Rozhodni se: 🚨 Phishing nebo ✅ Legitimní
6. Ihned uvidíš vysvětlení správné odpovědi
7. Hra končí po zodpovězení všech 20 e-mailů nebo ztrátě 3 životů
8. Na výsledkové obrazovce uvidíš skóre a přehled všech e-mailů
```

**Bodování:** `+10 bodů` za správnou odpověď · `3 životy` · maximum `200 bodů`

---

## Funkce

- ✅ 20 realistických e-mailů v češtině (10 phishing + 10 legitimní)
- 🔀 Náhodné pořadí e-mailů při každém spuštění (Fisher-Yates shuffle)
- 💡 Okamžitý vzdělávací feedback po každé odpovědi
- ❤️ Systém životů s vizualizací pomocí emoji srdíček
- 📊 Progress bar sledující postup hrou
- 🔗 Automatické zvýraznění URL adres v těle e-mailů
- 🏆 Výsledková obrazovka s hodnocením a přehledem všech e-mailů
- 📱 Plně responzivní design (funguje na mobilu i počítači)
- 📦 Žádné závislosti — jediný HTML soubor

---

## Technologie

| Technologie | Použití |
|---|---|
| HTML5 | Struktura a sémantické značení |
| CSS3 | Styly, animace, Grid, Flexbox |
| Vanilla JavaScript ES6+ | Herní logika, DOM manipulace |
| Google Fonts | Space Mono + DM Sans |

> Projekt je záměrně napsán **bez jakýchkoliv frameworků nebo externích knihoven**. Celá aplikace běží v jediném souboru `main.html` bez nutnosti build procesu nebo instalace závislostí.

---

## Struktura projektu

```
getphished/
└── main.html       # celá aplikace (HTML + CSS + JavaScript)
```

---

## Technický přehled

Aplikace je postavena na architektuře tří obrazovek (menu → hra → výsledky). Herní stav je centralizován v jediném objektu `state`.

**Klíčové technické detaily:**

- **Fisher-Yates shuffle** — skutečně náhodné míchání e-mailů, na rozdíl od `array.sort(() => Math.random())`, které produkuje zkreslené výsledky
- **CSS Custom Properties** — centralizovaná správa barevného schématu přes `:root` proměnné
- **CSS Grid + Flexbox** — responzivní dvousloupcový layout
- **`addEventListener`** místo inline `onclick` — čistá separace logiky od HTML struktury
- **DOM caching** — reference na elementy uloženy v konstantách při inicializaci
- **Regulární výraz** — automatické zvýrazňování URL adres v textu e-mailů
- **CSS animace** — `fadeIn` / `fadeUp` / `shake` pro uživatelský prožitek

---

## Vzdělávací přínos

GetPhished! využívá princip **aktivního učení** — hráč musí sám rozhodnout a nese za rozhodnutí okamžité důsledky. Okamžitá zpětná vazba ve formě vysvětlení u každého e-mailu posiluje zapamatování mnohem efektivněji než pasivní výuka.

Hra je navržena pro:
- Středoškolské a vysokoškolské studenty
- Zaměstnance jako součást bezpečnostního školení
- Kohokoliv, kdo chce zlepšit svou odolnost vůči phishingovým útokům

---

## Licence

Tento projekt byl vytvořen jako maturitní práce a je dostupný pro vzdělávací účely.

---

<div align="center">

*Petr Přibyl · Academic School · Maturitní projekt · Vedoucí práce: Pavel Valášek*

</div>
