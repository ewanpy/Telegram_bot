# 🍪 Как получить cookies для makefilm.ai

## 🚀 Быстрый способ (рекомендуется)

### Шаг 1: Откройте браузер и авторизуйтесь
1. Откройте **Chrome** или **Safari**
2. Перейдите на **https://makefilm.ai**
3. **Авторизуйтесь** на сайте (войдите в аккаунт)

### Шаг 2: Откройте инструменты разработчика
- **Chrome**: Нажмите `F12` или `Ctrl+Shift+I` (Windows) / `Cmd+Option+I` (Mac)
- **Safari**: `Cmd+Option+I` (нужно включить меню разработчика в настройках)

### Шаг 3: Найдите cookies
1. В открывшемся окне перейдите на вкладку **"Application"** (Chrome) или **"Storage"** (Safari)
2. В левом меню найдите **"Cookies"**
3. Кликните на **"https://makefilm.ai"**

### Шаг 4: Скопируйте важные cookies
Найдите и скопируйте значения этих cookies:

| Cookie Name | Описание | Пример |
|-------------|----------|---------|
| `session_id` | Идентификатор сессии | `abc123def456` |
| `auth_token` | Токен авторизации | `eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9...` |
| `user_id` | ID пользователя | `12345` |
| `csrf_token` | Защита от CSRF | `csrf_abc123` |

### Шаг 5: Заполните шаблон
1. Откройте файл `cookies_template.json`
2. Замените значения `ВАШ_*_ЗДЕСЬ` на реальные значения из браузера
3. Сохраните файл как `cookies.json`

## 📝 Пример заполненного файла cookies.json

```json
[
  {
    "name": "session_id",
    "value": "abc123def456ghi789",
    "domain": ".makefilm.ai",
    "path": "/",
    "expires": -1,
    "httpOnly": true,
    "secure": true,
    "sameSite": "Lax"
  },
  {
    "name": "auth_token",
    "value": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiIxMjM0NSIsIm5hbWUiOiJKb2huIERvZSIsImlhdCI6MTUxNjIzOTAyMn0.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c",
    "domain": ".makefilm.ai",
    "path": "/",
    "expires": -1,
    "httpOnly": false,
    "secure": true,
    "sameSite": "Lax"
  },
  {
    "name": "user_id",
    "value": "12345",
    "domain": ".makefilm.ai",
    "path": "/",
    "expires": -1,
    "httpOnly": false,
    "secure": true,
    "sameSite": "Lax"
  }
]
```

## 🔍 Альтернативные названия cookies

Если не нашли cookies с указанными именами, поищите:

- **session_id**: `sessionid`, `PHPSESSID`, `JSESSIONID`
- **auth_token**: `access_token`, `bearer_token`, `jwt_token`
- **user_id**: `userid`, `uid`, `user`, `id`
- **csrf_token**: `csrf`, `_token`, `csrfmiddlewaretoken`

## ⚠️ Важные моменты

1. **Не публикуйте** файл `cookies.json` - он содержит ваши личные данные
2. **Обновляйте cookies** регулярно - они могут истекать
3. **Проверьте домен** - должен быть `.makefilm.ai` или `makefilm.ai`
4. **Сохраните все cookies** - даже если не знаете их назначение

## 🛠️ Проверка cookies

После создания файла `cookies.json` запустите бота и используйте команду `/status` для проверки:

```
🟢 Бот работает нормально
🟢 Браузер инициализирован  
🟢 Cookies найдены: cookies.json
⏱️ Таймаут ожидания: 300 сек
```

## 🆘 Если что-то не работает

1. **Проверьте авторизацию** - убедитесь, что вы вошли в аккаунт
2. **Обновите cookies** - возможно, они истекли
3. **Проверьте домен** - должен быть `.makefilm.ai`
4. **Добавьте больше cookies** - возможно, нужны дополнительные

---

**Готово! Теперь у вас есть cookies для работы бота.**
