# 🔍 Как найти селекторы для готовых изображений

## 🎯 Проблема:
Бот знает, как ввести промпт и нажать кнопку генерации, но не знает, где искать готовое изображение.

## 🔧 Решение:

### Способ 1: Ручной поиск через Chrome (рекомендуется)

1. **Откройте Chrome**
2. **Перейдите на https://makefilm.ai/workspace/image-generator**
3. **Авторизуйтесь**
4. **Введите тестовый промпт:** "кот"
5. **Нажмите Generate**
6. **Дождитесь появления готового изображения**
7. **Нажмите F12**
8. **Нажмите на иконку курсора**
9. **Кликните на ссылку скачивания** или на само изображение
10. **Правый клик** на подсвеченном коде → **Copy → Copy selector**

### Способ 2: Через консоль браузера

После генерации изображения введите в консоль:

```javascript
// Найти все ссылки на изображения
console.log('Ссылки на изображения:');
document.querySelectorAll('a').forEach((link, i) => {
    const href = link.href;
    if (href && (href.includes('image') || href.includes('.jpg') || href.includes('.png'))) {
        console.log(`${i+1}. ${href}`);
    }
});

// Найти все изображения
console.log('Изображения:');
document.querySelectorAll('img').forEach((img, i) => {
    const src = img.src;
    if (src) {
        console.log(`${i+1}. ${src}`);
    }
});

// Найти кнопки скачивания
console.log('Кнопки скачивания:');
document.querySelectorAll('button, a').forEach((el, i) => {
    const text = el.innerText;
    if (text && (text.includes('Download') || text.includes('Скачать'))) {
        console.log(`${i+1}. ${text}`);
    }
});
```

### Способ 3: Автоматический поиск

Запустите скрипт для поиска селекторов:

```bash
python3 find_result_selectors.py
```

## 📝 Примеры селекторов для результатов:

### Ссылки на изображения:
```css
a[href*="image"]
a[href*=".jpg"]
a[href*=".png"]
a[href*="download"]
.download-link
.result-image a
```

### Изображения:
```css
img[src*=".jpg"]
img[src*=".png"]
.result-image img
.generated-image
```

### Кнопки скачивания:
```css
button:has-text("Download")
a:has-text("Download")
.download-btn
.save-btn
```

## 🔧 Обновление bot.py:

Найдите в файле `bot.py` строки с TODO и замените:

```python
# TODO: ВСТАВЬТЕ ПРАВИЛЬНЫЙ CSS-СЕЛЕКТОР ДЛЯ ОЖИДАНИЯ РЕЗУЛЬТАТА
result_selectors = [
    'a[href*="image"]',  # Ссылка на изображение
    'a[href*="photo"]',  # Ссылка на фото
    'a[href*="jpg"]',    # Ссылка на JPG
    'a[href*="png"]',   # Ссылка на PNG
    'a[href*="result"]', # Ссылка на результат
    '.result-link',      # Класс ссылки на результат
    '.download-link',    # Класс ссылки на скачивание
    '[data-result-url]'  # Атрибут с URL результата
]
```

На ваши реальные селекторы:

```python
result_selectors = [
    'a[href*=".jpg"]',           # Ссылка на JPG
    'a[href*=".png"]',           # Ссылка на PNG
    '.download-link',            # Класс ссылки на скачивание
    'button:has-text("Download")', # Кнопка скачивания
    '.result-image a'            # Ссылка в контейнере результата
]
```

## ⚠️ Важно:

1. **Сначала сгенерируйте изображение** вручную
2. **Найдите ссылку на готовое изображение**
3. **Скопируйте точный селектор**
4. **Обновите код бота**

**Рекомендация:** Используйте **Способ 1** с DevTools - он самый точный!
