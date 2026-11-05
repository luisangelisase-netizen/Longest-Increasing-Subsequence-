Longest Increasing Subsequence (LIS)
Dada uma sequência de números inteiros, encontre o tamanho da maior subsequência estritamente crescente (não necessariamente contínua). Uma subsequência é formada removendo zero ou mais elementos da sequência original, sem alterar a ordem relativa dos elementos restantes. Crie uma solução utilizando programação dinâmica para determinar o comprimento da Longest Increasing Subsequence (LIS).

Entrada: sequência = {10, 22, 9, 33, 21, 50, 41, 60}

Saída: 5

_____________________________________



def lis(sequencia):
    n = len(sequencia)

    if n == 0:
        return 0

    dp = [1] * n

    for i in range(1, n):
        for j in range(i):
            if sequencia[j] < sequencia[i]:
                dp[i] = max(dp[i], dp[j] + 1)

    return max(dp)


sequencia = [10, 22, 9, 33, 21, 50, 41, 60]

print("Comprimento da LIS:", lis(sequencia))
