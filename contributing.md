# Přispívání do projektu Recepty z ledničky

Děkujeme za váš zájem o přispívání do projektu! Vaše příspěvky pomáhají udělat aplikaci lepší pro všechny uživatele.

## 🎯 Jak můžete přispět

### Hlášení chyb
- Použijte GitHub Issues pro hlášení chyb
- Popište problém co nejdetailněji
- Přiložte screenshots pokud je to možné
- Uveďte informace o prohlížeči a zařízení

### Navrhování nových funkcí
- Nejdříve zkontrolujte existující Issues a Discussions
- Vytvořte nový Issue s labelem "enhancement"
- Popište funkci a její přínos pro uživatele
- Diskutujte návrh s komunitou

### Přispívání kódem
- Forkněte repositář
- Vytvořte nový branch pro vaši funkci
- Implementujte změny s kvalitním kódem
- Otestujte funkčnost na různých zařízeních
- Pošlete pull request

## 🛠️ Vývojářské pokyny

### Požadavky na kód
- **Čitelnost** - použijte jasné názvy proměnných a funkcí
- **Komentáře** - dokumentujte složitější logiku
- **Konzistence** - dodržujte existující styl kódu
- **Responzivita** - testujte na mobilních zařízeních

### Struktura commitů
```
typ(oblast): stručný popis změny

Detailnější popis změny, pokud je potřeba.
Vysvětlete co a proč, ne jak.

Resolves: #123
```

Typy commitů:
- `feat`: nová funkcionalita
- `fix`: oprava chyby
- `docs`: dokumentace
- `style`: formátování kódu
- `refactor`: refaktoring bez změny funkčnosti
- `test`: přidání testů
- `chore`: ostatní změny

### Testování
- Otestujte aplikaci v různých prohlížečích
- Ověřte responzivitu na mobilních zařízeních
- Kontrola accessibility (přístupnost)
- Testování edge cases (extrémní situace)

## 📋 Pull Request proces

### Před odesláním PR
1. **Synchronizujte** svůj fork s main branch
2. **Testujte** všechny změny lokálně
3. **Zkontrolujte** že nedochází ke konfliktům
4. **Aktualizujte** dokumentaci pokud je potřeba

### Popis Pull Requestu
```markdown
## Popis změn
Stručně popište co vaše změny dělají.

## Typ změny
- [ ] Oprava chyby
- [ ] Nová funkcionalita
- [ ] Dokumentace
- [ ] Refaktoring

## Testování
- [ ] Testováno na desktop
- [ ] Testováno na mobilu
- [ ] Testováno v různých prohlížečích

## Screenshots
Přiložte screenshots pokud změny ovlivňují UI.
```

### Review proces
- Všechny PR musí být reviewed
- Adresujte feedback od reviewerů
- Udržujte PR aktuální s main branch
- Buďte trpěliví během review procesu

## 🎨 Design Guidelines

### UI/UX principy
- **Jednoduchost** - intuitivní ovládání
- **Přístupnost** - použitelné pro všechny uživatele
- **Konzistence** - jednotný design jazyk
- **Performance** - rychlé načítání a odezva

### Barevná schémata
- Primární: gradientní pozadí (`#667eea` → `#764ba2`)
- Sekundární: bílá a světle šedé pro karty
- Akcenty: živé barvy pro tlačítka a tagy
- Text: tmavě šedá pro čitelnost

### Responzivní design
- Mobile-first přístup
- Breakpointy: 600px, 768px, 1024px
- Flexibilní layout pomocí CSS Grid a Flexbox
- Optimalizace pro dotykové ovládání

## 🚀 Vývoj nových funkcí

### Prioritní oblasti
1. **AI integrace** - připojení k reálným AI službám
2. **Uživatelské účty** - registrace a personalizace
3. **Databáze receptů** - rozšíření o více receptů
4. **Sociální funkce** - sdílení a hodnocení receptů

### Technické požadavky
- Žádné externí závislosti pro frontend
- Progresivní vylepšování funkcionalit
- Offline-first přístup kde je to možné
- SEO optimalizace

## 📚 Dokumentace

### Co dokumentovat
- Nové API funkce
- Změny v uživatelském rozhraní
- Konfigurační možnosti
- Nasazení a setup instrukce

### Formát dokumentace
- Markdown soubory v `/docs` složce
- Inline komentáře v kódu
- JSDoc pro JavaScript funkce
- README aktualizace pro významné změny

## 💬 Komunikace

### Kanály komunikace
- **GitHub Issues** - technické diskuze a bug reporty
- **GitHub Discussions** - obecné dotazy a nápady
- **Pull Request** komentáře - specifické feedback

### Pravidla komunikace
- Buďte respektující a konstruktivní
- Používejte angličtinu nebo češtinu
- Poskytněte konkrétní a užitečný feedback
- Buďte trpěliví s odpověďmi

## 🏆 Uznání přispěvatelů

Všichni přispěvatelé budou:
- Uvedeni v README.md
- Zmíněni v release notes
- Pozvání do přispěvatelského týmu (po více příspěvcích)

## ❓ Máte otázky?

Neváhejte se zeptat prostřednictvím:
- GitHub Issues (s labelem "question")
- GitHub Discussions
- Přímé kontaktování maintainerů

Děkujeme za váš čas a úsilí věnované tomuto projektu! 🙏