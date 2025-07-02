# Návod na nasazení - Recepty z ledničky

Tento dokument popisuje různé možnosti nasazení aplikace "Recepty z ledničky" pro produkční použití.

## 🚀 Rychlé nasazení

### GitHub Pages (Doporučeno pro začátečníky)
Nejjednodušší způsob publikování zdarma:

1. **Forkněte nebo nahrajte** projekt na GitHub
2. **Přejděte** do Settings repositáře
3. **Vyberte** Pages v levém menu
4. **Nastavte** Source na "Deploy from branch"
5. **Vyberte** branch "main" a folder "/ (root)"
6. **Uložte** nastavení

Aplikace bude dostupná na: `https://[username].github.io/[repository-name]`

### Vercel (Doporučeno pro pokročilé)
```bash
# Instalace Vercel CLI
npm i -g vercel

# Nasazení
vercel

# Následujte instrukce v terminálu
```

### Netlify
1. **Přetáhněte** složku projektu na netlify.com/drop
2. **Nebo připojte** GitHub repositář pro automatické nasazení

## 🔧 Lokální vývoj

### Jednoduchý HTTP server
```bash
# Python 3
python -m http.server 8000

# Python 2
python -M SimpleHTTPServer 8000

# Node.js
npx serve .
npx http-server

# PHP
php -S localhost:8000
```

### Live reload pro vývoj
```bash
# Instalace live-server
npm install -g live-server

# Spuštění s automatickým refreshem
live-server --port=8000
```

## 🌐 Produkční konfigurace

### Web server konfigurace

#### Apache (.htaccess)
```apache
# Povolení HTTPS přesměrování
RewriteEngine On
RewriteCond %{HTTPS} off
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]

# Gzip komprese
<IfModule mod_deflate.c>
    AddOutputFilterByType DEFLATE text/html text/css text/javascript application/javascript
</IfModule>

# Cache hlavičky
<IfModule mod_expires.c>
    ExpiresActive On
    ExpiresByType text/css "access plus 1 month"
    ExpiresByType application/javascript "access plus 1 month"
    ExpiresByType image/png "access plus 1 year"
    ExpiresByType image/jpg "access plus 1 year"
    ExpiresByType image/jpeg "access plus 1 year"
    ExpiresByType image/gif "access plus 1 year"
</IfModule>
```

#### Nginx
```nginx
server {
    listen 80;
    server_name your-domain.com;
    return 301 https://$server_name$request_uri;
}

server {
    listen 443 ssl;
    server_name your-domain.com;
    
    ssl_certificate /path/to/certificate.crt;
    ssl_certificate_key /path/to/private.key;
    
    root /path/to/your/app;
    index index.html;
    
    # Gzip komprese
    gzip on;
    gzip_types text/css application/javascript text/html;
    
    # Cache nastavení
    location ~* \.(css|js|png|jpg|jpeg|gif|ico|svg)$ {
        expires 1y;
        add_header Cache-Control "public, immutable";
    }
    
    # Fallback pro SPA
    location / {
        try_files $uri $uri/ /index.html;
    }
}
```

## 🔐 Bezpečnostní konfigurace

### Content Security Policy (CSP)
Přidejte do `<head>` sekce:
```html
<meta http-equiv="Content-Security-Policy" content="
    default-src 'self';
    img-src 'self' data: blob:;
    style-src 'self' 'unsafe-inline';
    script-src 'self';
    connect-src 'self';">
```

### Security Headers
```html
<!-- Zabránění clickjacking -->
<meta http-equiv="X-Frame-Options" content="DENY">

<!-- Zabránění MIME sniffing -->
<meta http-equiv="X-Content-Type-Options" content="nosniff">

<!-- XSS ochrana -->
<meta http-equiv="X-XSS-Protection" content="1; mode=block">

<!-- Referrer policy -->
<meta name="referrer" content="strict-origin-when-cross-origin">
```

## 🤖 AI integrace pro produkci

### Google Vision API
```javascript
// Nahraďte simulaci skutečnou AI funkcí
async function analyzeImageWithVision(imageFile) {
    const base64Image = await fileToBase64(imageFile);
    
    const response = await fetch('https://vision.googleapis.com/v1/images:annotate?key=YOUR_API_KEY', {
        method: 'POST',
        headers: {
            'Content-Type': 'application/json',
        },
        body: JSON.stringify({
            requests: [{
                image: {
                    content: base64Image
                },
                features: [{
                    type: 'OBJECT_LOCALIZATION',
                    maxResults: 50
                }]
            }]
        })
    });
    
    const result = await response.json();
    return extractFoodItems(result.responses[0].localizedObjectAnnotations);
}
```

