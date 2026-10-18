DRYLINE ROOFING CO. — сайт-концепт

Файли
  public/index.html   головна сторінка (весь сайт в одному файлі)
  public/404.html     сторінка «не знайдено»
  public/favicon.svg  іконка вкладки
  public/_headers     заголовки безпеки й noindex для Cloudflare
  wrangler.jsonc      налаштування Cloudflare Workers

Як подивитися локально
  python tools/serve.py 5501 і відкрийте http://localhost:5501
  (сервер поводиться як Cloudflare: адреси без .html і власна сторінка 404).
  Потрібен інтернет: 3D-бібліотека (three.js з jsDelivr) і шрифти (Google Fonts) вантажаться з CDN.

Як викласти на Cloudflare
  Збірка не потрібна, Cloudflare віддає папку public як є; README, tools і wrangler.jsonc на сайт не потрапляють.
  1. Запуште цю папку в порожній репозиторій на GitHub.
  2. dash.cloudflare.com → Workers & Pages → Create → Import a repository → цей репозиторій.
  3. Project name: dryline-site (має збігатися з "name" у wrangler.jsonc).
     Build command: порожньо. Deploy command: npx wrangler deploy
  4. Deploy. Сайт з'явиться на адресі dryline-site.<ваш-акаунт>.workers.dev.
  Свій домен: у wrangler.jsonc поставте "workers_dev": false і додайте
  "routes": [{ "pattern": "домен", "custom_domain": true }].
  Посилання на 404-сторінці ведуть на "/", тож сайт має лежати в корені домену.

Важливо
  Dryline — вигадана компанія. Ціни, відгуки, дані про град, адреси й телефони
  (555-0xxx) — зразки. Футер сайту прямо каже, що це концепт; залиш цю примітку,
  якщо показуєш сайт як роботу в портфоліо.
  Тому сайт закритий від пошуковиків (X-Robots-Tag: noindex у public/_headers),
  щоб вигадана компанія не з'являлась у Google серед справжніх покрівельників.
