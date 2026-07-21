# Публикация на GitHub Pages и Render

## Важно

Render не подключает ZIP-файл напрямую. Сначала распакуйте архив и загрузите содержимое папки проекта в корень GitHub-репозитория.

В корне репозитория должны сразу находиться:

- `render.yaml`
- `package.json`
- папка `dist`
- папка `.github`
- папки `public` и `src`

Не загружайте папку `note-lock-pwa` как дополнительную вложенную папку.

## GitHub Pages

1. Создайте репозиторий GitHub и загрузите в его корень все файлы проекта.
2. Откройте `Settings` → `Pages`.
3. В `Build and deployment` выберите `Source: GitHub Actions`.
4. Откройте вкладку `Actions` и дождитесь завершения `Deploy to GitHub Pages`.

Workflow поддерживает ветки `main` и `master` и публикует готовую папку `dist`.

## Render через Blueprint

1. В Render выберите `New` → `Blueprint`.
2. Подключите GitHub-репозиторий с проектом.
3. Blueprint Path оставьте `render.yaml`.
4. Render создаст Static Site `note-lock-pwa-static`.

Сборка не требует установки Node.js или pnpm: Render публикует готовую папку `dist`.

## Если Blueprint не импортируется

Создайте `New` → `Static Site` и укажите:

- Build Command: `echo "Using prebuilt static site"`
- Publish Directory: `dist`
- Branch: `main` или `master`

После публикации сайт работает на серверах GitHub/Render и не зависит от включённого компьютера.
