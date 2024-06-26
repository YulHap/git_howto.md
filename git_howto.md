# Подсказка по Git

## Что такое Git и для чего он нужен?
Git - это консольная утилита, для отслеживания и ведения истории изменения файлов. Чаще всего его используют для кода, но можно и для других файлов.
С помощью Git можно перемещаться между разными версиями файла, сравнивать эти версии и анализировать изменения.

## Как установить Git на компьютер?
Для работы с Git нужно установить Git и Visual Studio Code (VSCode).

 [Ссылка для установки Git для Windows, MAC, Linux](https://git-scm.com/downloads "Ссылка для установки Git")

 [Ссылка для установки VSCode для Windows, MAC, Linux](https://code.visualstudio.com/Download "Ссылка для установки VSCode")

 После установки необходимо «представиться» системе контроля версий. Это нужно сделать всего один раз, и git запомнит вас. Для этого нужно ввести в терминале 2 команды:

 ```sh
git config --global user.name "Ваше имя англ буквами"

```
```sh
git config --global user.email ваша почта@example.com
```
Данные не проверяются, то есть вы можете указать любую почту и любое имя. Но лучше написать реальные данные или, как минимум что-то осмысленное. Эти данные будут указываться, когда вы будете делать коммиты, а указание реальных данных упростит командную работу.

## Что такое репозиторий?
Репозиторий - это хранилище кода и истории его изменений. 

## Где хранятся репозитории?
Git работает локально и все репозитории хранятся в определенных папках на жестком диске. Так же репозитории можно хранить и в интернете. Обычно для этого используют различные сервисы, например:
* GitHub
* Bitbucket
* GitLab.

## Создание репозитория:

Для **создания реппозитория** необходимо выполнить команду *git init* в папке с реппозиторием и у Вас создастся kjrfkmysq репозиторий (появится скрытая папка .git).
```sh
git init 
```
Теперь Git отслеживает изменения файлов вашего проекта. Но, так как вы только создали репозиторий в нем нет вашего кода. Для этого необходимо создать commit.

## Что такое коммит?
Каждая точка сохранения проекта носит название коммит (commit). У каждого commit-a есть hash (уникальный id) и комментарий. Из таких commit-ов собирается ветка. Ветка - это история изменений. У каждой ветки есть свое название. Репозиторий может содержать в себе несколько веток, которые создаются из других веток или вливаются в них.

## Создание коммитов

Для **добавления изменений в коммит** используется команда *git add* 
```sh
git add <имя файла>
```

Для **просмотра состояния репозитория** необходимо в папке с репозиторием написать команду *git status*. Станет видно были ли изменения в файлах.
```sh
git status
```

Для **создания коммита (сохранения)** используется команда *git commit* с добавлением сообщения о том, что ихменилось или добавилось в файле.
```sh
git commit -m "Сообщение"
``` 
Для **просмотра всех созданных коммитов** с присвоенными им уникальными хеш-кодами используется команда *git log* (для просмотра полной информации о коммитах) и *git log --oneline* (для просмотра краткой информации о коммитах).
```sh
git log
git log --oneline
```
Для **перемещения между версиями файла** используется команда *git checkout* с указанием хеш-кода коммита, к которому необходимо перейти.
```sh
git checkout <хеш-код коммита>
```
Для того, чтобы **вернуться к актуальному состоянию файла и продолжить работу**, используется команда *git checkout master*
```sh
git checkout master
```

Для того, чтобы **увидеть разницу между текущим файлом и закоммиченным файлом**, используется команда *git diff*.
```sh
git diff
```
## Команды для работы с ветками

Для того, чтобы **увидеть все существующие ветки**, используется команда *git branch*. Активной является та ветка, название которой написано зеленым цветом и помечена звездочкой (* branch_name).
```sh
git branch
```

Для **создания новой ветки** используется команда *git branch <имя_новой_ветки>*.
```sh
git branch <имя_новой_ветки>
```
Для **перемещения между ветками** используется команда *git checkout <имя_ветки>*. При этом указывается имя той ветки, на которую необходимо переключиться.
```sh
git checkout <имя_ветки>
```
Для **слияния веток** используется команда *git merge <имя_ветки>*. При этом перед слиянием необходимо перейти в ту ветку, в которую необходимо добавить всю новую информацию из другой ветки. 
```sh
git merge <имя_ветки>
```

Для **удаления ветки** используется команда *git branch -d <имя_ветки>*. 
```sh
git branch -d <имя_ветки>
```
## Как игнорировать файлы 
Чтобы Git **игнорировал файл** (например, фото), необходимо создать в папке файл с названием ".gitignore" с точкой в начале без пробелов. После этого закоммитить файл .gitignore.

## Очистка терминала
Для того, чтобы **очистить терминал**, используется команда *clear*.

## Работа с удаленными репозиториями

Репозитории бывают:
* локальные (находятся на нашем компьютере)
* удаленные (не на нашем компьютере).

Для работы с удаленными репозиториями необходимо:

1. Создать аккаунт в сервисе для работы с удаленными репозиториями. Мы будем работать с сервисом GitHub. 
2. Создать локальный репозиторий.
3. "Подружить" локальный и удаленный репозитории. *GitHub при создании нового репозитория даст подсказки как это сделать*.
4. Отправить **(push)** локальный репозиторий в удаленный (на GitHub). Возможно необходимо будет авторизоваться на удаленном репозитории. 
5. Провести изменения с "другого компьютера".
6. Выкачать **(pull)** актуальное состояние из удаленного репозитория.

## Команды для работы с удаленным репозиторием:

Для того, чтобы **скопировать (склонироваль) внешний репозиторий на наш ПК**, используется комианда *git clone* с указанием ссылки на удаленный репозиторий (адрес репозитория), которую можно скопировать на GitHub (кнопка Code).
```sh
git clone <адрес_репозитория>
```

Для того, чтобы наш **локальный репозиторий синхронизировался с удаленным репозиторием**, т.е. скачал все из удаленного репозитория в локальный, используется команда *git pull*. Эта команда составная - она не только подгрузит все изменения с GitHub, но и слить наши ветки. 

```sh
git pull
```

Для того, чтобы **отправить нашу версию локального репозитория на внешний (удаленный) репозиторий**, используется команда *git push*. Трубает авторизации на внешнем репозитории при первом использовании.
```sh
git push
```
*git pull* забирает изменения с сервера, а *git push* - выталкивает изменения на сервер.

### Как сделать pull request

1. Сделать fork (ответвление) репозитория

    Если мы хотим поучаствовать в проекте, то сначала мы должны сделать свою *отдельную копию с помощью кнопки Fork*. У нас появится точно такой же репозиторий, только уже на своем аккаунте в GitHub. 

2. Делаем *git clone* своей версии репозитория 
(забираем репозиторий из нашего аккаунта в GitHub в наш локальный компьютер)

3. Создаем новую ветку и в нее вносим свои изменения
    
    Когда мы хотим внести/предложить изменения в чей-то проект, нужно всегда делать это в отдельной ветке. Создаем файл (обычно его называют *README.md*) и вносим туда свои изменения. Если файл README.md уже есть, то вносим изменения в него, не забывая о том, что мы должны работать (вносить изменения) только в новой созданной ветке.
4. Фиксируем изменения (делаем коммиты)
5. Отправляем свою версию в свой GitHub (*git push*)

    В GitHub среди веток появится наша новая ветка, а также появится кнопка *Compare & pull request*.

6. На сайте GitHub нажимаем на кнопку *pull request*.

## Основная ветка в GitHub и на локальном компьютере

В GitHub основаня ветка называется *main*, а на локальных компьютерах - *master*. Для переименования ветки *master* на *main*, можно использовать команду 
```sh
git branch -M main
```



