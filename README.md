## Laboratory work I

Данная лабораторная работа посвещена изучению утилит для разработки проектов

## Tasks

- [X] 1. Ознакомиться со ссылками учебного материала
- [X] 2. Выполнить инструкцию учебного материала
- [ ] 3. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial

```bash
#Присваиваем переменной имя пользователя
$ export GITHUB_USERNAME=GLmi
#Присваиваем переменной токен
$ export GIST_TOKEN=<...>
#Присваиваем вызов vim при использовании команды edit
$ alias edit=<vim>
```

```ShellSession
# Создаем дирректорию с GITHUB_USERNAME с дочерним каталогом workspace
$ mkdir -p ${GITHUB_USERNAME}/workspace
# Переходим в созданный каталог
$ cd ${GITHUB_USERNAME}/workspace
# Выводим адрес текущей дирректории
$ pwd
/home/vb/GLmi
# Подниманемся в /home/vb
$ cd ..
# Выводим адрес текущей директории
$ pwd
/home/vb/GLmi
```

```ShellSession
# Создаем каталоги (флаг "-p" позволяет создать недостающие каталоги)
$ mkdir -p workspace/tasks/
$ mkdir -p workspace/projects/
$ mkdir -p workspace/reports/
$ cd workspace
```

```ShellSession
# Linux
# Скачиваем архив с nodejs
$ wget https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz
# Распаковываем в текущую директорию
$ tar -xf node-v6.11.5-linux-x64.tar.xz
# Удаляем архив с nodejs
$ rm -rf node-v6.11.5-linux-x64.tar.xz
# Переименовываем каталог nodejs в каталог node
$ mv node-v6.11.5-linux-x64 node
```

```ShellSession
# Выводим содержимое директории
$ ls node/bin
node  npm
# Выводим список директорий с установленными программами
$ echo ${PATH}
/usr/local/sbin:/usr/local/bin:/usr/bin:/usr/bin/site_perl:/usr/bin/vendor_perl:/usr/bin/core_perl
# Добавляем к переменной PATH путь до бинарных файлов созданного каталога node
$ export PATH=${PATH}:`pwd`/node/bin
# Проверим успешность изменения
$ echo ${PATH}
/usr/local/sbin:/usr/local/bin:/usr/bin:/usr/bin/site_perl:/usr/bin/vendor_perl:/usr/bin/core_perl:pwd/node/bin
# Создаем директорию scripts
$ mkdir scripts
# Создаем в этой директории файл activate
$ cat > scripts/activate<<EOF
export PATH=\${PATH}:`pwd`/node/bin
EOF
# При помощи команды source содержимое файла будет исполнено как набор команд
$ source scripts/activate
```

```ShellSession
# Устанавливаем gistup при помощи npm
$ npm install -g gistup
# Показываем список файлов директории node/bin и убеждаемся, что все установилось корректно
$ ls node/bin
gistup  gistup-open  gistup-rename  node  npm
```

```ShellSession
# Создаем файл .gistup.json, где будет находится наш gist token
$ cat > ~/.gistup.json <<EOF
{
"token": "${GIST_TOKEN}"
}
EOF
```

## Report

```ShellSession
# Добавляем переменную с номером л/р
$ export LAB_NUMBER=01
# Клонируем репозиторий с л/р в директорию tasks/lab01
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}
# Создаем директорию для хранения отчетов
$ mkdir reports/lab${LAB_NUMBER}
# Копируем README.md в директорию с отчетами и переименовываем его
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
# Переходим в директорию с REPORT.md
$ cd reports/lab${LAB_NUMBER}
# Редактируем его
$ edit REPORT.md
# Создаем gist с сообщением 'lab01'
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
$ wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
2. Разархивируйте скаченный файл в директорию `~/boost_1_69_0`
$ tar -xf boost_1_69_0.tar.gz
3. Подсчитайте количество файлов в директории `~/boost_1_69_0` **не включая** вложенные директории.
$ ls -f | wc -l 
20
4. Подсчитайте количество файлов в директории `~/boost_1_69_0` **включая** вложенные директории.
$ ls -R -f | wc -l
5. Подсчитайте количество заголовочных файлов, файлов с расширением `.cpp`, сколько остальных файлов (не заголовочных и не `.cpp`).
$ find ./ -type f -name "*.h" | wc -l #296
$ find ./ -type f -name "*.cpp" | wc -l #13774
$ find ./ -type f '!' -name '*.cpp' -a '!' -name '*.h' | wc -l #47102
6. Найдите полный пусть до файла `any.hpp` внутри библиотеки *boost*.
$ find . -type f -name 'any.hpp'
#./boost/fusion/include/any.hpp
#./boost/fusion/algorithm/query/any.hpp
#./boost/fusion/algorithm/query/detail/any.hpp
#./boost/spirit/home/support/algorithm/any.hpp
#./boost/proto/detail/any.hpp ./boost/type_erasure/any.hpp
#./boost/hana/fwd/any.hpp
#./boost/hana/any.hpp
#./boost/any.hpp
#./boost/xpressive/detail/utility/any.hpp
7. Выведите в консоль все файлы, где упоминается последовательность `boost::asio`.
$ grep -lr "boost::asio"
#./doc/html/process/reference.html
8. Скомпилирутйе *boost*. Можно воспользоваться [инструкцией](https://www.boost.org/doc/libs/1_61_0/more/getting_started/unix-variants.html#or-build-custom-binaries) или [ссылкой](https://codeyarns.com/2017/01/24/how-to-build-boost-on-linux/).
$ cd tools/build/
$ bootstrap.sh
$ ./b2 install
9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию `~/boost-libs`.
$ cd ~/boost-libs
$ mv boost_1_69_0/boost_output boost-libs
10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.
$ tree -h
11. Найдите *топ10* самых "тяжёлых".
$ find . -type f -exec ls -s -k {} \; | sort -n -r | head -10
#11548 ./libs/math/doc/math.pdf
#3756 ./status/expected_results.xml
#3048 ./libs/gil/io/test_images/raw/RAW_CANON_D30_SRGB.CRW
#2760 ./libs/asio/doc/reference.qbk
#2736 ./libs/algorithm/test/search_test_data/0001.corpus
#2276 ./boost/typeof/vector200.hpp
#2256 ./libs/contract/doc/html/contract.docbook
#2200 ./libs/math/test/ellint_rg.ipp
#2048 ./libs/intrusive/doc/autodoc.xml
#2032 ./libs/polygon/doc/GTL_boostcon_draft03.pdf
```
Copyright (c) 2015-2019 The ISC Authors
```
