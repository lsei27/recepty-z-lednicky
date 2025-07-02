# Bezpečnostní pravidla

## 🔒 Hlášení bezpečnostních zranitelností

Bezpečnost našich uživatelů je pro nás prioritou. Pokud objevíte bezpečnostní zranitelnost v aplikaci "Recepty z ledničky", prosíme vás o odpovědné nahlášení.

### 📧 Jak nahlásit zranitelnost

**Prosíme, NEHLASTE bezpečnostní zranitelnosti přes veřejné GitHub Issues.**

Místo toho:
1. **Pošlete email** na: [security@your-domain.com] (nahraďte vaším emailem)
2. **Nebo použijte GitHub Security Advisory** na privátní hlášení
3. **Uveďte** co nejvíce detailů o zranitelnosti

### 📋 Co zahrnout do hlášení

- **Typ zranitelnosti** (např. XSS, CSRF, injection, atd.)
- **Umístění** zranitelnosti v kódu
- **Kroky k reprodukci** bezpečnostního problému
- **Potenciální dopad** zranitelnosti
- **Návrhy na opravu** (pokud je máte)

### ⏱️ Časová lhůta odpovědi

- **48 hodin** - potvrzení přijetí hlášení
- **7 dní** - prvotní analýza a hodnocení
- **30 dní** - oprava a vydání bezpečnostní aktualizace

## 🛡️ Podporované verze

| Verze | Podporována |
| ----- | ----------- |
| 1.0.x | ✅ |
| < 1.0 | ❌ |

## 🔐 Bezpečnostní opatření v aplikaci

### Frontend bezpečnost
- **Content Security Policy (CSP)** - ochrana proti XSS
- **Input sanitization** - čištění uživatelských vstupů
- **HTTPS only** - šifrovaná komunikace
- **No inline scripts** - prevence injection útoků

### Zpracování obrázků
- **File type validation** - pouze povolené formáty
- **File size limits** - ochrana proti DoS
- **Client-side processing** - žádné nahrávání na server v demo verzi
- **No EXIF data exposure** - ochrana soukromí

### Data privacy
- **No server storage** - obrázky se zpracovávají pouze lokálně
- **No tracking** - žádné sledování uživatelů v základní verzi
- **No cookies** - minimalizace dat

## 🚨 Známé bezpečnostní aspekty

### Demo verze
- Současná verze používá simulaci AI - **žádná real AI integrace**
- Obrázky se **nezpracovávají na serveru** - pouze lokálně v prohlížeči
- **Žádná perzistence dat** - vše se smaže po zavření prohlížeče

### Produkční implementace
Pro produkční nasazení s real AI doporučujeme:
- **Rate limiting** pro API volání
- **API key rotation** pro AI služby
- **Input validation** na backend serveru
- **Logging a monitoring** bezpečnostních událostí

## 🔧 Bezpečnostní konfigurace

### Doporučené HTTP hlavičky
```
X-Content-Type-Options: nosniff
X-Frame-Options: DENY
X-XSS-Protection: 1; mode=block
Strict-Transport-Security: max-age=31536000; includeSubDomains
Content-Security-Policy: default-src 'self'; img-src 'self' data: blob:
Referrer-Policy: strict-origin-when-cross-origin
```

### Browser kompatibilita
- **Modern browsers only** - bezpečnostní funkce vyžadují aktuální prohlížeče
- **Feature detection** - graceful degradation pro starší verze
- **Progressive enhancement** - základní funkcionalita bez JS

## 📚 Bezpečnostní zdroje

### Pro vývojáře
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [MDN Web Security](https://developer.mozilla.org/en-US/docs/Web/Security)
- [CSP Reference](https://content-security-policy.com/)

### AI/ML bezpečnost
- [AI Security Best Practices](https://www.nist.gov/itl/ai-risk-management-framework)
- [ML Privacy Guidelines](https://developers.google.com/machine-learning/guides/responsible-ai)

## 🏆 Uznání bezpečnostních reportérů

Uznáváme a děkujeme následujícím osobám za odpovědné nahlášení bezpečnostních problémů:

*(Tato sekce bude aktualizována s budoucími reporty)*

## 📞 Kontakt

Pro bezpečnostní dotazy:
- **Email**: [security@your-domain.com]
- **PGP Key**: [link na veřejný klíč]
- **Response Time**: 48 hodin

---

**Poslední aktualizace**: 2025-07-02