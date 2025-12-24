# Задание на конвертацию страниц в Tailwind CSS

## Общее описание
Нужно конвертировать оставшиеся HTML-страницы из старого дизайна (styles.css) в новый дизайн на Tailwind CSS.

**КРИТИЧЕСКИ ВАЖНО: НЕ менять текст! Только применить стили.**

## Готовые шаблоны (использовать как образец)

### Для county-страниц:
`/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/bergen-county.html`

### Для city-страниц:
Нужно создать на основе county-шаблона, но упрощённый вариант.

---

## Файлы для конвертации

### County-страницы (3 шт.):
1. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/morris-county.html`
2. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/essex-county.html`
3. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/passaic-county.html`

### City-страницы Bergen (5 шт.):
1. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/bergen/hackensack.html`
2. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/bergen/paramus.html`
3. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/bergen/fort-lee.html`
4. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/bergen/englewood.html`
5. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/bergen/teaneck.html`

### City-страницы Hudson (5 шт.):
1. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/hudson/jersey-city.html`
2. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/hudson/hoboken.html`
3. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/hudson/bayonne.html`
4. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/hudson/north-bergen.html`
5. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/hudson/union-city.html`

### City-страницы Morris (5 шт.):
1. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/morris/morristown.html`
2. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/morris/parsippany.html`
3. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/morris/dover.html`
4. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/morris/denville.html`
5. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/morris/madison.html`

### City-страницы Essex (5 шт.):
1. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/essex/newark.html`
2. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/essex/montclair.html`
3. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/essex/bloomfield.html`
4. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/essex/maplewood.html`
5. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/essex/livingston.html`

### City-страницы Passaic (5 шт.):
1. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/passaic/paterson.html`
2. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/passaic/clifton.html`
3. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/passaic/wayne.html`
4. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/passaic/passaic-city.html`
5. `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/passaic/little-falls.html`

---

## Правила конвертации

### 1. Head секция
Заменить:
```html
<link rel="stylesheet" href="../styles.css">
```

На:
```html
<script src="https://cdn.tailwindcss.com"></script>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=Source+Sans+3:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<script>
    tailwind.config = {
        theme: {
            extend: {
                colors: {
                    'brand': {
                        50: '#fffbeb',
                        100: '#fef3c7',
                        200: '#fde68a',
                        300: '#fcd34d',
                        400: '#fbbf24',
                        500: '#f59e0b',
                        600: '#d97706',
                        700: '#b45309',
                    }
                },
                fontFamily: {
                    'display': ['"DM Serif Display"', 'Georgia', 'serif'],
                    'body': ['"Source Sans 3"', 'system-ui', 'sans-serif'],
                }
            }
        }
    }
</script>
<style>
    .gradient-text {
        background: linear-gradient(135deg, #f59e0b 0%, #fbbf24 50%, #f59e0b 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
    }
</style>
```

### 2. Body
```html
<body class="bg-slate-950 text-slate-300 font-body">
```

### 3. Навигация в dropdown
Для текущего county добавить активный стиль:
```html
<a href="morris-county.html" class="block px-4 py-2 text-brand-500 bg-slate-800/50">Morris County</a>
```
Остальные:
```html
<a href="bergen-county.html" class="block px-4 py-2 text-slate-300 hover:text-white hover:bg-slate-800/50 transition-colors">Bergen County</a>
```

### 4. Hero с gradient-text
```html
<h1 class="font-display text-4xl md:text-5xl lg:text-6xl text-white mb-6">
    Handyman Services in <span class="gradient-text">Morris County</span>, New Jersey
</h1>
```

### 5. FAQ - использовать details/summary
```html
<details class="bg-slate-900 border border-slate-800 rounded-xl group">
    <summary class="flex items-center justify-between p-6 cursor-pointer list-none">
        <span class="text-white font-medium">Question text here?</span>
        <svg class="w-5 h-5 text-brand-500 transform group-open:rotate-180 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"/></svg>
    </summary>
    <div class="px-6 pb-6 text-slate-400">
        Answer text here.
    </div>
</details>
```

### 6. Пути для city-страниц
City-страницы находятся в подпапках, поэтому пути к ресурсам:
- `../../index.html` - главная
- `../../services/tv-mounting.html` - сервисы
- `../bergen-county.html` - county
- `../bergen/hackensack.html` - другой город того же county

---

## Порядок работы

1. Прочитать шаблон `bergen-county.html`
2. Прочитать файл для конвертации
3. Применить структуру шаблона, сохранив ВЕСЬ оригинальный текст
4. Записать результат

**Рекомендация:** Обрабатывать файлы группами:
- Сначала 3 county-страницы
- Потом city-страницы по округам (5 городов за раз)

---

## Чек-лист для каждого файла

- [ ] Head секция с Tailwind CDN
- [ ] Body с правильными классами
- [ ] Header с мобильным меню
- [ ] Breadcrumbs с правильными путями
- [ ] Hero с gradient-text для названия локации
- [ ] Все секции контента
- [ ] FAQ на details/summary
- [ ] Форма CTA
- [ ] Footer
- [ ] Mobile menu script в конце body
- [ ] Весь оригинальный текст сохранён
