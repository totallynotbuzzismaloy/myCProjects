# Проект: c-rpn (Калькулятор RPN)

Этот проект представляет собой консольный калькулятор, реализующий обратную польскую нотацию (Reverse Polish Notation, RPN) для выполнения арифметических операций. Калькулятор поддерживает базовые арифметические операции и проверки на корректность введенных данных.

## Оглавление

- [Описание проекта](#описание-проекта)
- [Модули проекта](#модули-проекта)
  - [Стек (stack.h)](#стек-stackh)
  - [Обработка выражений RPN (rpn.h)](#обработка-выражений-rpn-rpnh)
  - [Основная программа (main.c)](#основная-программа-mainc)
- [Использование](#использование)
- [Примеры ввода и вывода](#примеры-ввода-и-вывода)

## Описание проекта

Калькулятор RPN — это консольное приложение для вычисления выражений в обратной польской нотации. Калькулятор принимает входные выражения с операндами и операторами, разделенными пробелами, и поддерживает следующие арифметические операции:
- Сложение (`+`)
- Вычитание (`-`)
- Умножение (`*`)
- Деление (`/`)

## Модули проекта

### Стек (stack.h)

Модуль `stack.h` предоставляет структуру стека для хранения операндов, используемых в процессе вычисления RPN.

#### Функции модуля stack.h:

- **`initialize_stack`** — Инициализирует новый стек и возвращает указатель на него.
- **`stack_is_full`** — Проверяет, заполнен ли стек.
- **`stack_push`** — Добавляет элемент на вершину стека. Если стек заполнен, выводит сообщение об ошибке.
- **`stack_is_empty`** — Проверяет, пуст ли стек.
- **`stack_pop`** — Удаляет и возвращает элемент с вершины стека. Если стек пуст, возвращает ошибку `STACK_UNDERFLOW_ERR`.
- **`stack_peek`** — Возвращает значение элемента на вершине стека без удаления.

### Обработка выражений RPN (rpn.h)

Модуль `rpn.h` выполняет обработку строки с выражением в RPN, выполняет арифметические операции и возвращает результат.

#### Функции модуля rpn.h:

- **`is_valid_char`** — Проверяет, является ли символ допустимым для выражения RPN (цифра, оператор или пробел).
- **`check_valid_str`** — Проверяет, содержит ли строка только допустимые символы.
- **`check_decimal_points`** — Проверяет правильность использования десятичных точек.
- **`check_spaces`** — Проверяет корректность пробелов в выражении.
- **`make_operation`** — Выполняет одну из операций (`+`, `-`, `*`, `/`) над двумя верхними элементами стека.
- **`parse_expression`** — Разбирает строку RPN, выполняет операции и возвращает результат.
- **`start_rpn`** — Основной цикл программы для обработки выражений RPN и вывода результата.
- **`menu`** — Выводит инструкции по использованию калькулятора и запускает обработку выражений.

### Основная программа (main.c)

Модуль `main.c` содержит функцию `main`, которая вызывает функцию `menu` для начала работы с калькулятором.

## Использование

1. **Клонируйте репозиторий**:
   ```bash
   git clone https://github.com/username/c-rpn.git
   ```
2. **Сборка программы**:
   ```bash
   gcc main.c -o main
   ```
3. **Запуск**:
    ```bash
   ./main
   ```
