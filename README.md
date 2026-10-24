import random

n = int(input("Введіть довжину першого масиву: "))
m = int(input("Введіть довжину другого масиву: "))

A = [random.randint(1, 9) for _ in range(n)]
B = [random.randint(1, 9) for _ in range(m)]

print("Перший масив:", A)
print("Другий масив:", B)

result = []
carry = 0

i = len(A) - 1
j = len(B) - 1

while i >= 0 or j >= 0 or carry > 0:
    x = A[i] if i >= 0 else 0
    y = B[j] if j >= 0 else 0

    s = x + y + carry

    result.append(s % 10)
    carry = s // 10

    i -= 1
    j -= 1

result.reverse()

print("Результат додавання:", result)
