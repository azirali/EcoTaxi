# EcoTaxi

<p align="center">
  <a href="https://github.com/azirali/EcoTaxi/actions/workflows/ci.yml"><img src="https://github.com/azirali/EcoTaxi/actions/workflows/ci.yml/badge.svg?branch=main" alt="CI"></a>
  <a href="https://ecotaxi-mu.vercel.app"><img src="https://img.shields.io/badge/Live_demo-Vercel-000000?logo=vercel&logoColor=white" alt="Live demo"></a>
  <img src="https://img.shields.io/badge/React-19-61DAFB?logo=react&logoColor=black" alt="React 19">
  <img src="https://img.shields.io/badge/Vite-8-646CFF?logo=vite&logoColor=white" alt="Vite 8">
  <img src="https://img.shields.io/badge/Tailwind_CSS-4-06B6D4?logo=tailwindcss&logoColor=white" alt="Tailwind 4">
</p>

**Live demo:** https://ecotaxi-mu.vercel.app

Интерактивный прототип мобильного приложения пассажира сервиса экологического
такси. Собран в Figma Make, работает как обычное React-приложение.

Прототип **демонстрационный**: интерфейс и переходы между экранами реальные,
данные — заглушки, серверной части нет.

## Запуск

```bash
pnpm install
pnpm dev
```

Сборка: `pnpm build` → `dist/`

Требования указаны в `.mise.toml` (Node.js и pnpm).

## Стек

React 19 · TypeScript 5.7 · Vite 8 · Tailwind CSS v4

## Что внутри

22 экрана, покрывающие полный сценарий поездки:

| Группа | Экраны |
|---|---|
| Запуск и вход | splash, onboarding, ввод телефона, код из SMS, имя |
| Заказ | главная с картой, поиск адреса, маршрут, выбор тарифа, подтверждение |
| Поездка | поиск водителя, водитель назначен, водитель прибыл, поездка идёт, завершение |
| Разделы | история поездок, детали поездки, экология, профиль, оплата, уведомления, поддержка |

## Структура

```
index.html          HTML-оболочка Vite
src/main.tsx        точка входа, монтирует App в #root
src/App.tsx         все экраны и навигация между ними
src/index.css       Tailwind v4 и глобальные стили
src/imports/        изображения и исходное описание дизайна
vite.config.ts      Vite + React + Tailwind + плагины Figma Make
AGENTS.md           заметки по проекту для ИИ-ассистентов
```

Вся логика находится в одном файле `src/App.tsx` — так его выгружает Figma Make.
При переходе к рабочей версии экраны стоит разнести по отдельным компонентам.
