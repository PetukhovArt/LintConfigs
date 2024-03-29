## Настройка Linters & Husky pre-commit
## ESLint конфиг на основе AirBnb JS/TS

1. ### До момента устранения всех ошибок ESLint, не устанавливать/не включать husky pre-commit)
2. Установка расширений (предварительно вставить зависимости в package.json):
   - `npm install`
   - Установите необходимые dev зависимости из package.json файла соответствующего проекта (react-ts / vue-js / ....)
3. Скопируйте в свой проект:
   - .eslintrc.json из соответствующего проекта в корневую папку своего проекта
   - дополните своей package.json кодом из package.json файла соответствующего проекта
   - скопируйте файлы .prettierrc.json, .stylelintrc.json, .prettierignore, .eslintignore из папки all-projects-files в корневую папку своего проекта
4. файл watchers.xml - утилка для автоматического линтинги css /scss файлов
   - в IDE Webstorm подключается в settings > tools > filewatchers
   - делаем импорт данного файла и включаем styleint, styleint scss
5. Устранить появляющиеся ошибки импортов/ необходимых зависимостей
6. Для VSCode необходимо установить и включить расширения prettier , eslint, styleint
7. Для VSCode необходимо настроить файл settings.json
8. Запустить линтеры : npm run lint , npm run format
9. Проанализировать ошибки , при появлении каких-либо ошибок, которые уже очень сложно исправить , сообщайте в группу TG , будем обсуждать изменение конфигов > далее отладка > запуск на живых проектах
10. После утверждения конечных конфигов и устранения всех ошибок, установить/включить husky и гит хуки и проверить работоспособность husky pre-commit , должен запрещать сделать push при наличии ESLint error :
- `npm i lint-staged --save-dev`
- `npx husky-init && npm install`
- `npx husky add .husky/pre-commit "npx lint-staged"`
- В папке husky -> pre-commit ->  закомментировать npm test (если у вас нет тестов в проекте)
- Специально оставить/создать одну ESLint ошибку для проверки работоспособности husky

### Конфиг оттестирован : **react-ts (vite)**

