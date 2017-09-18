## Laboratory work III

Данная лабораторная работа посвещена изучению систем контроля версий на примере **Git**.

```bash
$ open https://git-scm.com
```

## Tasks

- [x] 1. Создать публичный репозиторий с названием **lab03** и с лиценцией **MIT**
- [x] 2. Ознакомиться со ссылками учебного материала
- [x] 3. Выполнить инструкцию учебного материала
- [x] 4. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial

```ShellSession
$ export GITHUB_USERNAME=poljkee2010  # Устанавливаем значение переменной окружения GITHUB_USERNAME
$ export GITHUB_EMAIL=poljkee2010@gmail.com # Устанавливаем значение переменной окружения GITHUB_EMAIL
$ alias edit=subl # Выбираем текстовый редактор 
```

```ShellSession
$ mkdir lab03 && cd lab03 # Создаём директорию и переходим в неё
$ git init # Создаём репозиторий в существующей директории
$ git config --global user.name ${GITHUB_USERNAME} # git config позволяет просматривать и устанавливать параметры; опция --global даёт возможность настроить всего лишь один раз
$ git config --global user.email ${GITHUB_EMAIL} # Указываем имя пользователя и email
$ git config -e --global # Включить поддержку вывода Escape последовательностей;
$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab03  # Загрузка удаленного репозитория lab03 
$ git pull origin master # Выгрузить изменения всех веток с удаленного репозитория в ветку master
$ touch README.md # Создать файл в текущей директории
$ git status # Текущее состояние репозитория (изменения, неразрешенные конфликты)
$ git add README.md # Добавляем новый файл под контроль,чтобы в дальнейшем отслеживать его изменения 
$ git commit -m"added README.md" # Выполняем commit файла и добавляем комментарий к коммиту
$ git push origin master # Залить все изменения ветки master с локального на удаленный репозиторий
```

Добавить на сервисе **GitHub** в репозитории **lab03** файл **.gitignore**
со следующем содержимом:

```ShellSession
*build*/
*install*/
*.swp
# Сделано https://github.com/poljkee2010/lab03
```

```ShellSession
$ git pull origin master # Выгрузить изменения всех веток с удаленного репозитория в ветку master
$ git log # История изменений
```

```ShellSession
$ mkdir sources # Создание директорий
$ mkdir include
$ mkdir examples

# Запись в .cpp файл участка кода
$ cat > sources/print.cpp <<EOF
#include <print.hpp>

void print(const std::string& text, std::ostream& out) {
  out << text;
}

void print(const std::string& text, std::ofstream& out) {
  out << text;
}
EOF 

# end of file — конец файла,переход на новый строку
```

```ShellSession
# Запись в .cpp файл участка кода
$ cat > include/print.hpp <<EOF 
#include <string>
#include <fstream>
#include <iostream>

void print(const std::string& text, std::ostream& out = std::cout);
void print(const std::string& text, std::ofstream& out);
EOF 
# end of file — конец файла,переход на новый строку
```

```ShellSession
# Запись в .cpp файл участка кода
$ cat > examples/example1.cpp <<EOF 
#include <print.hpp>

int main(int argc, char** argv) {
  print("hello");
}
EOF 
# end of file — конец файла,переход на новый строку
```

```ShellSession
# Запись в .cpp файл участка кода
$ cat > examples/example2.cpp <<EOF 
#include <fstream>
#include <print.hpp>

int main(int argc, char** argv) {
  std::ofstream file("log.txt");
  print(std::string("hello"), file);
}
EOF 
# end of file — конец файла,переход на новый строку
```

```ShellSession
$ edit README.md # Редактируем файл README.md
```

```ShellSession
$ git status # Текущее состояние репозитория
$ git add . # Обработка содержимого текущей директории
$ git commit -m"added sources" # Выполняем commit файла и добавляем комментарий к коммиту
$ git push origin master # Залить все изменения ветки master с локального на удаленный репозиторий
```

## Report

```ShellSession
$ cd ~/workspace/labs/  # Переходим в /workspace/labs/
$ export LAB_NUMBER=03 # # Устанавливаем значение переменной окружения LAB_NUMBER
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER} # Клонирование репозитория с лабой
$ mkdir reports/lab${LAB_NUMBER} # Создаем каталог lab${LAB_NUMBER}
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md # Копируем README.md в REPORT.md
$ cd reports/lab${LAB_NUMBER} # Меняем директорию на reports/lab${LAB_NUMBER}
$ edit REPORT.md # Редактируем файл REPORT.md
$ gistup -m "lab${LAB_NUMBER}" #Создаем Gist из командной строки и комментарием 
```

## Links

- [GitHub](https://github.com)
- [Bitbucket](https://bitbucket.org)
- [Gitlab](https://about.gitlab.com)
- [LearnGitBranching](http://learngitbranching.js.org/)

```
Copyright (c) 2017 Братья Вершинины
```
