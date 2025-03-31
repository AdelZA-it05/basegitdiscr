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
