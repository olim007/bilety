# Плюсы
## 1. Директивы препроцессора (`#include`, `#define`). Функция main()

Препроцессор запускается до компилятора и преобразовывает исходный код в код, который видит компилятор. Каждая строка, которая начинается с #, представляет собой директиву препроцессора.
`#include` директива указывает, что код должен включить содержимое какого-то файла в исходный текст вместо самой директивы. Для стандартных заголовочных файлов используются `<>`, для других `""`.
Примеры: 
  ```cpp
 #include <iostream>
#include "tracer.h"
 ```
`#define` директива выполняет определяет макропостановки, которые будет проводить препроцессор.
Например, написав `#define abc xyz` компилятор вместо исходного кода:
```cpp
int abc = 1;
int abcd = 2;
```

Увидит:
```cpp
int xyz = 1;
int abcd = 2;
```
Слово, на которое будет выполнена замена - это макрос. Макросы принято писать uppercase-ом.
Также с помощью define можно определить макросы с параметрами.
```cpp
// пример макроса, который определяет максимум 2 объектов.
#define MAX(x, y) ( ((x) > (y)) ? (x) : (y) ) 
```

Все программы, написанные на С++, должны содержать функцию с именем `main()`. Ей дается управление после запуска программы. Она может возвращать значения в вызвавшую систему. Функция `main()` может быть без параметров и с параметрами:
```cpp
int main();
int main(int argc, char* argv[]);
```

## 2. Встроенные типы данных. Строки std::string и массивы std::vector
 Каждая переменная имеет определенный тип. И этот тип определяет, какие значения может иметь переменная, 
 какие операции с ней можно производить и сколько байт в памяти она будет занимать.
 В языке C++ определены следующие базовые типы данных:
+ логический (bool)
+ символьный (char), 
+ целочисленный (int, unsigned int), 
+ вещественный (double, float)  
---
 С помощью них можно реализовать все идеи и создавать собственные типы. `std::string` - массив символов хранящий свой размер и имеющий свои методы,
 `std::vector` - массив содержащий элементы одного типа данных, хранящий свой размер и  имющий свои методы.

## 3. Константы. Квалификаторы `const` и `constexpr`
Квалификаторы `const` и `constexpr` говорят о том, что значения хранящиеся в памяти под этим именем именять нельзя. 
значние с квалификатором constexpr - обязано быть известно на этапе компиляции, а вот const - нет.
```cpp
const a = 12; // может быть и не известна во время компиляции
constexpr b = 15; // должна быть известна во время компиляции
```

