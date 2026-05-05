# Laboratory work II

## Цель работы

Изучить основы работы с системой контроля версий Git и сервисом GitHub.

## Задание

1. Создать публичный репозиторий `lab02` на GitHub.
2. Добавить лицензию MIT.
3. Настроить локальный репозиторий.
4. Создать структуру проекта.
5. Добавить исходные файлы.
6. Зафиксировать изменения с помощью Git и отправить их на GitHub.

## Ход работы

Сначала были заданы данные пользователя GitHub:

```bash
export GITHUB_USERNAME=VincentTheBrainfuqqer
export GITHUB_EMAIL=<my_email>
```

Были настроены имя пользователя и email для Git:

```bash
git config --global user.name ${GITHUB_USERNAME}
git config --global user.email ${GITHUB_EMAIL}
```

После этого был создан локальный каталог лабораторной работы:

```bash
mkdir -p ~/VincentTheBrainfuqqer/workspace/projects/lab02
cd ~/VincentTheBrainfuqqer/workspace/projects/lab02
```

Был инициализирован локальный Git-репозиторий:

```bash
git init
```

Затем был добавлен удаленный репозиторий:

```bash
git remote add origin https://github.com/VincentTheBrainfuqqer/lab02.git
```

Так как в репозитории используется ветка `main`, дальнейшая отправка выполнялась в нее:

```bash
git branch -M main
git pull origin main
```

В проект была добавлена структура каталогов:

```bash
mkdir examples
mkdir include
mkdir sources
```

Итоговая структура проекта:

```text
lab02/
├── .gitignore
├── LICENSE
├── README.md
├── examples/
│   ├── example1.cpp
│   └── example2.cpp
├── include/
│   └── print.hpp
└── sources/
    └── print.cpp
```

Файл `.gitignore` содержит исключения для временных файлов и каталогов сборки:

```gitignore
*build*/
*install*/
*.swp
.idea/
```

В файл `include/print.hpp` были добавлены объявления функций:

```cpp
#include <fstream>
#include <iostream>
#include <string>

void print(const std::string& text, std::ofstream& out);
void print(const std::string& text, std::ostream& out = std::cout);
```

В файл `sources/print.cpp` была добавлена реализация функций:

```cpp
#include <print.hpp>

void print(const std::string& text, std::ostream& out)
{
  out << text;
}

void print(const std::string& text, std::ofstream& out)
{
  out << text;
}
```

В файл `examples/example1.cpp` был добавлен пример вывода строки в стандартный поток:

```cpp
#include <print.hpp>

int main(int argc, char** argv)
{
  print("hello");
}
```

В файл `examples/example2.cpp` был добавлен пример вывода строки в файл:

```cpp
#include <print.hpp>

#include <fstream>

int main(int argc, char** argv)
{
  std::ofstream file("log.txt");
  print(std::string("hello"), file);
}
```

После добавления файлов было проверено состояние репозитория:

```bash
git status
```

Затем все изменения были добавлены в индекс:

```bash
git add .
```

Был создан коммит:

```bash
git commit -m "added sources"
```

После этого изменения были отправлены в удаленный репозиторий GitHub:

```bash
git push origin main
```

## Результат

В результате выполнения лабораторной работы был создан публичный репозиторий `lab02` с лицензией MIT.

В репозиторий были добавлены:

- файл `README.md`;
- файл `.gitignore`;
- лицензия `LICENSE`;
- каталог `include` с заголовочным файлом;
- каталог `sources` с реализацией функций;
- каталог `examples` с примерами использования.

Работа с Git была выполнена через основные команды:

```bash
git init
git remote add
git status
git add
git commit
git push
```

## Вывод

В ходе лабораторной работы были изучены базовые возможности Git и GitHub.

Был создан локальный репозиторий, подключен удаленный репозиторий, добавлены файлы проекта, выполнен коммит и отправка изменений на GitHub.
