# 🎉 Бот готов к работе с правильными селекторами!

## ✅ Что обновлено:

1. **🎯 URL изменен** на: `https://makefilm.ai/workspace/image-generator`
2. **📝 Селекторы обновлены** на точные с сайта:
   - **Поле ввода:** `body > div > div > div.flex-1.flex.flex-col > main > div > div > div > div.px-8.pt-1 > div > div > div.p-4.pb-12 > textarea`
   - **Кнопка генерации:** `body > div > div > div.flex-1.flex.flex-col > main > div > div > div > div.px-8.pt-1 > div > div > div.absolute.bottom-3.right-4.flex.items-center.gap-3 > button.inline-flex...`
3. **🔄 Добавлены альтернативные селекторы** на случай, если основные не сработают

## 🚀 Что нужно сделать:

### 1. Получить токен Telegram бота:
1. Найдите **@BotFather** в Telegram
2. Отправьте `/newbot`
3. Следуйте инструкциям
4. Скопируйте полученный токен

### 2. Настроить токен в .env:
```env
TELEGRAM_TOKEN=ваш_токен_здесь
MAKEFILM_COOKIES_PATH=cookies.json
TIMEOUT_SECONDS=300
```

### 3. Запустить бота:
```bash
python3 bot.py
```

## 📱 Использование:

1. **Отправьте `/start`** боту
2. **Отправьте промпт** для изображения:
   - "Создай фото котика в саду"
   - "Нарисуй закат над морем"
   - "Портрет девушки в стиле аниме"
3. **Дождитесь результата** - бот вернет ссылку на изображение

## 🔍 Альтернативные селекторы:

Если основные селекторы не сработают, бот попробует:

### Для поля ввода:
- `textarea`
- `div.p-4.pb-12 textarea`
- `input[type="text"]`

### Для кнопки:
- `div.absolute.bottom-3.right-4 button`
- `button.bg-gradient-to-r.from-blue-600`
- `button:has-text("Generate")`

## ⚠️ Важно:

- **Cookies уже настроены** ✅
- **Селекторы обновлены** ✅
- **URL правильный** ✅
- **Осталось только токен** 🔑

## 🎯 Следующий шаг:

Получите токен у @BotFather и вставьте его в файл `.env`, затем запустите бота!

**Бот готов для генерации изображений на makefilm.ai!**
