## Определения и теория систем счисления

**Система счисления** — это способ записи чисел.

**_Алфавит системы счисления_** — это используемый в ней набор цифр.

**_Мощьность системы счисления, (мощность алфавита)_** — это количество цифр в алфавите.

Система счисления называется **позиционной**, если количественный эквивалент цифры зависит от её положения (места, позиции) в записи числа. Например: если мы возьмем число 1050 в 10й системе счисления, то если переставить местами цифры в числе получится абсолютно другое число: 1500. То есть мы сместили с позиции десяток цифру 5 и поставили ее на место сотен, получилось число, превышающее исходное.

Последовательность чисел, каждое из которых задает «вес» соответствующего разряда, называется **базисом** позиционной системы счисления:

![Иллюстрации/1.png](https://github.com/At1set/Number-system/blob/main/%D0%98%D0%BB%D0%BB%D1%8E%D1%81%D1%82%D1%80%D0%B0%D1%86%D0%B8%D0%B8/1.png)

## Развернутая форма записи числа

Когда мы записываем число в десятичной системе счисления (q = 10), мы как бы раскладываем его в сумму единиц (10^0), десяток (10^1), сотен (10^2), тысяч (10^3) и т.д., при этом количество в каждом разряде (множитель при основании системы счисления в какой то степени) строго меньше 10.

Число x в q-ричной системе счисления представляется также в виде суммы целых степеней числа  с коэффициентами:

![Иллюстрации/2.png](https://github.com/At1set/Number-system/blob/main/%D0%98%D0%BB%D0%BB%D1%8E%D1%81%D1%82%D1%80%D0%B0%D1%86%D0%B8%D0%B8/2.png)

Перевод в десятичную систему счисления осуществляется прямым вычислением по этой формуле.
#### пример:

![Иллюстрации/3.png](https://github.com/At1set/Number-system/blob/main/%D0%98%D0%BB%D0%BB%D1%8E%D1%81%D1%82%D1%80%D0%B0%D1%86%D0%B8%D0%B8/3.png)

## Алгоритм перевода числа из одной системы счисления в другую и обратно:

1) Смотрим на систему счисления того числа, которое мы хотим перевести в другую сис.: если оно записано не в 10й сис, то для начала переводим его в 10ю систему счисления, после этого приступаем к нижним пунктам.

2) Находим максималую степень, в которую можно возвести основание системы счисления (основание системы счисления - это число, которое находится в названии системы счисления, например в 10й сис основание - "10").

3)  Если основание сис в максимальной степени меньше того числа, которое мы переводим (но не больше!), то подбираем максимальный множитель, на который мы можем умножить это основание.

4) Производим разницу между числом, которое мы переводим и множителем с основаним сис в макс. степени.

5) Производим аналогичные действия, как в прошлых пунктах, только для полученной разницы. (остатка того числа, которое мы переводим). Проходимся по каждому разряду по убыванию и, если оно избыточно, логично подставить множитель 0.

6) Записываем по порядку множители (базисы сис) из разрядов, которые мы нашли. Это и есть искомое число в новой системе счисления.

## Пример.

#### У нас есть число 110101, записанное в 2й системе счисления и мы хотим перевести его в 3ю сис.

По пунктам:

1) Для перевода в 10ю систему счисления расписываем число в развернутом виде:

110101 = 1 * 2^5 + 1 * 2^4 + 0 * 2^3 + 1 * 2^2 + 0 * 2^1 + 1 * 2^0.

Теперь считаем, что получилось:

1 * 2^5 + 1 * 2^4 + 0 * 2^3 + 1 * 2^2 + 0 * 2^1 + 1 * 2^0 = 53 в 10й сис.

2) Макс. множитель, который мы можем взять для 3ки - 3^3 = 27, что маловато, поэтому домножаем на число, не превышающее 53, но и сам множитель не должен превышать нашу систему счисления (в данном примере макс. множитель - 2, так как в 3й системе счисления используются цифры (0, 1, 2)) - 2 мы не можем взять, так как 2 * 27 = 54 > 53, поэтому берем **_1_**:

![Иллюстрации/4.png](https://github.com/At1set/Number-system/blob/main/%D0%98%D0%BB%D0%BB%D1%8E%D1%81%D1%82%D1%80%D0%B0%D1%86%D0%B8%D0%B8/4.png)

4) Теперь смотрим на следующий по убыванию разряд: 3^2 = 9. Мы видим, что максимально можно домножить 9 на 2, чтобы результат не превышал число 26. (В случае, если у нас оставалось бы число не 26, а например 8, то даже не домножая 9, мы бы превысили данный остаток. В таком случае надо брать множитель = 0: 0 * 9^2 < 8 и дальше идти по разрядам):

![Иллюстрации/5.png](https://github.com/At1set/Number-system/blob/main/%D0%98%D0%BB%D0%BB%D1%8E%D1%81%D1%82%D1%80%D0%B0%D1%86%D0%B8%D0%B8/5.png)

5) У нас остался остаток 8 и максимально мы можем взять тройку в 1м разряде 2 раза :  2 * 3^1 = 6 < 8:

![Иллюстрации/6.png](https://github.com/At1set/Number-system/blob/main/%D0%98%D0%BB%D0%BB%D1%8E%D1%81%D1%82%D1%80%D0%B0%D1%86%D0%B8%D0%B8/6.png)

6) Осталась 2ка и она полностью вмещается в оставшийся разряд единиц: 2 * 3^0 = 2 = 2. (Если бы у нас была ситуация, что осталось, например, число большее, чем мы можем взять, то вы скорее всего ошиблись в прошлых этапах и взяли либо немаксимальную степень, либо подобрали немаксимальные множители.):

![Иллюстрации/7.png](https://github.com/At1set/Number-system/blob/main/%D0%98%D0%BB%D0%BB%D1%8E%D1%81%D1%82%D1%80%D0%B0%D1%86%D0%B8%D0%B8/7.png)
