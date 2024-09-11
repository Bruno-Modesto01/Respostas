# Respostas
1) K = 1, SOMA = 0 + 1 = 1
 K = 2, SOMA = 1 + 2 = 3
 K = 3, SOMA = 3 + 3 = 6
...
 K = 13, SOMA = 78 + 13 = 91

2) def fibonacci_sequence(limit):
    fib_sequence = [0, 1]
    
    while fib_sequence[-1] < limit:
        fib_sequence.append(fib_sequence[-1] + fib_sequence[-2])
    
    return fib_sequence

def is_in_fibonacci(number):
    fib_sequence = fibonacci_sequence(number)
    return number in fib_sequence

number = 21
result = is_in_fibonacci(number)
result, fibonacci_sequence(number)
Resultado
(True, [0, 1, 1, 2, 3, 5, 8, 13, 21])

3) faturamento_json = """
{
    "faturamento_diario": [
        0, 22174.1664, 24537.6698, 0, 26139.6134, 0, 0,
        34101.3199, 26742.6612, 0, 0, 0, 42889.2258, 46251.174,
        11191.4722, 0, 0, 0, 3847.4823, 373.7838, 2659.7563,
        48924.2448, 18419.2614, 0, 0, 0, 35240.1826, 43829.1667,
        18235.6852, 4355.0662, 13327.1025
    ]
}
"""


dados = json.loads(faturamento_json)
faturamento_diario = dados["faturamento_diario"]

Filtrar dias com faturamento (exclui finais de semana e feriados)
faturamento_valido = [valor for valor in faturamento_diario if valor > 0]

 Calculando o menor e maior valor de faturamento
menor_faturamento = min(faturamento_valido)
maior_faturamento = max(faturamento_valido)

Calculando a média de faturamento
media_faturamento = sum(faturamento_valido) / len(faturamento_valido)

Contar dias com faturamento acima da média
dias_acima_da_media = len([valor for valor in faturamento_valido if valor > media_faturamento])

 Exibindo os resultados
print(f"Menor valor de faturamento: R$ {menor_faturamento:.2f}")
print(f"Maior valor de faturamento: R$ {maior_faturamento:.2f}")
print(f"Número de dias com faturamento acima da média: {dias_acima_da_media}")
Menor valor de faturamento: R$ 373.78
Maior valor de faturamento: R$ 48924.24
Número de dias com faturamento acima da média: 10

4)  Valores de faturamento por estado
faturamento = {
    "SP": 67836.43,
    "RJ": 36678.66,
    "MG": 29229.88,
    "ES": 27165.48,
    "Outros": 19849.53
}

 Calcula o total
total = sum(faturamento.values())

 Calcula o percentual de cada estado
percentuais = {estado: (valor / total) * 100 for estado, valor in faturamento.items()}

 Exibe o resultado
for estado, percentual in percentuais.items():
    print(f"{estado}: {percentual:.2f}%")

5) def inverter_string(s):
    string_invertida = ""
    for i in range(len(s) - 1, -1, -1):
        string_invertida += s[i]
    return string_invertida


string_original = input("Digite uma string para inverter: ")
print("String invertida:", inverter_string(string_original))
    

