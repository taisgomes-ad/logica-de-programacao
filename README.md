# logica-de-programacao
Calculadora Inteligente

"""Explicação para executar o .sh:
Para executar o arquivo sh no seu computador
•	entre no diretório do projeto
use o cd minha-primeira-calculadora
•	de permissão de execução para o arquivo
use o comando chmod +x calculadora.sh
•	por último use o comando ./ antes do arquivo
./calculadora.sh
Explicação do meu código em Python:
1-	Exibe um título no terminal para identificar o programa. O \n adiciona uma quebra de linha para deixar o visual mais organizado.
2-	O while True cria um laço infinito, ou seja, o programa continua rodando até que o usuário escolha sair. Dentro desse laço, todo o funcionamento da calculadora é executado.
3-	O input() captura o que o usuário digita no teclado. Neste caso, são dois números para realizar a operação.
4-	Como o input() retorna um texto (string), é preciso converter os valores para número.
O float() permite números inteiros e decimais.
O bloco try/except serve para evitar erros se o usuário digitar algo que não seja um número (exemplo: letras).
Se ocorrer erro, o programa exibe uma mensagem e volta ao início com continue.
5-	Aqui o programa mostra as opções de cálculo e espera que o usuário escolha uma delas digitando 1, 2, 3 ou 4.
6-	Através de condições (if, elif, else), o código executa a operação escolhida.
Adição (+)
Subtração (-)
Multiplicação (*)
Divisão (/) — com verificação de divisão por zero, que geraria erro.
Se o usuário digitar algo diferente de 1 a 4, aparece “Operação inválida”.
7-	Após exibir o resultado, o programa pergunta se o usuário quer fazer outro cálculo.
Se digitar “s”, o loop recomeça.
Se digitar “n” (ou qualquer outra coisa), o programa mostra uma mensagem de encerramento e o comando break interrompe o laço, finalizando o programa.
"""
#inicio
print(">>> CALCULADORA INTELIGENTE <<<\n")
while True:
# Entrada de dados
num1 = input("Digite o primeiro número: ")
num2 = input("Digite o segundo número: ")
    # Conversão para número (float para permitir números decimais)

    try:
      num1 = float(num1)
      num2 = float(num2)
    except ValueError:
      print("Erro: Por favor, digite números válidos.")
      continue

    # Menu de operações

    print("\nEscolha a operação:\n")
    print("1 - Adição (+)")
    print("2 - Subtração (-)")
    print("3 - Multiplicação (*)")
    print("4 - Divisão (/)")
    escolha = input("\nDigite o número da operação desejada:")

    # Condicional para realizar a operação

    if escolha == "1":
      resultado = num1 + num2
      print(f"Resultado: {num1} + {num2} = {resultado}")
    elif escolha == "2":
      resultado = num1 - num2
      print(f"Resultado: {num1} - {num2} = {resultado}")
    elif escolha == "3":
      resultado = num1 * num2
      print(f"Resultado: {num1} * {num2} = {resultado}")
    elif escolha == "4":
      if num2 == 0:
        print("Erro: Divisão por zero não é permitida.")
      else:
        resultado = num1 / num2
        print(f"Resultado: {num1} / {num2} = {resultado}")
    else:
      print("Operação inválida. Tente novamente.")

    # Verifica se o usuário quer continuar

    continuar = input("\nDeseja fazer outra operação? (s/n): ").lower()
    if continuar != 's':
      print ("Encerrando a calculadora. Até a próxima!")
      break

#fim
