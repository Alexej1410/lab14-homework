<h1>Домашняя работа к лабораторной №14</h1>
<h2>Выполнил: Кравченко А.С.</h2>

<h1>Вариант 14</h1>
<h2>Условие задачи</h2>
Каждый вариант оформить в виде отдельной функции, которая возвращает найденного значение и принимает в качестве аргументов – указатель на массив, его размер и необходимые для условий поиска параметры. Поиск максимального значения, среди элементов порядковый номер которых лежит в диапазоне [K; L]

<h2>Алгоритм</h2>

```
1. Начало.
2. Функция full_elements(double* ptr_array, int n):
  Инициализируем переменные double st = 1, double end = 3, double element = (end - st) / (n - 1);
  Пока i = 0; i < n; i++:
    double x = st + i * st;
    ptr_array[i] = x * x + pow(cos(M_PI*x), 2);
  return ptr_array.
3. Функция put_elements(double* ptr_array, int n):
  printf("| Номер элемента | Значение |\n");
  Пока i = 0; i < n; i++:
    printf("| %14d | %3f |\n", i, ptr_array[i]);
  return 0.
4. Функция max_element(double* ptr_array, int n1, int n2):
  Инициализируем переменную double max_el = 0;
  for (int i = n1; i <= n2; i++) {
    if (ptr_array[i] > max_el)
        max_el = ptr_array[i];
  return max_el.
5. main:
  Инициализируем массив double array[N] и переменную int size;
  Вводим размер массива size не больше N;
  Если size > N || size <= 0:
    printf("размер массива введен неверно\n");
    return 1;
  full_elements(array, size);
  printf("\nисходный массив:\n");
  put_elements(array, size);
  Вводим начальный элемент поиска n1;
  Вводим конечный элемент поиска n2;
  printf("максимальный элемент из диапазона [%d;%d] - %lf", n1, n2, max_element(array, n1, n2));
  return 0.
6. конец.
```

<h2>Код проограммы</h2>

```
#define _CRT_SECURE_NO_WARNINGS
#define _CRT_SECURE_NO_DEPRECATE
#include <locale.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h> 
#include <conio.h>
#define _USE_MATH_DEFINES
#include <math.h>
#define N 100

double* full_elements(double* ptr_array, int n) {
    double st = 1;
    double end = 3;
    double element = (end - st) / (n - 1);
    for (int i = 0; i < n; i++) {
        double x = st + i * st;
        ptr_array[i] = x * x + pow(cos(M_PI*x), 2);
    }
    return ptr_array;
}

int put_elements(double* ptr_array, int n) {
    printf("| Номер элемента | Значение |\n");
    for (int i = 0; i < n; i++) {
        printf("| %14d | %3f |\n", i, ptr_array[i]);
    }
    return 0;
}

double max_element(double* ptr_array, int n1, int n2) {
    double max_el = 0;
    for (int i = n1; i <= n2; i++) {
        if (ptr_array[i] > max_el)
            max_el = ptr_array[i];
    }
    return max_el;
}

void main() {
    setlocale(LC_ALL, "RUS");
    double array[N];
    int size;

    printf("введите размер массива (не больше %d):", N);
    scanf("%d", &size);

    if (size > N || size <= 0) {
        printf("размер массива введен неверно\n");
        return 1;
    }
    full_elements(array, size);
    printf("\nисходный массив:\n");
    put_elements(array, size);
    printf("введите начальный элемент поиска:");
    int n1;
    scanf("%d", &n1);
    printf("введите конечный элемент поска:");
    int n2;
    scanf("%d", &n2);
    printf("максимальный элемент из диапазона [%d;%d] - %lf", n1, n2, max_element(array, n1, n2));
    return 0;
}
```

<h2>Схемы</h2>

<h2>Консоль</h2>
<img width="640" height="437" alt="image" src="https://github.com/user-attachments/assets/9d810c7d-602a-44e5-bf3b-b8bc48d09e59" />
