# Calculadora_Matematica_Py
Uma calculadora  simples para calculos

import math

def calculadora_basica(operacao, num1, num2=None):
  if operacao == "soma":
    resultado = num1 + num2
  elif operacao == 'subtracao':
    resultado = num1 - num2
  elif operacao == 'multiplicacao':
    resultado = num1 * num2
  elif operacao == 'divisao':
    if num2 != 0:
      resultado = num1 / num2
    else:
      return 'Erro: divisão por zero'
  elif operacao == 'raiz quadrada':
    resultado = math.sqrt(num1)
  else:
    return 'Operação não reconhecida'

  return resultado

# Loop para permitir várias operações

while True:
  print("Escolha uma operação")
  print("1 - soma")
  print("2 - subtração")
  print("3 - multiplicação")
  print("4 - disão")
  print("5 - raiz quadrada ")
  print("0 sair ")

  escolha = input("Digite o número da operação desejada (ou 0 para sair): ")
# Onde vai ser gerado os calculos determinado pelo usuario 
  if escolha == '0':
    print("saindo da calculadora.")
    break

  if escolha in ['1', '2', '3', '4', '5']:
    num1 = float(input("Digite o primeiro número: "))

  if escolha != '5':
    num2 = float(input("Digite o segundo número: "))

  if escolha == '4' and num2 == 0:
    print("Erro: divisão por zero")
  else:
    operacoes = ['soma', 'subtracao', 'multiplicacao', 'divisao', 'raiz_quadrada']
    resultado = calculadora_basica(operacoes[int(escolha) - 1], num1, num2)
    print(f"Resultado: {resultado}")
