# HeroGame
HeroGame - интерактивная работа с git. Направленная на изучение основных команд для работы с git.

![](/hero.jpg)

## Начало работы
1. Зарегистрироваться на GitHub.
2. Для изучения команд git, необходимо установить Git Bash.
    Скачать его можно [здесь].
   
[здесь]: https://git-scm.com/downloads

## Шаги
1. Создать папку, в которой будет Ваш будующий "проект" - HeroGame
2. Открыть папку в cmd или git bash
3. Ввести свои данные используя команды *git config*:
    ```
    git config --global user.name "ivangor"
    git config --global user.name "goryachev@mephi3.ru"
    ```

    ![](/photo/git_config.png)
   
4. Инициализировать локальный репозиторий в этой папке:
    ```
    git init
    ```
    
    ![](/photo/git_init.png)

3. Создать текстовый документ в папке с названием *hero.txt*:
   
   ![](/photo/txt_create.png)
   
4. Добавить первую строку в *hero.txt* - имя персонажа/героя, например:

    ![](/photo/1abzac.png)

5. Перейти в cmd или git bash и добавить в индекс созданный документ:
   
    ```
    git add hero.txt
    ```
  
6. Сохранить изменения в репозитории:

    ```
    git commit -m "Hero name"
    ```
    
    ![](/photo/commit1.png)
  
7. Добавить еще 4 характеристики вашему персонажу, например:
    
    ![](/photo/2abzac.png)
    
    ![](/photo/commit2.png)
    
    ![](/photo/3abzac.png)
    
    ![](/photo/commit3.png)
    
    ![](/photo/4abzac.png)
    
    ![](/photo/commit4.png)
    
    ![](/photo/5abzac.png)
    
    ![](/photo/commit5.png)
    
5. Посмотреть status репозитория:
    ```
    git status
    ```
    ![](/photo/git_status.png)
6. Создать еще один текстовый документ, в котором будет храниться карта, по которой будет передвигаться персонаж - *map.txt*:

    ![](/photo/txt_create2.png)
8. Внести файл в индекс и сохранить изменения:
    ```
    git add map.txt
    git commit -m "map-render"
    ```
    ![](/photo/commit7.png)
9. Посмотреть протокол коммитов с помощью команды:
    ```
    git log
    ```
    ![](/photo/git_log.png)
10. Посмотреть изменения в файле по сравнению с последним сохранением:
    ```
    git diff HEAD~1 map.txt
    ```
     ![](/photo/git_diff.png)
11. Уберем изменения относительно последнего сохранения файла *map.txt*:
    ```
    git checkout -- map.txt
    ```
    
12. Посмотрим существующие ветки:
    ```
    git branch
    ```
    
    ![](/photo/git_branch.png)
13. Создадим новую ветку *hero-move*:
    ```
    git branch hero-move
    ```
    ![](/photo/branch_create.png)
14. Переключимся на эту ветку с помощью команды:
    ```
    git checkout hero-move
    ```
    ![](/photoes/git_checkout2.png)
15. Создадим еще одну ветку и сразу же переключилась на нее с помощью команды:
    ```
    git checkout -b map-render
    ```
    ![](/photo/git_checkout_b.png)
16. Удалим ранее созданную ветку *map-render* с помощью команды:
    ```
    git branch -d map-render
    ```
    ![](/photo/branch_del.png)
17. Выполним слияние двух веток с помощью команды:
    ```
    git merge hero-move
    ```
    ![](/photo/git_merge.png)
19. Попробуем создать конфликт при помощи следующих действий:
    Сначала переключимся на ветку *hero-move*:
    ```
    git checkout hero-move
    ```
    Изменим файл *map.txt*, добавив название карты: "Forest"

    ![](/photo/conflict1.png)

    Добавим в индекс и сохраним изменения:
    ```
    git add map.txt
    git commit -m "map forest (branch hero-move)"
    ```
    ![](/photo/conflict2.png)

    Теперь переключимся на основную ветку - *master*:
    ```
    git checkout master
    ```
    Изменим файл *map.txt*, стерев надпись "Map: Forest", и, добавив надпись: "Map: Desert"
    
    ![](/photo/conflict3.png)
    
    Добавим в индекс и сохраним изменения:
    
    ```
    git add map.txt
    git commit -m "map desert (branch master)"
    ```
    ![](/photo/conflict4.png)

    Попытался выполнить слияние:
      
    ```
    git merge hero-move
    ```
    
    ![](/photo/conflict5.png)

    Как мы видим у нас **конфликт**.
    
21. Посмотрим в каких файлах есть конфликты при помощи команды:
    ```
    git status
    ```
    
    ![](/photo/git_status2.png)
    
23. Устраним конфликт, выполнив следующие действия:
    Так выглядит текстовый документ *map.txt* при конфликте:
    
    ![](/photo/txt_map.png)

    Стерем разметку *Git* и оставим карту "Desert":
    
    ![](/photo/conflict_remove1.png)
    
    Добавим в индекс и сохраним изменения:
    
    ```
    git add map.txt
    git commit -m "solved conflict with map.txt"
    ```
    ![](/photo/conflict_remove2.png)
19. Переключимся на указанное сохранение:
    ```
    git checkout b7c0c2c
    ```
    ![](/photo/b7c0c2c.png)
18. Интегрирует фиксации:
    ```
    git rebase hero-move
    ```

    ![](/photo/rebase.png)
18. Удалим ветку *hero2*, которую предварительно создадим:
    ```
    git branch hero2
    git branch -d hero2
    ```

    ![](/photo/rebase.png)
19. Попробуем пропустить текущий коммит во время процесса rebase:
    ```
    git rebase --skip
    ```
    ![](/photo/rebase_skip.png)
20. Теперь отправим изменения из локального репозитория для указанной ветки в удаленный (дистанционный):

    Создадим репозиторий на GitHub
    Отправим при помощи команд:
    ```
    git remote add origin https://github.com/GorIvanisp401/herogame.git
    git branch -M main
    git push -u origin main
    ```
    
    ![](/photo/git_remote.png)
22. Заберем изменения из репозитория, для которого были созданы удаленные ветки по умолчанию:
    ```
    git pull origin main
    ```

    ![](/photo/git_pull.png)
23. Заберем изменения удаленной ветки из репозитория основной ветки по умолчанию:
    
24. Клонируем репозиторий при помощи команды:
    ```
    git clone https://github.com/GorIvanisp401/herogame.git
    ```

    ![](/photo/git_clone.png)

    У нас появится новые файлы в папке:

    ![](/photo/git_clone2.png)
