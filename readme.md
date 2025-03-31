#  Проект помошник по работе с Git

## Создание папки и файла

**создание папки**
```
mkdir <имя папки>
```

**создание файла**
```
touch <имя файла>
```

## Просмотр и редактирование файла
**просмотр файла**
```
cat <имя файла>
```

**редактирование файла**
```
nano <имя файла>
```

## Инициализация локального репозитария
```
git init

```

## Добавляем файлы в репозиторий
```
git add <--all>/<.>/<имя файла>
```

## Делаем первый коммит
```
git commit -m'Краткое описание изменений'
```

## Регистрация на GitHub
На сайте: https://github.com/ нажать sign up и ввести:
* электронную почту
* придумать пароль
* имя пользователя

## Создание удалённого репозитория
На сайте github:
* зайти в свой профиль
* перейти на вкладку Repositories
* нажать кнопку New
* Задать имя проекта
* нажать Create repository

## Генерация SSH-ключа
В терминале выполняем:
```
ssh-keygen -t ed25519 -C "электронная почта"
```
или в слчае ошибки:
```
ssh-keygen -t rsa -b 4096 -C "электронная почта"
```


## Привязываем SSH-ключ к GitHub
* копировуем в буфер содержимое созданного на предыдущем шаге файла с расширением pub
* логинимся в свой профиль на github
* в меню аккоунта выбираем Setting
* переходим в пункт SSH and GPG keys
* выбираем New SSH key
* заполняем поле Title
* в поле Key type выбираем Authentication Key
* копируем в поле Key содержиме буфера обмена
* нажимаем Add SSH key

## Связываем удалённый и локальный репозиторий
* переходим в github на страницу удалённого репозитория
* выбираем SSH (HTTPS/SSH)
* копируем url
* в консоли переходим в папку проекта
* выполняем команду:
```
git remote add origin <скопированный url>
```

## Синхронизация репозиториев
* переходим в консоль
* выполняем:
```
git push - u origin <main или master>
```
* при следующих синхронизациях выполняем без параметров:
```
git push
```

## Описание и формат файла readme.md
Файл readme.md содержит:
* название и краткое описание проекта
* применяемые технологии
* документация проекта
* планы проекта
Удобство файла заключается в структурированном отображении используя язык разметка Маркдаун

## Хеш - идентификатор коммита
Хеш - это основной идентификатор коммита содержащий информацию:
* когда был сделан коммит
* содержимое файлов в репозитории на момент коммита
* ссылка на предыдущий/родительский коммит

Основные свойства хеш:
1. хеш одного и того же набора данных гарантированно одинаковый
2. Любое изменение в исходных данных гарантированно изменяет хеш

Хеш хранится в служебных файлах в .git

## Элементы коммита - log
Вывод полного лога:
```
git log
```

Выводится информация:
* хеш коммита
* имя и электронная почта автора
* дата и время коммита
* сообщение коммита

Вывод сокращённого лога:
```
git log --oneline
```
Выводится несколько (достаточное для соблюдения уникальности) символов коммита и комментарии
Сокращённый лог полезен для поиска коммита

## Файл Head
Head - служебный файл указывающий на последний коммит 
При выполнении коммита в файл на который указывает Head записывает хеш последнего коммита
В командах git можно указать Head вместо последнего коммита

## Статусы файлов git
Основные статусы файлов в git:
* untracked - не отслеживаемый
* tracked - отслеживаемый
* staged (tracked) - в списке файлов которые войдут в коммит
* modified (tracked) - изменён относительно версии в staging

## Сообщения к коммитам
Есть общие рекомендации к составлению сообщений:
* относительно короткое, чтобы его было легко читать
* информативным
Подходы к оформлению сообщений:
* Корпоративный
"<jira-id>: Описание"
* Conventional Commits
"<type: feat/fix>: Описаие"
* GitHub-стиль
"<инфинитив/императив> <номер задачи>, Описание"


