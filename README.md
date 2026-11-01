<div align="center">

# ⚡ TaskFlow

**Мінімалістичний To-Do менеджер для тих, хто живе в терміналі.**

[![Build Status](https://img.shields.io/github/actions/workflow/status/username/taskflow/ci.yml?branch=main&style=for-the-badge&logo=github)](https://github.com/username/taskflow/actions)
[![npm version](https://img.shields.io/npm/v/taskflow-cli?style=for-the-badge&logo=npm&color=cb3837)](https://www.npmjs.com/package/taskflow-cli)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=for-the-badge)](CONTRIBUTING.md)
[![Made with Node.js](https://img.shields.io/badge/Node.js-18+-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org)

[Демо](#-демо) · [Встановлення](#-встановлення) · [Використання](#-використання) · [Roadmap](#-roadmap) · [Contributing](#-як-долучитися)

</div>

---

## 📖 Зміст

- [Чому TaskFlow?](#-чому-taskflow)
- [Демо](#-демо)
- [Можливості](#-можливості)
- [Встановлення](#-встановлення)
- [Використання](#-використання)
- [Команди](#-команди)
- [Конфігурація](#️-конфігурація)
- [Структура проєкту](#-структура-проєкту)
- [Roadmap](#-roadmap)
- [Як долучитися](#-як-долучитися)
- [Ліцензія](#-ліцензія)

## 🚀 Чому TaskFlow?

Більшість to-do застосунків — це десятки екранів, акаунти й підписки. TaskFlow робить одне: **додає, показує й закриває задачі за секунду**, не виводячи вас із терміналу.

> 💡 *«Найкращий таск-менеджер — той, яким ти справді користуєшся.»*

## 🎬 Демо

![TaskFlow demo](docs/demo.gif)

> GIF-демо можна записати за допомогою [asciinema](https://asciinema.org/) + [agg](https://github.com/asciinema/agg) або [ScreenToGif](https://www.screentogif.com/) і покласти у `docs/demo.gif`.

## ✨ Можливості

- ⚡ **Швидкість** — запуск менше ніж за 100 мс
- 🏷️ **Теги та пріоритети** — `high`, `medium`, `low`
- 📅 **Дедлайни** — природна мова: `tomorrow`, `next friday`
- 💾 **Локальне сховище** — усе в одному JSON-файлі, жодних акаунтів
- 🎨 **Кольоровий вивід** — з підтримкою світлої й темної тем
- 🔌 **Експорт** — у JSON, CSV та Markdown

## 📦 Встановлення

### Через npm

```bash
npm install -g taskflow-cli
```

### З вихідного коду

```bash
git clone https://github.com/username/taskflow.git
cd taskflow
npm install
npm link
```

### Перевірка

```bash
taskflow --version
# taskflow v1.0.0
```

## 🛠️ Використання

Швидкий старт за три кроки:

```bash
# 1. Додати задачу
taskflow add "Здати лабораторну з Git" --priority high --due tomorrow

# 2. Переглянути список
taskflow list

# 3. Позначити виконаною
taskflow done 1
```

Приклад виводу:

```text
 ID  Статус  Пріоритет  Задача                      Дедлайн
 1   ⏳      high       Здати лабораторну з Git     02.11.2026
 2   ✅      low        Прочитати документацію      —
```

## 📋 Команди

| Команда | Опис | Приклад |
|---------|------|---------|
| `add <text>` | Додати нову задачу | `taskflow add "Купити молоко"` |
| `list` | Показати всі задачі | `taskflow list --tag work` |
| `done <id>` | Позначити виконаною | `taskflow done 3` |
| `edit <id>` | Змінити задачу | `taskflow edit 3 --priority low` |
| `rm <id>` | Видалити задачу | `taskflow rm 3` |
| `export <format>` | Експорт даних | `taskflow export csv` |

### Опції

| Прапорець | Скорочено | Значення за замовчуванням | Опис |
|-----------|-----------|---------------------------|------|
| `--priority` | `-p` | `medium` | Пріоритет: `high` / `medium` / `low` |
| `--due` | `-d` | — | Дата виконання |
| `--tag` | `-t` | — | Тег задачі |
| `--no-color` | — | `false` | Вимкнути кольори |

## ⚙️ Конфігурація

Налаштування зберігаються у `~/.taskflow/config.json`:

```json
{
  "theme": "dark",
  "dateFormat": "DD.MM.YYYY",
  "defaultPriority": "medium"
}
```

<details>
<summary>📂 Де зберігаються дані?</summary>

| ОС | Шлях |
|----|------|
| Linux / macOS | `~/.taskflow/tasks.json` |
| Windows | `%USERPROFILE%\.taskflow\tasks.json` |

</details>

## 🗂️ Структура проєкту

```text
taskflow/
├── .github/
│   └── workflows/
│       └── ci.yml
├── docs/
│   └── demo.gif
├── src/
│   ├── commands/
│   ├── storage.js
│   └── index.js
├── tests/
├── CONTRIBUTING.md
├── LICENSE
├── package.json
└── README.md
```

## 🗺️ Roadmap

- [x] Базові команди `add`, `list`, `done`, `rm`
- [x] Пріоритети й теги
- [x] Експорт у JSON/CSV
- [ ] Підтримка підзадач
- [ ] Синхронізація через GitHub Gist
- [ ] Інтерактивний TUI-режим
- [ ] Плагіни

Повний список планів — на [GitHub Projects](https://github.com/username/taskflow/projects).

## 🤝 Як долучитися

Ми раді будь-якому внеску!

1. Зробіть **Fork** репозиторію
2. Створіть гілку: `git checkout -b feature/amazing-feature`
3. Закомітьте зміни: `git commit -m "feat: add amazing feature"`
4. Запуште гілку: `git push origin feature/amazing-feature`
5. Відкрийте **Pull Request**

Докладніше — у [CONTRIBUTING.md](CONTRIBUTING.md). Для повідомлень комітів використовуємо [Conventional Commits](https://www.conventionalcommits.org/).

## 👥 Автори

| [<img src="https://github.com/username.png" width="80" alt="avatar"><br><sub>@username</sub>](https://github.com/username) |
|:---:|
| 💻 Розробка · 📖 Документація |

## 📄 Ліцензія

Розповсюджується під ліцензією **MIT**. Деталі — у файлі [LICENSE](LICENSE).

---

<div align="center">

Зроблено з ❤️ на курсі з Git та GitHub

⭐ Якщо проєкт вам сподобався — поставте зірку!

</div>
