# 🍳 Recepty z ledničky

Webová aplikace pro vytváření zdravých receptů na základě fotografií obsahu vaší ledničky. Využívá umělou inteligenci k rozpoznání ingrediencí a navrhuje rychlé recepty připravitelné do 20 minut.

![Recepty z ledničky](https://img.shields.io/badge/status-ready-brightgreen) ![License](https://img.shields.io/badge/license-MIT-blue) ![Tech](https://img.shields.io/badge/tech-HTML%2BCSS%2BJS-orange)

## ✨ Hlavní funkce

- **📸 Nahrání 2 fotografií** - hlavní část ledničky + dvířka pro kompletní analýzu
- **🤖 AI rozpoznávání ingrediencí** - automatická detekce potravin z fotografií
- **👩‍🍳 Inteligentní recepty** - zdravé recepty maximálně do 20 minut
- **🏠 Přizpůsobeno domácnosti** - počítá s běžným vybavením a kořením
- **📱 Responzivní design** - funguje na počítačích i mobilech

## 🎯 Pro koho je aplikace určena

- **Domácí kuchaři** hledající inspiraci z dostupných ingrediencí
- **Zaneprázdněné rodiny** potřebující rychlé a zdravé recepty
- **Osoby dbající na zdravý životní styl** - bez smažených pokrmů
- **Každý, kdo chce efektivně využít obsah ledničky**

## 🔧 Technické požadavky

### Minimální požadavky
- Moderní webový prohlížeč (Chrome, Firefox, Safari, Edge)
- Připojení k internetu (pro produkční verzi s AI)
- Zařízení s fotoaparátem (pro mobilní použití)

### Podporované spotřebiče
- Elektrický sporák, trouba, mikrovlnná trouba
- Horkovzdušná parní fritéza
- Mixér, tyčový mixér
- Elektrický kontaktní gril, toastovač

## 🚀 Rychlý start

### 1. Stažení a spuštění
```bash
git clone https://github.com/[username]/recepty-z-lednicky.git
cd recepty-z-lednicky
```

### 2. Otevření aplikace
- Otevřete soubor `index.html` v prohlížeči
- Nebo spusťte lokální server:
```bash
# Python 3
python -m http.server 8000

# Node.js
npx serve .
```

### 3. Použití aplikace
1. **Nahrajte fotografie** - hlavní část ledničky + dvířka
2. **Klikněte na analýzu** - aplikace rozpozná ingredience
3. **Prozkoumejte recepty** - vyberte si z navržených možností
4. **Vařte a užívejte si!** 🍽️

## 📖 Jak aplikace funguje

### Rozpoznávání ingrediencí
Aplikace analyzuje nahrané fotografie a detekuje:
- **Čerstvé potraviny** - zelenina, maso, mléčné výrobky
- **Základní suroviny** - automaticky přidává koření, olej, těstoviny
- **Mražené potraviny** - počítá s obsahem mrazáku

### Generování receptů
- **Filtrování podle času** - maximálně 20 minut přípravy
- **Zdravé stravování** - vyvarování se smažených pokrmů
- **Využití spotřebičů** - recepty přizpůsobené vašemu vybavení
- **Kombinace chutí** - vyvážené použití koření a bylinek

## 🎨 Screenshoty

```
┌─────────────────────────────────────┐
│  🍳 Recepty z ledničky              │
│  ─────────────────────────────────  │
│                                     │
│  📸 Vyfotografujte obsah ledničky   │
│  💡 Tip: 2 fotografie pro lepší    │
│      rozpoznání                     │
│                                     │
│  [📷 Foto 1: Hlavní část]          │
│  [🚪 Foto 2: Dvířka]               │
│                                     │
│  ┌─────────────┐ ┌─────────────┐   │
│  │   Foto 1    │ │   Foto 2    │   │
│  └─────────────┘ └─────────────┘   │
│                                     │
│  [🔍 Analyzovat fotografie]        │
└─────────────────────────────────────┘
```

## 🏗️ Architektura

### Frontend
- **HTML5** - sémantická struktura
- **CSS3** - moderní design s gradientem a animacemi
- **Vanilla JavaScript** - bez závislostí na frameworku

### AI simulace (současná verze)
- Náhodné generování ingrediencí pro demo účely
- Připraveno pro integraci s AI službami

### Produkční implementace
Pro plnou funkcionalnost doporučujeme integraci s:
- **Google Vision API** - rozpoznávání objektů
- **Azure Cognitive Services** - analýza obrázků
- **Backend API** - zpracování a ukládání dat

## 🛠️ Vývoj a přispívání

### Struktura projektu
```
recepty-z-lednicky/
├── index.html          # Hlavní aplikace
├── README.md          # Dokumentace
├── LICENSE            # MIT licence
├── CONTRIBUTING.md    # Návod pro přispěvatele
└── docs/             # Dodatečná dokumentace
    └── DEPLOYMENT.md # Návod na nasazení
```

### Přispívání
1. **Fork** repositáře
2. **Vytvořte branch** pro vaši funkcionalitu
3. **Implementujte změny** s testy
4. **Pošlete pull request**

Více informací v [CONTRIBUTING.md](CONTRIBUTING.md)

## 📋 Roadmapa

### Verze 1.1 (Q3 2025)
- [ ] Integrace s reálnou AI službou
- [ ] Uložení oblíbených receptů
- [ ] Export nákupního seznamu

### Verze 1.2 (Q4 2025)
- [ ] Registrace uživatelů
- [ ] Hodnocení receptů
- [ ] Komunitní recepty

### Verze 2.0 (2026)
- [ ] Mobilní aplikace
- [ ] Hlasové ovládání
- [ ] Personalizace podle diet

## 🤝 Komunita a podpora

- **GitHub Issues** - hlášení chyb a nové funkce
- **Discussions** - dotazy a diskuze
- **Wiki** - rozšířená dokumentace

## 📄 Licence

Tento projekt je licencován pod MIT licencí - viz [LICENSE](LICENSE) soubor pro detaily.

## 👥 Autoři

- **Váš název** - *Původní vývojář* - [GitHub profil](https://github.com/username)

## 🙏 Poděkování

- Inspirováno moderními trendy ve zdravém stravování
- Navrženo pro skutečné potřeby domácích kuchařů
- Testováno na reálných domácnostech

---

⭐ **Líbí se vám projekt? Dejte nám hvězdičku!** ⭐