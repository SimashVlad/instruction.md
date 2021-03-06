<div align="center">
  <img src="https://media.giphy.com/media/kH6CqYiquZawmU1HI6/giphy.gif" width="300"/>
</div>

---

<div align="center">
    
# Инструкция для работы с Git и удалёнными репозиториями

</div>

В данной инструкции мы подробно ознакомимся со многими командами программы GIT и рассмотрим, как они работают. 

<div align="center">

Приятного чтения!

</div>

## Что такое Git?
***Git*** - это одна из реализаций распределённых систем контроля версий, имеющая как и локальные, так и удалённые репозитории. Является самой популярной реализацией систем контроля версий в мире.

## Установка Git
Для установки программы __*Git*__ необходимо скачать, а затем запустить установочный файл с официфльного сайта https://git-scm.com.

---

## Первая настройка

 При первом запуске необходимо представиться системе. Сделать это можно с помощью следующих команд:
 * *git config --global user.name "__Ваше имя__"*

 * *git config --global user.email "__Ваша почта__"*

 Данная процедура делается один раз, но обязательно.

Проверить успешное сохранение ваших данных можно командой:
* *git config --list*

## Подготовка репозитория
Для создания репозитория необходимо выполнить команду
* *git init*  

в папке с репозиторием и у Вас создаться репозиторий (появится скрытая папка .git)

## Просмотр состояния репозитория
Для того, чтобы посмотреть состояние репозитория используется команда
* *git status*. 

Для этого необходимо в папке с репозиторием написать *git status*, и Вы увидите были ли измения в файлах, или их не было.

## Git add
Для добавления измений в коммит используется команда *git add*. Чтобы использовать команду *git add* напишите
* *git add <имя файла>*

## Создание коммитов
Для того, чтобы создать коммит(сохранение) необходимо выполнить команду *git commit*. Выполняется она так: 
* *git commit -m "<сообщение к коммиту>*

 Все файлы для коммита должны быть ***ДОБАВЛЕНЫ*** и сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО***.

## Перемещение между сохранениями
Для того, чтобы перемещаться между коммитами, используется команда *git checkout*. Используется она в папке с репозиторием следующим образом: 
* *git checkout <номер коммита>*

## Журнал изменений
Для того, чтобы посмтреть все сделанные изменения в репозитории, используется команда 
* *git log*. 

Для этого достаточно выполнить команду *git log* в папке с репозиторием.
<div align="center">

## Ветки в Git
</div>

## Создание ветки

Для того, чтобы создать ветку, используется команда: 
* *git branch <название новой ветки>*

Делается это в папке с репозиторием.
так же можно использовать команду:
* *git checkout -b* <имя новой ветки>

данная команда позволяет создать новую ветку с одновременным переходом на неё.

## Переход по веткам
Для того чтобы перейти на созданную ветку необходимо воспользоватся командой:
* git branch <название ветки>

## Слияние веток

Для того чтобы дабавить ветку в текущую ветку используется команда:
* *git merge <имя ветки>*

## Удаление веток
Для удаления ветки ввести команду:
* *git branch -d <имя ветки>*


# Удаленные репозитории
Сейчас наш коммит является локальным — существует только в директории .git на нашей файловой системе. Несмотря на то, что сам по себе локальный репозиторий полезен, в большинстве случаев мы хотим поделиться нашей работой или доставить код на сервер, где он будет выполняться.

## Что такое удаленный репозиторий
Репозиторий, хранящийся в облаке, на стороннем сервисе, специально созданном для работы с git.

## Клонирование
Клонирование - это когда вы копируете удаленный репозиторий к себе на локальный ПК. При этом вы переносите себе все файлы и папки проекта, а также всю его историю с момента его создания. Чтобы склонировать проект, сперва, необходимо узнать где он расположен и скопировать ссылку на него в GitHub, BitBucket или любом другом сервисе:

* git clone https://*адрес репозитория*

При клонировании в текущий каталог, там будет создана папка, в которую поместятся все проектные файлы и скрытая директория .git, с самим репозиторием, или с необходимой информацией о нем. В такой ситуации, для клонируемого репозитория, по умолчанию, будет создана папка с одноименным названием, но его можно залить и в другую директорию, например:

* git clone https://*адрес репозитория* new-folder

## Подключение к удаленному репозиторию

Чтобы загрузить что-нибудь в удаленный репозиторий, сначала нужно к нему подключиться. Чтобы связать наш локальный репозиторий с репозиторием на GitHub, выполним следующую команду в терминале. 

* $ git remote add origin https://*адрес репозитория*

Проект может иметь несколько удаленных репозиториев одновременно. Чтобы их различать, мы дадим им разные имена. Обычно главный репозиторий называется origin.

## Отправка изменений на сервер

Команда, предназначенная для этого - push. Она принимает два параметра: имя удаленного репозитория (мы назвали наш origin) и ветку, в которую необходимо внести изменения (master — это ветка по умолчанию для всех репозиториев).

* $ git push -u origin master

Эта команда немного похожа на git fetch, с той лишь разницей, что при помощи fetch мы импортируем коммиты в локальную ветку, а при применив push, мы экспортируем их из локальной в удаленную. Если вам необходимо настроить удаленную ветку используйте git remote. Однако пушить надо осторожно, ведь рассматриваемая команда перезаписывает безвозвратно все изменения. В большинстве случаев, ее используют, чтобы опубликовать выгружаемые локальные изменения в центральный репозиторий. А еще ее применяют для того, чтобы поделиться, внесенными в локальный репозиторий, нововведениями, с коллегами или другими удаленными участниками разработки проекта. Подытожив сказанное, можно назвать git push - командой выгрузки, а git pull и git fetch - командами загрузки или скачивания. После того как вы успешно запушили измененные данные, их необходимо внедрить или интегрировать, при помощи команды слияния git merge.

<div align="center">
Более подробно можно ознакомится на сайте:

https://proglib.io/p/git-for-half-an-hour
</div>
