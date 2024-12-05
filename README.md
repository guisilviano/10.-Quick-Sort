def partition(arr, low, high):
    """
    Função para particionar a lista com base no pivô.

    :param arr: Lista de elementos a serem ordenados.
    :param low: Índice inicial da sublista.
    :param high: Índice final da sublista.
    :return: Índice do pivô na posição correta.
    """
    pivot = arr[high]  # Escolhe o último elemento como pivô
    i = low - 1  # Índice do menor elemento

    for j in range(low, high):
        if arr[j] < pivot:
            i += 1
            arr[i], arr[j] = arr[j], arr[i]

    arr[i + 1], arr[high] = arr[high], arr[i + 1]
    return i + 1


def quick_sort(arr, low, high):
    """
    Implementa o algoritmo Quick Sort.

    :param arr: Lista de elementos a serem ordenados.
    :param low: Índice inicial.
    :param high: Índice final.
    """
    if low < high:
        pi = partition(arr, low, high)  # Índice do pivô

        # Ordena recursivamente as sublistas
        quick_sort(arr, low, pi - 1)
        quick_sort(arr, pi + 1, high)


# Testes
if __name__ == "__main__":
    data = [10, 7, 8, 9, 1, 5]
    print("Lista original:", data)
    quick_sort(data, 0, len(data) - 1)
    print("Lista ordenada:", data)
# 10.-Quick-Sort
