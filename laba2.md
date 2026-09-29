# 1. Преобразование типов
def convert_types(data):
    result = []

    for item in data:
        if isinstance(item, (int, float)) and not isinstance(item, bool):
            result.append(str(item))
        elif isinstance(item, str):
            try:
                if "." in item:
                    result.append(float(item))
                else:
                    result.append(int(item))
            except ValueError:
                result.append(item)
        else:
            result.append(str(item))

    return result


# 2. Обмен значений без третьей переменной
def swap_values(a, b):
    a, b = b, a
    return a, b


# 3. Проверка истинности без bool()
def bool_transform(value):
    if value:
        return True
    return False


# 4. Составные операции
def compound_operations(a, b):
    results = []

    value = a
    value += b
    results.append(value)

    value = a
    value -= b
    results.append(value)

    value = a
    value *= b
    results.append(value)

    value = a
    value /= b
    results.append(value)

    value = a
    value //= b
    results.append(value)

    value = a
    value %= b
    results.append(value)

    value = a
    value **= b
    results.append(value)

    return results


# 5. Проверка типа
def check_type(value, expected_type):
    allowed_types = ["int", "float", "str", "list", "bool"]

    if expected_type not in allowed_types:
        return False

    return type(value).__name__ == expected_type


# 6. Логическое И без and
def logical_and(a, b, c):
    if a:
        if b:
            if c:
                return True

    return False


# 7. Логическое ИЛИ без or
def logical_or(a, b, c):
    if a:
        return True

    if b:
        return True

    if c:
        return True

    return False


# 8. Проверка диапазона
def is_between(value, low, high):
    if low <= value and value <= high:
        return True

    return False


# 9. Чётные числа
def print_even_numbers(n):
    for number in range(2, n + 1, 2):
        print(number)


# 10. Обратный отсчёт
def countdown_while(n):
    while n >= 1:
        print(n)
        n -= 1


# 11. Пропуск кратных чисел
def skip_multiples(n, multiple):
    for i in range(1, n + 1):
        if i % multiple == 0:
            continue

        print(i)


# 12. Конструкция if-elif-else
def if_elif_else_chain(x):
    if x > 0:
        return "positive"
    elif x < 0:
        return "negative"
    else:
        return "zero"


# 13. Абсолютное значение
def abs_value(x):
    if x < 0:
        return -x

    return x


# 14. Двоичное представление
def binary_representation(n):
    if n == 0:
        return "0"

    sign = ""
    if n < 0:
        sign = "-"
        n = -n

    result = ""

    while n > 0:
        remainder = n % 2
        result = str(remainder) + result
        n //= 2

    return sign + result


# 15. Округление без round()
def custom_round(number, ndigits):
    factor = 10 ** ndigits
    scaled = number * factor

    if scaled >= 0:
        rounded = int(scaled + 0.5)
    else:
        rounded = int(scaled - 0.5)

    return rounded / factor


# 16. Поиск максимума и минимума
def find_max_min(numbers):
    if len(numbers) == 0:
        raise ValueError("Список не должен быть пустым")

    max_value = numbers[0]
    min_value = numbers[0]

    for number in numbers[1:]:
        if number > max_value:
            max_value = number

        if number < min_value:
            min_value = number

    return max_value, min_value


# 17. Все элементы истинные
def all_true(iterable):
    for element in iterable:
        if not element:
            return False

    return True


# 18. Хотя бы один элемент истинный
def any_true(iterable):
    for element in iterable:
        if element:
            return True

    return False


# 19. Собственный enumerate()
def custom_enumerate(sequence, start=0):
    result = []
    index = start

    for element in sequence:
        result.append((index, element))
        index += 1

    return result


# 20. Собственный filter()
def custom_filter(func, iterable):
    result = []

    for element in iterable:
        if func(element):
            result.append(element)

    return result


# 21. Собственный map()
def custom_map(func, iterable):
    result = []

    for element in iterable:
        result.append(func(element))

    return result


# 22. Собственный zip()
def custom_zip(list1, list2):
    result = []
    length = min(len(list1), len(list2))

    for i in range(length):
        result.append((list1[i], list2[i]))

    return result


# 23. Разворот последовательности
def custom_reversed(sequence):
    result = []

    for i in range(len(sequence) - 1, -1, -1):
        result.append(sequence[i])

    return result


# 24. Сортировка пузырьком
def custom_sorted(iterable, reverse=False):
    result = []

    for element in iterable:
        result.append(element)

    n = len(result)

    for i in range(n):
        for j in range(0, n - i - 1):
            should_swap = result[j] > result[j + 1]

            if reverse:
                should_swap = result[j] < result[j + 1]

            if should_swap:
                result[j], result[j + 1] = result[j + 1], result[j]

    return result


# 25. Сумма цифр числа
def sum_digits(n):
    n = abs(n)
    total = 0

    while n > 0:
        total += n % 10
        n //= 10

    return total


# 26. Подсчёт гласных
def count_vowels(text):
    vowels = "aeiouAEIOU"
    count = 0

    for character in text:
        if character in vowels:
            count += 1

    return count


# 27. Возведение в степень без ** и pow()
def power(base, exp):
    if exp == 0:
        return 1

    result = 1
    positive_exp = exp

    if exp < 0:
        positive_exp = -exp

    for _ in range(positive_exp):
        result *= base

    if exp < 0:
        return 1 / result

    return result


# 28. Проверка простого числа
def is_prime(n):
    if n < 2:
        return False

    for divisor in range(2, int(n ** 0.5) + 1):
        if n % divisor == 0:
            return False

    return True


# 29. Факториал
def factorial(n):
    if n < 0:
        raise ValueError("Факториал определён только для неотрицательных чисел")

    result = 1

    for i in range(1, n + 1):
        result *= i

    return result


# 30. Число Фибоначчи
def fibonacci(n):
    if n < 0:
        raise ValueError("Индекс не может быть отрицательным")

    previous = 0
    current = 1

    for _ in range(n):
        previous, current = current, previous + current

    return previous
