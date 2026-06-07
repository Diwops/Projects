# My project
## 📚 GIT ШПАРГАЛКА

### 🔧 НАСТРОЙКА (один раз)
git config --global user.name Ваше Имя
git config --global user.email email@example.com
git config --global core.autocrlf true

### 🚀 НАЧАЛО РАБОТЫ
git init                                      # Создать репозиторий
git clone git@github.com:user/repo.git       # Скачать репозиторий

### 📝 РАБОТА С ФАЙЛАМИ
git status                                    # Что изменилось?
git add file.txt                              # Добавить файл
git add .                                     # Добавить все файлы
git commit -m Сообщение                     # Сохранить изменения
git rm file.txt                               # Удалить файл

### 🔄 ОТПРАВКА И ПОЛУЧЕНИЕ
git push                                      # Отправить на GitHub
git push -u origin main                       # Отправить + связать ветку
git pull                                      # Скачать + объединить
git fetch                                     # Скачать (не объединять)

### 📋 ПРОСМОТР ИСТОРИИ
git log --oneline                             # Краткая история коммитов
git log --oneline --graph                     # История с графом веток
git show                                      # Показать последний коммит
git show <hash>                               # Показать конкретный коммит
git diff                                      # Показать изменения

### 🌿 ВЕТКИ
git branch                                    # Список веток
git branch new-branch                         # Создать ветку
git checkout branch-name                      # Переключиться на ветку
git checkout -b new-branch                    # Создать и переключиться
git merge branch-name                         # Слить ветку в текущую
git branch -d branch-name                     # Удалить ветку

### ⚠️ ОТМЕНА ИЗМЕНЕНИЙ
git reset file.txt                            # Убрать из индекса (было git add)
git checkout -- file.txt                      # Отменить изменения в файле
git reset --soft HEAD~1                       # Отменить коммит (оставить изменения)
git reset --hard HEAD~1                       # Отменить коммит (удалить изменения)

### 🔗 СВЯЗЬ С УДАЛЕННЫМ РЕПОЗИТОРИЕМ
git remote add origin git@github.com:user/repo.git   # Добавить удаленный репозиторий
git remote -v                                         # Посмотреть удаленные репозитории
git remote remove origin                              # Удалить связь

### 💡 ПОЛЕЗНЫЕ КОМАНДЫ
git --version                                 # Версия Git
git help                                      # Справка
clear                                         # Очистить экран терминала
