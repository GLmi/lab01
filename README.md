## Laboratory work I

Данная лабораторная работа посвещена изучению утилит для разработки проектов

## Tasks

- [X] 1. Ознакомиться со ссылками учебного материала
- [ ] 2. Выполнить инструкцию учебного материала
- [ ] 3. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial

```bash
#Присваиваем переменной свое имя пользователя
$ export GITHUB_USERNAME=<имя_пользователя>
#Присваиваем переменной свой токен
$ export GIST_TOKEN=<сохраненный_токен>
#Биндим команду edit с вызовом редактора vim
$ alias edit=<vim>
```

```ShellSession
#Создаем дирректорию с нашим именем пользователя и со вложенной папкой workspace
$ mkdir -p ${GITHUB_USERNAME}/workspace
#Переходим в созданный каталог
$ cd ${GITHUB_USERNAME}/workspace
#Выводим полный путь до текущей дирректории
$ pwd
#Возвращаемся наверх(в предыдущую папку)
$ cd ..
#Выводим полный путь до текущей директории
$ pwd
 
```

```ShellSession
#Создаем каталоги, используя флаг -p
$ mkdir -p workspace/tasks/
$ mkdir -p workspace/projects/
$ mkdir -p workspace/reports/
$ cd workspace
```

```ShellSession
#Debian
#Скачиваем архив с последней версией nodejs
$ wget https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz
#Распаковываем в текущую директорию (создается каталог с именем файла)
$ tar -xf node-v6.11.5-linux-x64.tar.xz
#Удаляем архив
$ rm -rf node-v6.11.5-linux-x64.tar.xz
#Перемещаем каталог с nodejs в каталог node (переименовываем)
$ mv node-v6.11.5-linux-x64 node
```

```ShellSession
#Выводим содержимое директории
$ ls node/bin
#Выводим список директорий, где терминал ищет исполняемые файлы
$ echo ${PATH}
#Добавляем к переменной PATH путь до бинарных файлов nodejs
$ export PATH=${PATH}:`pwd`/node/bin
#Снова выводим его и видим, что наша директория успешно добавлена
$ echo ${PATH}
#Создаем директорию scripts
$ mkdir scripts
#Создаем в этой директории файл activate
$ cat > scripts/activate<<EOF
export PATH=\${PATH}:`pwd`/node/bin
EOF
#При помощи команды source содержимое файла будет исполнено как набор команд
$ source scripts/activate
```

```ShellSession
#Устанавливаем gistup при помощи npm
$ npm install -g gistup
#Показываем список файлов директории node/bin и убеждаемся, что все установилось корректно
$ ls node/bin
```

```ShellSession
#Создаем файл .gistup.json, где будет находится наш gist token
$ cat > ~/.gistup.json <<EOF
{
  "token": "${GIST_TOKEN}"
}
EOF
```

## Report

```ShellSession
#Добавляем переменную с номером л/р
$ export LAB_NUMBER=01
#Клонируем репозиторий с л/р в директорию tasks/lab01
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}
#Создаем директорию для хранения отчетов
$ mkdir reports/lab${LAB_NUMBER}
#Копируем README.md в директорию с отчетами и переименовываем его
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
#Переходим в директорию с REPORT.md
$ cd reports/lab${LAB_NUMBER}
#Редактируем его
$ edit REPORT.md
#Создаем gist с сообщением 'lab01'
$ gistup -m "lab${LAB_NUMBER}" # enter: yes↵
```

## Links

### Unix commands

- [ar](https://en.wikipedia.org/wiki/Ar_(Unix))
- [cat](https://en.wikipedia.org/wiki/Cat_(Unix))
- [cd](https://en.wikipedia.org/wiki/Cd_(command))
- [cp](https://en.wikipedia.org/wiki/Cp_(Unix))
- [cut](https://en.wikipedia.org/wiki/Cut_(Unix))
- [echo](https://en.wikipedia.org/wiki/Echo_(command))
- [env](https://en.wikipedia.org/wiki/Env_(shell))
- [ex](https://en.wikipedia.org/wiki/Ex_(editor))
- [file](https://en.wikipedia.org/wiki/File_(command))
- [find](https://en.wikipedia.org/wiki/Find)
- [ls](https://en.wikipedia.org/wiki/Ls)
- [man](https://en.wikipedia.org/wiki/Man_page)
- [mkdir](https://en.wikipedia.org/wiki/Mkdir)
- [mv](https://en.wikipedia.org/wiki/Mv)
- [nm](https://en.wikipedia.org/wiki/Nm_(Unix))
- [ps](https://en.wikipedia.org/wiki/Ps_(Unix))
- [pwd](https://en.wikipedia.org/wiki/Pwd)
- [rm](https://en.wikipedia.org/wiki/Rm_(Unix))
- [sed](https://en.wikipedia.org/wiki/Sed)
- [touch](https://en.wikipedia.org/wiki/Touch_(Unix))

### Package Managers

- [apt](http://help.ubuntu.ru/wiki/apt) | [dnf](https://en.wikipedia.org/wiki/DNF_(software)) | [yum](https://fedoraproject.org/wiki/Yum/ru)
- [brew](https://brew.sh) | [linuxbrew](http://linuxbrew.sh)
- [npm](https://docs.npmjs.com)

### Software

- [curl](https://www.gitbook.com/book/bagder/everything-curl/details)
- [wget](https://www.gnu.org/software/wget/manual/wget.pdf)
- [clang](https://clang.llvm.org)
- [g++](https://gcc.gnu.org/onlinedocs/gcc-4.0.2/gcc/G_002b_002b-and-GCC.html)
- [make](https://en.wikipedia.org/wiki/Make_(software))
- [open](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man1/open.1.html)
- [openssl](https://www.openssl.org)
- [nano](https://www.nano-editor.org)
- [tree](https://linux.die.net/man/1/tree)
- [vim](http://www.vim.org)

## Homework

1. Скачайте библиотеку *boost* с помощью утилиты **wget**. Адрес для скачивания `https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz`.
2. Разархивируйте скаченный файл в директорию `~/boost_1_69_0`
3. Подсчитайте количество файлов в директории `~/boost_1_69_0` **не включая** вложенные директории.
4. Подсчитайте количество файлов в директории `~/boost_1_69_0` **включая** вложенные директории.
5. Подсчитайте количество заголовочных файлов, файлов с расширением `.cpp`, сколько остальных файлов (не заголовочных и не `.cpp`).
6. Найдите полный пусть до файла `any.hpp` внутри библиотеки *boost*.
7. Выведите в консоль все файлы, где упоминается последовательность `boost::asio`.
8. Скомпилирутйе *boost*. Можно воспользоваться [инструкцией](https://www.boost.org/doc/libs/1_61_0/more/getting_started/unix-variants.html#or-build-custom-binaries) или [ссылкой](https://codeyarns.com/2017/01/24/how-to-build-boost-on-linux/).
9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию `~/boost-libs`.
10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.
11. Найдите *топ10* самых "тяжёлых".

```
Copyright (c) 2015-2019 The ISC Authors
```
