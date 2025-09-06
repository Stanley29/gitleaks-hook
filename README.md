# 🕵️‍♂️ Gitleaks Pre-Commit Hook

Автоматичний pre-commit hook для перевірки секретів у коді за допомогою [Gitleaks](https://github.com/gitleaks/gitleaks).  
Працює локально та в CI/CD через GitHub Actions.

---

## 🚀 Можливості

- 🔒 Блокує коміти, якщо знайдено токени, паролі або ключі
- ⚙️ Автоматично встановлює Gitleaks (Windows ZIP + розпаковка)
- 🧠 Вмикається через `git config gitleaks.enable true`
- ☁️ CI/CD інтеграція через GitHub Actions
- 📦 Працює без попередньої установки Gitleaks

---

## 📦 Встановлення

1. Склонуй репозиторій:
   ``bash
   git clone https://github.com/Stanley29/gitleaks-hook.git
   cd gitleaks-hook

2. Увімкни hook:

``bash
git config gitleaks.enable true

3. Додай hook:

``bash
cp pre-commit .git/hooks/pre-commit
chmod +x .git/hooks/pre-commit


🧪 Тестування
Додай фейковий токен у код:

``python
token = "ghp_1234567890abcdef"

Спробуй закомітити:

``bash
git add .
git commit -m "Test secret"

Hook заблокує коміт і виведе:

``Code
🚨 Secrets detected! Commit blocked.


⚙️ CI/CD (GitHub Actions)
Файл: .github/workflows/gitleaks.yml 
Автоматично запускає Gitleaks при кожному push або pull request.

🏷️ Badge

![Gitleaks Scan](https://github.com/Stanley29/gitleaks-hook/actions/workflows/gitleaks.yml/badge.svg)

📁 Структура
``Code
.
├── .gitleaks.toml         # Конфігурація правил
├── pre-commit             # Hook-скрипт
└── .github/
    └── workflows/
        └── gitleaks.yml   # CI/CD інтеграція
📄 Ліцензія
MIT — використовуй, змінюй, поширюй.