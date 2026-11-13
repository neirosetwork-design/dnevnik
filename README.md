# Дневник ритуалов — GitHub Pages

Готовая папка для бесплатного HTTPS-хостинга на GitHub Pages.

## Что внутри

- `index.html` — калькулятор процедур, он же «Дневник ритуалов».
- `spa-passport-prototype.html` — та же страница по прямому адресу.
- `spa-published-hotels.js` — список опубликованных отелей. Сейчас пустой; после публикации отелей файл нужно обновлять.

## Как выложить

1. Откройте <https://github.com/new>.
2. Создайте **публичный** репозиторий, например `spa-diary`.
3. Нажмите **Add file → Upload files** и загрузите все файлы из этой папки в корень репозитория.
4. Сделайте коммит в ветку `main`.
5. Откройте **Settings → Pages**.
6. В разделе **Build and deployment** выберите:
   - Source: **Deploy from a branch**
   - Branch: **main**
   - Folder: **/ (root)**
7. Нажмите **Save** и подождите 1–2 минуты.

Адрес будет таким:

```text
https://neirosetwork-design.github.io/dnevnik/
```

Калькулятор:

```text
https://neirosetwork-design.github.io/dnevnik/?hotel=hotel-ru#calculator
```

## Ссылка для поста

Подставьте адрес GitHub Pages в backend:

```env
CALCULATOR_URL=https://neirosetwork-design.github.io/dnevnik/
```

Backend сам добавит:

```text
?hotel=hotel-<id>#calculator
```

## Обновление отелей

После публикации нового отеля обновите `spa-published-hotels.js`:

```js
window.SPA_PUBLISHED_HOTELS = [ /* отели из backend */ ];
```

Файл можно брать из `http://95.174.93.139:3000/spa-published-hotels.js` или генерировать автоматически после публикации.

## Важно

- Репозиторий должен быть публичным для бесплатного GitHub Pages.
- Не загружайте сюда `.env`, токены и пароли.
- Для обновления файлов нужен доступ к репозиторию: collaborator или GitHub-токен с правами на репозиторий.
