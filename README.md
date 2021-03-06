# АА-дерево

[![CMake](https://github.com/Algorithms-and-Data-Structures-2021/semester-work-aa-tree-fixiki/actions/workflows/cmake.yml/badge.svg)](https://github.com/Algorithms-and-Data-Structures-2021/semester-work-aa-tree-fixiki/actions/workflows/cmake.yml)

AA-дерево  - это форма сбалансированного дерева, которое используется для хранения и эффективного извлечение упорядоченных данных. АА-деревья названы по имени их изобретателя Арне Андерсона.​

АА-дерево является разновидностью красно-черного дерева, но в отличие от красно-черных деревьев, красные узлы на АА-дереве могут быть добавлены только как правый потомок, благодаря этому, АА-деревья обладают повышенной простотой кодировки.

В AA-дереве разрешены правые ребра, не идущие подряд, и запрещены все левые горизонтальные ребра. Эти более жесткие ограничения , аналогичные ограничениям на красно-черных деревьях, приводят к более простой реализации балансировки AA-дерева.

Свойства АА-дерева:
- Уровень каждого листа равен 1.
- Уровень каждого левого ребенка ровно на один меньше, чем у его родителя.
- Уровень каждого правого ребенка равен или на один меньше, чем у его родителя.
- Уровень каждого правого внука строго меньше, чем у его прародителя.
- Каждая вершина с уровнем больше 1 имеет двоих детей.

Оценка на высоту деревьев соответствует оценке для красно-черного дерева, 2⋅log2(N), так как AA-дерево сохраняет структуру красно-черного дерева. Следовательно все операции происходят за O(logN), потому что в сбалансированном двоичном дереве поиска почти все операции реализуются за O(h). Скорость работы AA-дерева эквивалентна скорости работы красно-черного дерева, но так как в реализации вместо цвета обычно хранят «уровень» вершины, дополнительные расходы по памяти достигают байта.

## Команда "Fixiki"

| Фамилия Имя    | Вклад (%) | Прозвище              |
| :---           |   ---:    |  ---:                 |
| Видеева Ирина  | 50        |  Нолик                |
| Бадамшин Артур | 50        |  Симка                |
| Сафин Рамиль   | неизмеримо много        |  Папус                |

**Девиз команды**
«А кто такие фиксики — большой-большой секрет!»

## Структура проекта

- [`src`](src)/[`include`](include) - реализация структуры данных (исходный код и заголовочные файлы);
- [`benchmark`](benchmark) - контрольные тесты производительности структуры данных (операции добавления, удаления,
  поиска);
- [`examples`](examples) - примеры работы со структурой данных;
- [`dataset`](dataset) - наборы данных для запуска контрольных тестов;
- [`results-path-example`](results-path-example) - пример структуры для выгрузки ответов;

## Требования (Prerequisites)

Рекомендуемые требования:

- :black_square_button: С++ компилятор c поддержкой стандарта C++17 (например, _GNU GCC 8.1.x_ и выше).
- :black_square_button: Система автоматизации сборки _CMake_ (версия _3.12.x_ и выше).
- :black_square_button: Java Development Kit (версия 8 и выше).
- :black_square_button: Рекомендуемый объем оперативной памяти - не менее 4 ГБ.
- :black_square_button: Свободное дисковое пространство объемом ~ 1 ГБ (набор данных для контрольных тестов).
- :white_check_mark: Желание

## Сборка и запуск

### Пример (Windows)

#### Сборка проекта

Склонируйте проект к себе на устройство через [Git for Windows](https://gitforwindows.org/) (либо используйте
возможности IDE):

```shell
git clone https://github.com/Algorithms-and-Data-Structures-2021/semester-work-aa-tree-fixiki.git
```

Для ручной сборки проекта в терминале введите:

```shell
# переход в папку с проектом
cd C:\Users\username\asd-projects\semester-work-aa-tree-fixiki

# создание папки для файлов сборки (чтобы не засорять папку с проектом) 
mkdir -p build && cd build 

# сборка проекта
cmake .. -DCMAKE_BUILD_TYPE=RelWithDebInfo && cmake --config RelWithDebInfo --build . 
```

#### Генерация тестовых данных

Генерация тестового набора данных в
формате [comma-seperated values (CSV)](https://en.wikipedia.org/wiki/Comma-separated_values)

1) Склонируйте проект генератора набора случайных чисел [ЗДЕСЬ](https://github.com/rthoor/generation.git) к себе на устройство 
2) Ознакомьтесь с инструкциями генерации
3) Сгенерируйте наборы данных

#### Контрольные тесты (benchmarks)

Есть два режима тестирования:
1) Прогоняется сначала последовательное добавление N кол-ва элементов, потом последовательный поиск каждого и затем удаление каждого
2) Прогоняется добавление, удаление и поиск в дереве из N-элементов (сначала добавится, допустим, 100 элементов, а далее будет засекаться добавление, поиск и удаление нового элемента

Результаты наших тестов:
[ЗДЕСЬ](https://drive.google.com/drive/folders/1cXU96JxD963AUfDVZU4DiMPw9EpWiGzg?usp=sharing)

##### Список контрольных тестов

| Название                  | Описание                                | Метрики         |
| :---                      | ---                                     | :---            |
| `demo_benchmark.cpp` | insert, search, delete                  | _время_         |


## Источники
- [Викикоспекты ИТМО](https://neerc.ifmo.ru/wiki/index.php?title=AA-дерево)

- [Википедия(англ)](https://en.wikipedia.org/wiki/AA_tree)