### Azure Cognitive Services
```javascript
async function analyzeImageWithAzure(imageFile) {
    const formData = new FormData();
    formData.append('image', imageFile);
    
    const response = await fetch('https://your-resource.cognitiveservices.azure.com/vision/v3.2/analyze?visualFeatures=Objects', {
        method: 'POST',
        headers: {
            'Ocp-Apim-Subscription-Key': 'YOUR_SUBSCRIPTION_KEY',
        },
        body: formData
    });
    
    const result = await response.json();
    return extractFoodItems(result.objects);
}
```

## 📊 Monitoring a analytics

### Google Analytics 4
```html
<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

### Plausible Analytics (Privacy-friendly alternativa)
```html
<script defer data-domain="yourdomain.com" src="https://plausible.io/js/script.js"></script>
```

## ⚡ Performance optimalizace

### Service Worker pro caching
Vytvořte `sw.js`:
```javascript
const CACHE_NAME = 'recepty-v1';
const urlsToCache = [
    '/',
    '/index.html',
    // Přidejte další statické soubory
];

self.addEventListener('install', event => {
    event.waitUntil(
        caches.open(CACHE_NAME)
            .then(cache => cache.addAll(urlsToCache))
    );
});

self.addEventListener('fetch', event => {
    event.respondWith(
        caches.match(event.request)
            .then(response => {
                if (response) {
                    return response;
                }
                return fetch(event.request);
            }
        )
    );
});
```

Registrace v `index.html`:
```javascript
if ('serviceWorker' in navigator) {
    navigator.serviceWorker.register('/sw.js');
}
```

### Lazy loading obrázků
```javascript
// Přidejte do stávajícího kódu
const images = document.querySelectorAll('img[data-src]');
const imageObserver = new IntersectionObserver((entries, observer) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            const img = entry.target;
            img.src = img.dataset.src;
            img.classList.remove('lazy');
            imageObserver.unobserve(img);
        }
    });
});

images.forEach(img => imageObserver.observe(img));
```

## 🔄 CI/CD Pipeline

### GitHub Actions
Vytvořte `.github/workflows/deploy.yml`:
```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    
    - name: Setup Node.js
      uses: actions/setup-node@v3
      with:
        node-version: '16'
    
    - name: Install dependencies
      run: npm ci
      
    - name: Run tests
      run: npm test
      
    - name: Build
      run: npm run build
      
    - name: Deploy to GitHub Pages
      uses: peaceiris/actions-gh-pages@v3
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./dist
```

## 🌍 Doménové nastavení

### Custom doména na GitHub Pages
1. **Vytvořte** soubor `CNAME` s vaší doménou:
```
www.recepty-z-lednicky.cz
```

2. **Nastavte DNS** u vašeho registrátora:
```
Type: CNAME
Name: www
Value: [username].github.io
```

### SSL certifikát
- GitHub Pages automaticky poskytuje SSL
- Pro vlastní hosting použijte Let's Encrypt:
```bash
# Certbot pro automatické SSL
sudo certbot --nginx -d yourdomain.com
```

## 🧪 Testování produkce

### Lighthouse audit
```bash
# Instalace Lighthouse CLI
npm install -g lighthouse

# Spuštění auditu
lighthouse https://yourdomain.com --output html --output-path report.html
```

### PageSpeed Insights
Testujte na: https://pagespeed.web.dev/

## ❗ Řešení problémů

### Časté problémy
1. **CORS chyby** - ujistěte se, že servírujete přes HTTP(S)
2. **Cache problémy** - použijte Ctrl+F5 nebo incognito režim
3. **Mobile zobrazení** - zkontrolujte viewport meta tag
4. **AI API limity** - implementujte rate limiting

### Debug módy
```javascript
// Přidejte na začátek aplikace
const DEBUG = window.location.hostname === 'localhost';
if (DEBUG) {
    console.log('Debug mode enabled');
}
```

## 📞 Podpora

Pro problémy s nasazením:
1. Zkontrolujte GitHub Issues
2. Vytvořte nový Issue s labelem "deployment"
3. Přiložte error logy a konfiguraci