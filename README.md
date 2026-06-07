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


# Хеш-идентификатор коммита.
## У каждого коммита есть свой хеш, он уникален для каждого коммита и учитывает малейшие изменения в файлах. Дату, содержание и тд.\

Хеш для одного и того же файла должен быть всегда один.

# `HEAD` - всему голова 
Файл HEAD - один из служебных файлов папки .git
Он указывает на коммит, который сделан последним (то есть на самый новый).

Внутри HEAD - ссылка на служебный файл: refs/heads/master.
 Если заглянуть в этот файл, можно увидеть хеш последнего коммита 

Когда вы делаете коммит, Git обновляет refs/heads/master - записывает в него хеш последнего коммита.
 Получается, что HEAD тоже обновляется, так как ссылается на refs/heads/master

## 📋 СТАТУСЫ ФАЙЛОВ GIT

### 🔍 КАК УВИДЕТЬ СТАТУС

git status          # Показать статусы всех файлов
git status -s       # Короткий формат (одна буква на файл)

### 📊 РАСШИФРОВКА СТАТУСОВ

untracked      - Файл новый, Git о нем не знает (нужно git add)
tracked        - Git знает о файле (уже был хотя бы один коммит)
modified       - Файл изменен, но не добавлен в коммит (нужно git add)
staged         - Файл добавлен в коммит (ждет git commit)
committed      - Файл сохранен в коммите (изменения зафиксированы)

### 📝 РАСШИФРОВКА КОРОТКОГО ФОРМАТА (git status -s)

?? file.txt         - untracked (новый файл)
A  file.txt         - добавлен в staged (новый файл)
M  file.txt         - изменен и добавлен в staged
 M file.txt         - изменен, но НЕ в staged (пробел перед M)
MM file.txt         - изменен и staged, потом снова изменен
D  file.txt         - удален и добавлен в staged
 D file.txt         - удален, но НЕ в staged
R  file.txt         - переименован
C  file.txt         - скопирован

### 🔄 ЖИЗНЕННЫЙ ЦИКЛ ФАЙЛА


1. untracked → git add → staged → git commit → committed

2. committed → изменить файл → modified → git add → staged

3. staged → снова изменить → modified + staged (обе версии)

4. committed → git rm → deleted → git add → staged

### ⚠️ ВАЖНЫЕ КОМАНДЫ ДЛЯ СТАТУСОВ

git add file.txt        - untracked/modified → staged

git commit -m "msg"     - staged → committed

git rm file.txt         - удалить файл (перемещает в staged)

git reset file.txt      - staged → modified (убрать из staged)

git checkout -- file    - modified → committed (отменить изменения)

git restore file.txt    - modified → committed (новый способ)

git restore --staged file.txt - staged → modified


### 💡 БЫСТРЫЕ ПРИМЕРЫ

# Создали файл

echo "text" > test.txt

git status              - untracked (?? test.txt)

# Добавили

git add test.txt

git status              - staged (A  test.txt)

# Закоммитили

git commit -m "add"

git status              - чистый (nothing to commit)

# Изменили

echo "new" >> test.txt

git status              - modified ( M test.txt)

# Добавили изменения

git add test.txt

git status              - staged (M  test.txt)

### 🎯 ГЛАВНОЕ ЗАПОМНИТЬ

untracked → нужно сделать git add (Git не следит за файлом)

modified → нужно сделать git add (Git видит изменения)

staged → нужно сделать git commit (файл готов к сохранению)

committed → всё хорошо (изменения сохранены)
