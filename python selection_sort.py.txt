def selection_sort(arr):
    n = len(arr)
    comparisons = 0
    assignments = 0

    # Зовнішній цикл
    # від 0 до n-2 (n-1 проходів)
    for i in range(n - 1):

        # Припускаємо, що поточний елемент є мінімальним
        min_index = i
        assignments += 1

        # Внутрішній цикл шукає найменший елемент в решті списку
        for j in range(i + 1, n):
            comparisons += 1

            if arr[j] < arr[min_index]:
                min_index = j
                assignments += 1 # Присвоєння змінній min_index

        # Обмін елементів, якщо знайдено новий мінімальний
        comparisons += 1 # Операція порівняння

        if min_index != i:
        # Обмін елементів
            arr[i], arr[min_index] = arr[min_index], arr[i]
            assignments += 3

    return arr, comparisons, assignments


# Приклад використання
my_list = [19, 75, 43, 31, 5, 66, 62, 34, 76]

sorted_list, comps, assigs = selection_sort(my_list.copy())
   # Використання .copy(), щоб не змінювати оригінал
print("Оригінальний список:", my_list)
print("Відсортований список:", sorted_list)
print(f"Кількість порівнянь: {comps}")
print(f"Кількість присвоєнь: {assigs}")
