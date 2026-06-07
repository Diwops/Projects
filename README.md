## 📚 GIT ШПАРГАЛКА

### 🔧 НАСТРОЙКА (один раз)

git config --global user.name "Ваше Имя"

git config --global user.email "email@example.com"

git config --global core.autocrlf true

### 🚀 НАЧАЛО РАБОТЫ

git init

git clone git@github.com:user/repo.git

### 📝 РАБОТА С ФАЙЛАМИ

git status

git add file.txt

git add .

git commit -m "Сообщение"

git rm file.txt

### 🔄 ОТПРАВКА И ПОЛУЧЕНИЕ

git push

git push -u origin main

git pull

git fetch

### 📋 ПРОСМОТР ИСТОРИИ

git log --oneline

git log --oneline --graph

git show

git show <hash>

git diff

git diff --stat

### 🌿 ВЕТКИ

git branch

git branch new-branch

git checkout branch-name

git checkout -b new-branch

git merge branch-name

git branch -d branch-name

### ⚠️ ОТМЕНА ИЗМЕНЕНИЙ

git reset file.txt

git checkout -- file.txt

git reset --soft HEAD~1

git reset --hard HEAD~1

### 🔗 СВЯЗЬ С УДАЛЕННЫМ РЕПОЗИТОРИЕМ

git remote add origin git@github.com:user/repo.git

git remote -v

git remote remove origin

### 💡 ПОЛЕЗНЫЕ КОМАНДЫ

git --version

git help

clear

### ⚠️ ВАЖНО: ВЫХОД ИЗ ПРОСМОТРА

git diff или git log открывают просмотрщик. Чтобы выйти - нажмите q