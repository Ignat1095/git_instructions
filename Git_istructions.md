# Git _инструкция_

Git - программа, одна из систем контроля версий.

## Для начала надо:
1. представиться Гиту: 


        git config --global user.name "My Name"

        git config --global user.email myEmail@example.com

2. Затем инициализировать:

        git init
***
***
## Чтобы сохранить изменения надо:
* Ввести команду: 

        git add .name 
    -git будет отслеживать новые файлы.

* а затем: 

        git commit -m "комментарий"
    -зафиксировать изменения.
* Команда объединяющая эти процессы:

        git commit -am "комментарий"

* Для полноценного процесса совместной работы в Git необходима третья команда: 

        git push

    Используется для отправки подтвержденных изменений 
    в удаленные репозитории для совместной работы, 
    чтобы к набору сохраненных изменений могли получить доступ 
    другие участники команды.

***
***
## Полезные команды которые надо запомнить:

1. Журнал всех действий, которые мы совершали:
        
        git log 
        git log --graph
        git log --all

        git reflog

2. Позволяет перемещаться между ветками: 

        git checkout

* Перемещение на __один__ коммит назад git checkout... :
        
        ^ # на один коммит
        main^ # первый родитель ветки
        main^^ # прародитель ветки
        HEAD^ # перемещение назад по коммитам
        HEAD~4 # перемещение на 4 коммита

        git branch -f main HEAD~3 # Переместит (принудительно) ветку main на три родителя назад от HEAD.

* Перемещение на несколько коммитов назад 

        ~<num>

* Позволяет создать ветку и сразу переместиться на нее:

        git checkout -b name_brunch

3. Показывает изменения между любыми двумя Git деревьями:

        git diff

4. Для отмены коммита:

        git reset # отменяет изменения, перенося ссылку на ветку назад, на более старый коммит.
        git revert # отмена для удаленных веток.

5. Слияние ветки, чтобы **собрать воедино разветвленную историю**:

* **ВАЖНО** - Команда вызывается от туда, куда хотим добавить изменения:

        git merge branch name

* Копирование и перенос коммитов в другую ветку:
        
        git rebase name_branch

* Прервать/откатить слияние:

        git merge --abort

6. Для удаления веткии: 

        git branch -d "branch name"

7. Для изменения <span style="color:yellow">цвета</span>:

                <span style="color:green">Create fork</span>
***
*** 
## Команды для удаленного репозитория

1. Чтобы залить свой репозиторий на GitHub нужно:

* Команда для создания записи о новом подключении к удаленному репозиторию:

       git remote add origin link

* Обозначаем главгую ветку как main:

        git branch -M main

* Отправить __локальный__ репозиторий на __удаленный__ репозиторий:

        git push
        git push -u origin main

* Выкачать актуальное состояние из __удаленного__ репозитория: 

        git pull
        git pull --rebase # 

1. Копирование удаленного репозитория себе в локальный:

        git clone 

2. Переход в чужой репозиторий, который скачали:

        cd name_folder
***
***
## Папка для файлов, которые нам не нужно  отображать

* Нужно создать файл **.gitignore** и в этом файле указать название файла с расширением.
