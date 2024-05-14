# Шапргалка по GIT
## Введение
Git — это система контроля версий, которая помогает отслеживать изменения в проекте. Этот инструмент можно использовать как для индивидуальной, так и для командной работы.
<br>
В этом документе приведена простейшая последовательность действий для создания публичного проекта, используя инструменты Git.

## Git for Windows
Для управления Git-проектами из под клиента с ОС Windows удобно использовать программный продукт [Git for Windows](https://git-scm.com/download/win).
<br>
После установки программы можно начать пользоваться специальной консолью Git Bash.
<br>
Попробуйте открыть консоль и выполнить первую команду
<br>
``` Bash
$ pwd
```
## Инициализация локального репозитория GIT
Создайте каталог для хранения проекта..
``` Bash
$ mkdir -p ~/dev/AboutGit
$ cd ~/dev/AboutGit/
```
Инициализируйте git-репозиторий
``` Bash
$ $ git init
```
## Создание первого файла в проекте
Через консоль создайте файл описания проекта README.md
``` Bash
$ touch README.md
```
Откройте файл любым текстовым редактором (удобно пользоваться Notepad++) и наполните файл содержанием, используя Markqown-синтаксис.

## Проверка статуса репозитория
Войдите в директорию проекта и по команде **git status** проверьте статус репозитория
``` Bash
$ cd ~/dev/AboutGit/
$ git status
```

увидим что-то вроде:

``` Bash
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md

nothing added to commit but untracked files present (use "git add" to track)
```

Состояние *untracked* значит, что Git ещё не хранит информацию о версиях файла и не может отследить, как он изменялся.

## Готовим файлы проекта для коммита
``` Bash
$ git add --all
```
## Делаем первый коммит
``` Bash
$ git commit -m 'Добавили описание в проект'
```
## Вносим изменения в проект и делаем новый коммит
Через текстовый редактор меняем содержимое файла README.md. Сохраняем файл.
<br>
Обновляем данные для коммита и делаем новый коммит
``` Bash
$ git add --all
$ git commit -m 'Обновили описание в проект'
```
## Просмотрим историю коммитов
``` Bash
$ git log

commit 00dc93400fbadaa98bc3fc25976f3f3bc5c1afee (HEAD -> master)
Author: _leb <lebedev.tmn@gmail.com>
Date:   Tue May 14 17:54:33 2024 +0300

    Обновили описание в проект

commit 587ee309e89dafb8ae494ce027dcb01499456017
Author: _leb <lebedev.tmn@gmail.com>
Date:   Tue May 14 17:46:53 2024 +0300

    Добавили описание в проект
```
## Регистрируем удаленный репозиторий на GitHub
GitHub — платформа для хранения IT-проектов и совместной работы над ними с использованием Git. По сути, это сайт, куда можно загрузить файлы своего проекта для обмена с другими людьми.
<br>
Практические шаги по регистрации удаленного репозитория:..
1. Зайдите в свой профиль по ссылке https://github.com/username, где username — имя, которое вы указали при регистрации.
1. Создайте репозиторий. Для этого перейдите на вкладку Repositories (англ. «репозитории»), а затем нажмите на зелёную кнопку New (англ. «новый») справа.
1. Открылось окно создания нового репозитория. Назовите его AboutGit. Нажимайте на зелёную кнопку **Create repository** (англ. «создать репозиторий») внизу.
<br>
Готово! Удалённый репозиторий создан. Страница с ним открывается автоматически. 
## Привязываем удалённый репозиторий к локальному
```Bash
$ cd ~/dev/AboutGit
$ git remote add origin git@github.com:Anatoliy-Lebedev/AboutGit.git 
```
## Убедимся, что репозитории связаны
```Bash
$ git remote -v
origin  git@github.com:Anatoliy-Lebedev/AboutGit.git (fetch)
origin  git@github.com:Anatoliy-Lebedev/AboutGit.git (push)
```
В выводе вы должны увидеть две строчки, аналогичные тем, что показаны выше.
## Синхронизируем локальный и удалённый репозитории
```Bash
$ git push -u origin master
```
При следующих итерациях отправки обновлений на удаленный репозиторий достаточно выполнять команду
```Bash
$ git push
```
В ответ на эту инструкцию будем видеть примерно следующее
```Bash
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 530 bytes | 530.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:Anatoliy-Lebedev/AboutGit.git
   39a4ae1..35898b7  master -> master

```





