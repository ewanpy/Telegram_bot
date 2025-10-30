# 🖼️ Поиск CSS-селекторов для генератора изображений

## 🎯 Целевая страница: https://makefilm.ai/workspace/image-generator

### Способ 1: Ручной поиск через Chrome DevTools

1. **Откройте Chrome**
2. **Перейдите на https://makefilm.ai/workspace/image-generator**
3. **Авторизуйтесь** (если нужно)
4. **Нажмите F12** (или `Cmd + Option + I`)

#### Для поля ввода промпта:
1. **Нажмите на иконку курсора** в DevTools
2. **Кликните на поле ввода** текста (где пишете описание изображения)
3. **Правый клик** на подсвеченном коде
4. **Copy → Copy selector**

#### Для кнопки генерации:
1. **Кликните на кнопку** "Generate" или "Create Image"
2. **Правый клик** на подсвеченном коде
3. **Copy → Copy selector**

#### Для ссылок на результаты:
1. **Сгенерируйте тестовое изображение**
2. **Кликните на ссылку** скачивания или просмотра
3. **Copy → Copy selector**

### Способ 2: Через консоль браузера

1. **Откройте консоль** (F12 → Console)
2. **Введите команды** для поиска элементов:

```javascript
// Поиск полей ввода
console.log('Поля ввода:');
document.querySelectorAll('input, textarea, [contenteditable="true"]').forEach((el, i) => {
    console.log(`${i+1}. ${el.tagName} - placeholder: "${el.placeholder}" - class: "${el.className}"`);
});

// Поиск кнопок
console.log('Кнопки:');
document.querySelectorAll('button').forEach((el, i) => {
    console.log(`${i+1}. "${el.innerText}" - class: "${el.className}"`);
});

// Поиск ссылок на изображения
console.log('Ссылки на изображения:');
document.querySelectorAll('a[href*="image"], a[href*="jpg"], a[href*="png"]').forEach((el, i) => {
    console.log(`${i+1}. ${el.href}`);
});
```

### Способ 3: Общие селекторы для try

Если не можете найти точные селекторы, попробуйте эти:

#### Поля ввода:
```css
input[type="text"]
textarea
[contenteditable="true"]
input[placeholder*="prompt"]
input[placeholder*="describe"]
input[placeholder*="text"]
.prompt-input
.text-input
#prompt
#text-input
```

#### Кнопки:
```css
button[type="submit"]
button:has-text("Generate")
button:has-text("Create")
button:has-text("Submit")
button:has-text("Generate Image")
.generate-btn
.create-btn
.submit-btn
#generate
#create
#submit
```

#### Ссылки на результаты:
```css
a[href*="image"]
a[href*="jpg"]
a[href*="png"]
a[href*="gif"]
a[href*="webp"]
a[href*="result"]
a[href*="download"]
.download-link
.result-link
.image-link
.result-image a
```

### Способ 4: Поиск по тексту

1. **F12 → Elements**
2. **Ctrl+F** (поиск в коде)
3. **Введите ключевые слова:**
   - "prompt" - для поля ввода
   - "generate" - для кнопки генерации
   - "image" - для ссылок на изображения
4. **Посмотрите на структуру** найденных элементов

### Пример найденных селекторов:

```python
# Поле ввода (пример)
prompt_input_selector = 'input[placeholder="Describe your image..."]'

# Кнопка генерации (пример)
generate_button_selector = 'button[data-testid="generate-button"]'

# Ссылка на результат (пример)
result_selectors = [
    'a[href*=".jpg"]',
    'a[href*=".png"]',
    '.result-image a',
    '.download-link'
]
```

### Способ 5: Автоматический анализ

Запустите скрипт для автоматического анализа:

```bash
python3 analyze_generator.py
```

**Рекомендация:** Используйте **Способ 1** с DevTools - он самый точный для конкретной страницы генератора изображений!
