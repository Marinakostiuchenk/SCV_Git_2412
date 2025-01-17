![logo](2560px-Git-logo.png)
# Работа с Git
## 1. Проверка наличия установленного Git
В терминале необходимо выполнить команду `Git version.`

Если Git установлен, появится сообщение с информацией о версии программы. Иначе будет сообщение об ошибке.

## 2. Установка Git
загружаем последнюю версию Git с сайта https://git-scm.com/downloads.
Устанавливаем с настройками по умолчанию.

## 3. Настройка Git

При первом использовании Git необходимо представиться. Для этого нужно ввести в терминале два команды:
```
git config --global user.name «Ваше имя английскими буквами»
git config --global user.email ваша почта@example.com
```

## 4. Инициализация репозитория.

Для того, чтобы работать с репозиторием, нужно к этому подготовить, а уже потом выполнять в нем изменения. В этом поможет команда:

```
git init
```

## 5. Проверка статуса Git

Статус показывает:

* в какой ветке мы сейчас находимся;
* есть ли какие-то изменения в Git, чтобы их сохранить;
* показывает общее состояние всего дерева.

Для этого необходима команда:

```
git status
```

## 6. Добавление файла и сохранение

Для того, чтобы добавить изменения - необходимо использовать команду ***git add***. 
Чтобы создать коммит - ***git commit -m “message”***.
Также можно использовать эти команды вместе:
```
git commit -am "Комментарий о проделанных изменениях"
```

## 7. Вывод списка всех сохранений

Осуществляется благодаря команде:
```
git log или git log --oneline
```
Например: 

>b7db47a (HEAD -> master) Пункт 4 - Инициализация
d665c8b Добавили раздел 3 - Настройка Git
e22779d Добавили раздел 2
e62edd0 Добавили раздел 1 - Проверка наличичя установленного Git
c78a29f Добавили заголовок
49f1905 Сохранение

## 8. Переход от одного коммита к другому

Осуществляется с помощью команды:
```
git checkout "Название коммита, к которому необходимо перейти"
```
Все команды можно найти в презентации к уроку -> [здесь](https://gb.ru/lessons/290433)

## 9. Определение разницы между файлами

![Как это выглядит в терминале](/Users/marinavojtisina/Desktop/git/Снимок экрана 2022-12-16 в 15.30.08.png)

### Сама команда выглядит так: 
```
git diff
```

## 10. Запись изменений в репозитории
## 11. Просмотр истории коммитов
## 12. Перемещение между сохранениями
## 13. Игнорирование файлов
Для того, чтобы исключить отслеживание в репозитории определенные файлы и папки, необходимо создать там файл ***.gitignore*** и записать в него их название или шаблоны, соответствующие этим файлам или папкам.

## 14. Создание веток и переключение между ними в Git

Текущая ветка отмечена будет звездочкой: **\*master**
Создать ветку ожно командой:
```
git branch <имя новой ветки>
```
В результате создется новый указатель на текущий коммит.

Ветка в Git - это простой перемещаемый указатель на один из коммитов, обычно последний в цепочке коммитов.
По умолчанию имя основной ветки в Git - *master*.
Список веток в репозитории можно посмотреть с помощью команды `git branch`.

Для того, чтобы переместится из одной ветки в другую, необходимо ввести команду:
```
git checkout <имя ветки>
```

## 15. Слияние веток и разрешение конфликтов
Для слияния выбранной ветки с текущей - нужно выполнить команду:
```
git merge <название выбранной ветки>
```
Конфликт случается, если в разных ветках были сохранены разные данные в одном и том же блоке. Тогда предлагает выбор вариантов решения конфликта: выбрать первый вариант, второй вариант, их слияние.

## 16. Удаление веток

Для того, чтобы удалить ветку, используется следующая команда:
```
git branch -d <имя ветки>
```
Чтобы удалить ветку, даже если в ней имеются не сохраненные данные - нужно вместо **-d** написать ту же букву, но заглавную **-D**.

## 17. Когда забыли ввести комментарий к коммиту
Если ошибочно появился встроенный редактор, то необходимо дописать сообщение к коммиту:
<Текст сообщения
Далее нужно поставить двоеточией и написать *wq*:
<:wq
Таким образом мы выйдем в привычный терминал.

## 18. Добавить все изменения
Чтобы не добавлять изменения пошагово - есть команда для сохранения всех последних изменений сразу в .gitignore:
```
git add .gitignore
```

## 19. Лайфхак две функции в одной: создать и переключиться на ветку
Для того, чтобы одновременно выполнить несколько функций:
1. Создать ветку
2. Переключиться в только что созданную ветку
применяется команда:
```
git checkout -b <имя новой ветки>
```
# Работа с удаленными репозиториями

* Для того, чтобы работать с удаленным репозиторием - нужно зайти на GitHub и сохранить себе его версию, нажатием **fork**.

* Для работы с репозиторием в VS необходимо клонировать репозиторий, используя команду: 
```
git clone <ссылка со страницы GitHub>
```

* Перемещение между папками выполняет команда:
```
cd <имя директории>
```

* Работа с репозиторием желательна в новой ветке и при создании нового файла, куда будут подгружаться изменения.

* Команда *git push* используется для выгрузки содержимого локального репозитория в удаленный и пишется в конце работы в VS следующим образом:
```
git push -u origin <название ветки, где были внесены изменения>
```
После чего можно отправлять репозиторий на GitHub.

* При принятии измененного репозитория, необходимо нажать кноку *pull request* на GitHub, чтобы извлечь и загрузить содержимое из принятого измененного репозитория, а также обновления локального репозитория этим содержимым. 
*Конец инструкции*