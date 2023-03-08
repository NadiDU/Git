# Git

Установка
* **git config** **--global user.email "Nadya.durina@gmail.com"**
* **git config** **--global user.name "Nadezhda"**
* **git config** **--global --list** - посмотреть юзера и имейл
* **ssh-keygen** - создать ssh ключ что бы подключить в гит хабе( в Settings) 
* **git clone** (ssh репозитория или URL репозитория) - клонировать репозиторий на локальный ПК
Перенос данных
* **git add** (файл, папка) или **git add** . (все элементы)- добавить элемент в поле видимости гита
* **git status** - узнать статус текущих элементов
* **git commit -m** "комментарий" - закомитить элемент
* **git commit -am** "комментарий" - добавить элемент в поле видимости гит и закомитить одной строкой
* **git pull** - стянуть данные с гит хаба на локалку и сразу вмержить в твою ветку апдейты
* **git fetch** - стянуть другие ветки с гит хаба на локалку но не мержить с имеющейся
* **git push** - скинуть данные с локалки на репозиторий
#Ветки
* **git branch NotMain** - создать ветку
* **git branch** - вывести все ветки, которые есть в репозитории
* **git checkout -b NotMain** - создать ветку и сразу на нее перейти
* **git checkout NotMain** - переход на другую ветку
* **git push -u --all** -  запушить все ветки на гит хаб (-u пишеться единожды для того чтобы сразу потом писать git push на ветке )
* **git push -u origin NotMain** - если нужно запушить одну ветку
* **git merge Foo -m "merge NotMain** - вмержить ветку NotMain в Main. Перед этим перейти в мейн git checkout main
* **git merge** (название ветки откуда забираем) -m "merge test" - мержим ветку в ту ветку в которой находимся сейчас по факту. После этого делаем git push
# Порядок действий при **Pull Request**
* **git add** - (на доп локал ветке)
* **git commit -m “”** - (на доп локал ветке)
* **git push** - (на доп ветку в гите)
* **git checkout Master** - (переход с доп локал ветки на мастер локал ветку)
* **git pull** - (залить данны с мастера на гите в мастер локал)
* **git checkout** (доп ветка) - (переход с мастер локал ветки на доп локал ветку)
* **git merge master** - (мерж в доп локал ветку с обновленной мастер локал ветики) 
коммит делать не надо (это делается автоматом)
* **git push** - (залить данные с доп локал ветки на доп ветку в гите)
* **pull request** - (мерж в мастер в гите с доп ветки в гите) 
# Git Bash
* **pwd** - посмотреть где ты сейчас
* **mkdir test** - создать папку
* **cd test** - зайти в папку
* **cd ..** - выйти с папки
* **touch file1.txt file4.json** - создать файл
* **ls-la** - вывести список содержимого папки
* **rm file1.txt file4.json test1** - переместить файлы в др. папку
* **cp file1.txt file4.json test1** - скопировать файлы в др. папку
* **nano file.txt** - редактор файлов 
* **Ctrl  O  и нажать Enter** - сохранение внесенных изменений в файл
* **Ctrl  O нажать Enter Ctrl  X** - сохранение внесенных изменений в файл и выход из редактора nano
* **Ctrl  Z** - не сохранять внесенные изменения

# Проверка настроек
* Если вы хотите проверить используемую конфигурацию, можете использовать команду **git config --list**, чтобы показать все настройки, которые Git найдёт
Основные команды git 
* **init** Позволяет проинициализировать репозиторий в текущей папке
* **git status** Показывает текущий статус 
* **git add** Отслеживает изменения файлов 
* **git add index.html** — добавляет index.html 
* **git add .** — добавляет все файлы 
* **git commit** Сохраняет изменения в коммит 
* **git commit -m** 'commit message' — создает коммит с сообщением 
* **git branch** Работа с ветками в репозитории 
* **git branch** — показывает список веток 
* **git branch branch-name** — создает новую ветку 
* **branch-name git branch -D branch-name** — удаляет ветку
* **branch-name git checkout** Переключается на другую ветку 
* **git checkout branch-name** — переключается на последний коммит в ветке 
* **branch-name git checkout -b branch-name** — создает и переключается на ветку branch-name git merge Совмещает текущую ветку с выбранной
* **git merge branch-name** — совмещает текущую ветку с branch-name git config 
* **clear** - очистить консоль

# Конфигурация и параметры git 
* **git config --global user.name** — Показывает имя пользователя 
* **git config --global user.name 'new user'** — Изменяет имя пользователя 
* **git config --global user.email** — Показывает email пользователя 
* **git config --global user.email 'test@mail.ru'** — Изменяет email пользователя 
* **git push** Заливает текущие локальные коммиты в удаленный репозиторий 
* **git pull** Забирает изменения с удаленного репозитория в локальный 
* **git clone** Клонирует проект с удаленного репозитори


# Синхронизировать ветки 

* Local Master branch is behind the remote Master branch
This means every locally created branch is behind.
Before preceding, you have to commit or stash all the changes you made on the branch behind commits.
* Solution:
* Checkout your local Master branch
* git checkout master
* Pull from remote Master branch
* git pull origin master
* Now your local Master is in sync with the remote branch. As a result of the above command, other local branches branched from the previous local Master branch are not in sync. To fix that:
* Checkout the branch that is behind your local Master branch
* git checkout BranchNameBehindCommit
* Merge with the local Master branch
* git merge master // Now your branch is in sync with the local Master branch
* If this branch is on the remote repository, you have to push your changes.
* git push origin branchBehindCommit

* В противном случае $ git push -f -u origin <name of branch>
