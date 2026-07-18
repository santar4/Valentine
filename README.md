# 💕 Will You Be My Valentine?

Інтерактивна веб-сторінка для запитання когось на побачення у День святого Валентина.

Проект розроблений на **Flask** з забавною інтерактивною логікою на JavaScript.

## 🎯 Особливості

- **Кнопка "No" втікає** — щоразу коли користувач намагається натиснути "No", кнопка рухається в випадкову позицію
- **Кнопка "Yes" зростає** — з кожною спробою натиснути "No", "Yes" кнопка збільшується, роблячи вибір очевидним
- **Конфетті** — коли натискають "Yes", на екран спадає конфетті
- **Падаючі серця** — анімовані серця падають зверху вниз
- **Адаптивний дизайн** — працює на мобільних та десктопних пристроях
- **Яскраво оформлено** — розовий градієнт та емодзі робить сторінку святковою

## 🛠 Технологічний стек

- **Backend**: Flask
- **Frontend**: HTML, CSS, JavaScript
- **Залежності**:
  - Flask 3.1.2
  - Gunicorn 25.0.3
  - Canvas Confetti (CDN)

## 📋 Вимоги

- Python 3.7+
- Pip

## 🚀 Встановлення та запуск

### 1. Клонуйте репозиторій
```bash
git clone https://github.com/santar4/Valentine.git
cd Valentine
```

### 2. Встановіть залежності
```bash
pip install -r requirements.txt
```

### 3. Запустіть сервер
```bash
python app.py
```

Сервер запуститься на `http://localhost:5000`

### 4. Відкрийте у браузері
Перейдіть на `http://localhost:5000` та насолоджуйтесь! 💘

## 📁 Структура проекту

```
Valentine/
├── app.py                 # Flask додаток
├── requirements.txt       # Залежності
└── templates/
    └── index.html        # Головна сторінка
└── static/
    ├── миньон-14-февраля.gif    # GIF коли чекаємо відповіді
    └── love-you-bear.gif        # GIF коли натиснута "Yes"
```

## 💻 Як це працює

### Backend (Flask)
```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def home():
    return render_template("index.html")
```

Просто повертає HTML-шаблон.

### Frontend (JavaScript)

**Функція `moveNo()`** — кнопка "No" втікає:
```javascript
function moveNo() {
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");
    
    // Випадкова позиція для "No"
    noBtn.style.left = Math.random() * maxX + "px";
    noBtn.style.top = Math.random() * maxY + "px";
    
    // "Yes" збільшується
    yesScale *= 1.25;
    yesBtn.style.transform = "scale(" + yesScale + ")";
    
    // "No" зменшується
    noScale *= 0.85;
    noBtn.style.transform = "scale(" + noScale + ")";
}
```

**Функція `yesClicked()`** — коли натиснута "Yes":
```javascript
function yesClicked() {
    // Змінюємо GIF та текст
    document.getElementById("gif").src = "love-you-bear.gif";
    document.getElementById("question").innerText = "Yea!!!!!! 💘💘💘";
    
    // Ховаємо кнопки
    document.getElementById("yesBtn").style.display = "none";
    document.getElementById("noBtn").style.display = "none";
    
    // Запускаємо ефекти
    startHearts();
    launchConfetti();
}
```

## 🎨 Налаштування

Хочете змінити текст, кольори або GIF'и? Відредагуйте `templates/index.html`:

- **Текст питання**: Знайдіть `h1` та змініть "Will you be my valentine?"
- **GIF'и**: Замініть шляхи у `document.getElementById("gif").src`
- **Кольори**: Змініть CSS змінні у `<style>`
  - `#ffe6f0` — перший колір градієнта
  - `#ff99cc` — другий колір градієнта
  - `#ff0066` — основний рожевий колір

## 🌐 Розгортання

### На Heroku
```bash
git push heroku main
```

### На інших хостингах
Використовуйте `gunicorn`:
```bash
gunicorn app:app
```

## 📝 Ліцензія

MIT License — використовуйте як вам подобається! 💖

## 🤝 Автор

Максим (santar4)

---

**Готово до запитання?** 💕 Скопіюйте посилання та надішліть улюбленій людині!
