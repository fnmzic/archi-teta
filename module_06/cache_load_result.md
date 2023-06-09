# Тестирование сервиса author

## Без кеширования запросов

| Параметры тестирования      | Тест 1           | Тест 2            | Тест 3            |
|:---------------------------|:----------------|:-----------------|:-----------------|
| Время                      | 60 секунд       | 60 секунд        | 60 секунд         |
| Количество потоков        | 1               | 10               | 50               |
| Количество соединений     | 1               | 10               | 50               |
| Среднее значение задержки   | 4.00ms          | 38.47ms          | 213.43ms         |
| Стандартное отклонение задержки    | 3.17ms          | 7.89ms           | 62.87ms          |
| Максимальное значение задержки     | 29.59ms         | 88.67ms          | 246.78ms         |
| +/- Stdev задержки                 | 94.62%          | 82.62%           | 91.67%           |
| Req/Sec среднее                   | 282.66          | 25.91            | 1.96             |
| Req/Sec стандартное                        | 40.14          | 5.17          | 2.40         |
| Req/Sec максимальное                        | 333.00         | 40.00          | 10       |
| Req/Sec  +/- Stdev                     | 68.40%          | 61.54%          | 91.30%         |
| 50%                        | 3.20ms          | 35.83ms          | 232.52ms         |
| 75%                        | 3.48ms          | 39.92ms          | 234.83ms         |
| 90%                        | 4.26ms          | 50.19ms          | 243.22ms         |
| 99%                        | 22.22ms         | 64.13ms          | 246.78ms         |
| Запросы в 1 мин                   | 16884           | 15597            | 23               |
| Transfer/sec               | 82.38KB         | 76.02KB          | 114.36B          |

**Краткий итог:**
-   Разброс значений задержки для тестов 1 и 2 является относительно маленьким, по сравнению с тестом 3.
-   Значение количества запросов в секунду падает с увеличением количества потоков и соединений.
-   Стандартное отклонение количества запросов в секунду также увеличивается с увеличением количества потоков и соединений.


## С кешированием
| Параметры тестирования      | Тест 1           | Тест 2            | Тест 3            |
|:---------------------------|:----------------|:-----------------|:-----------------|
| Время                      | 60 секунд       | 60 секунд        | 60 секунд         |
| Количество потоков        | 1               | 10               | 50               |
| Количество соединений     | 1               | 10               | 50               |
| Среднее значение задержки   | 2.12ms          | 14.04ms          | 91.83ms          |
| Стандартное отклонение задержки    | 2.41ms          | 3.88ms           | 31.09ms          |
| Максимальное значение задержки     | 31.18ms         | 52.53ms          | 157.22ms         |
| +/- Stdev задержки                 | 96.85%          | 91.13%           | 40.74%           |
| Req/Sec среднее                   | 551.83          | 71.95            | 8.22              |
| Req/Sec стандартное                        | 65.09          | 9.12          | 2.58          |
| Req/Sec максимальное                        | 610.00         | 150.00          | 10.00         |
| Req/Sec  +/- Stdev                     | 83.97%          | 77.36%          | 74.07%          |
| 50%                        | 1.68ms          | 13.27ms          | 104.39ms         |
| 75%                        | 1.80ms          | 14.33ms          | 109.26ms         |
| 90%                        | 2.00ms          | 16.27ms          | 128.18ms         |
| 99%                        | 16.97ms         | 33.53ms          | 157.22ms         |
| Запросы в 1 мин                   | 33007           | 43108            | 27               |
| Transfer/sec               | 9.19MB         | 12.30MB          | 7.85KB          |
**Краткий итог:**
Результаты тестов с кешированием значительно лучше результатов тестов без кеширования. С использованием кеша достигается более низкая задержка, высокая пропускная способность и более быстрая обработка запросов.