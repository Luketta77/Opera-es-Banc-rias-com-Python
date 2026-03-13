Desafio de codigo basico sobre uso de Excel e SQL em contexto de banco e mercado financeiro. Uma equipe de analistas usa planilhas Excel e consultas SQL para acompanhar saldos, limites de credito e historico de transacoes dos clientes. Preciso criar um programa que receba o nome de um uso comum de Excel ou SQL no contexto bancario e retorne uma breve descricao desse uso.

Caso o nome informado nao exista na lista de opcoes, o sistema deve retornar: Tecnica desconhecida.

Entrada
O programa deve ler uma string com o nome de um dos usos a seguir:

"Relatorio de juros em planilha Excel"
"Tabela de clientes com limite de credito"
"Consulta SQL de saldo por cliente"
"Consulta SQL de historico de transacoes"
Saida
O programa deve imprimir uma string com a descricao correspondente:

Calculo de juros sobre saldos usando colunas da planilha
Lista dados de clientes e campo com limite de credito
Filtra tabela de contas para mostrar saldo de cada cliente
Usa SQL para buscar transacoes antigas de uma conta
Se a entrada nao corresponder a nenhuma das opcoes validas, o programa deve imprimir:

Conclusão do desafio:

entrada = input().strip()

def descrever_uso(nome):
    if nome == "Relatorio de juros em planilha Excel":
        return "Calculo de juros sobre saldos usando colunas da planilha"

    elif nome == "Tabela de clientes com limite de credito":
        return "Lista dados de clientes e campo com limite de credito"

    elif nome == "Consulta SQL de saldo por cliente":
        return "Filtra tabela de contas para mostrar saldo de cada cliente"

    elif nome == "Consulta SQL de historico de transacoes":

        return "Usa SQL para buscar transacoes antigas de uma conta"

    else:
        return "Tecnica desconhecida"

print(descrever_uso(entrada))


Desafio 2 

Desafio
Você faz parte da equipe de tecnologia de um grande banco e recebeu uma missão importante: ajudar o setor financeiro a organizar rapidamente os lançamentos diários de despesas e receitas. Cada lançamento é registrado como uma string contendo o tipo (D para despesa, R para receita) seguido do valor em reais, separados por espaço. Sua tarefa é criar uma função que, ao receber uma lista desses lançamentos em uma única linha, calcule o saldo final do dia. O saldo é a soma de todas as receitas menos a soma de todas as despesas. O resultado deve ser apresentado com duas casas decimais, mesmo que o valor seja inteiro. Não utilize bibliotecas externas.

Implemente uma função que leia uma linha contendo lançamentos separados por vírgula, processe cada um conforme o tipo e valor, e imprima o saldo final do dia no formato especificado. Considere que todos os valores são números positivos e que pode haver tanto receitas quanto despesas, ou apenas um dos tipos.

Entrada
Uma única linha contendo lançamentos separados por vírgula. Cada lançamento é composto por uma letra (D ou R), seguida de um espaço e um valor decimal positivo.

Saída
Uma única linha contendo o saldo final do dia, com duas casas decimais.

Exemplos
A tabela abaixo apresenta exemplos de entrada e saída:

Entrada	Saída
R 100.00,D 50.00,R 20.00	70.00
R 10.00,R 25.50,R 14.50 	50.00
R 200.00                	200.00
D 100.00,D 50.00	       -150.00


Completei o TODO somando receitas (R) e subtraindo despesas (D):

# Lê a linha de lançamentos do stdin
entrada = input().strip()

# Inicialize o saldo do dia
saldo = 0.0

# Divide os lançamentos pela vírgula
lancamentos = entrada.split(',')

for lancamento in lancamentos:
    tipo, valor = lancamento.strip().split()
    valor = float(valor)
    
    if tipo == 'R':
        saldo += valor
    elif tipo == 'D':
        saldo -= valor

# Imprima o saldo final com duas casas decimais
print(f"{saldo:.2f}")

Desafio 3 

Desafio
O Banco ByteSafe é conhecido por sua eficiência digital, mas recentemente um bug no sistema causou a duplicação de algumas transações em seu extrato online. Como analista de dados do banco, você foi encarregado de criar uma ferramenta que ajude a identificar e remover essas inconsistências. Cada linha do extrato é uma sequência de identificadores de transações, separados por espaço, e pode conter transações repetidas. Sua missão é garantir que cada transação apareça apenas uma vez, mantendo a ordem da primeira ocorrência. Assim, o extrato ficará limpo e sem duplicatas, facilitando a conferência dos clientes e a auditoria do banco.

Implemente uma função que receba uma string com identificadores de transações separados por espaço e retorne uma nova string, também separada por espaço, contendo apenas a primeira ocorrência de cada transação, na ordem em que aparecem originalmente. Não utilize bibliotecas externas para manipulação de listas ou conjuntos.

Entrada
Uma única linha contendo identificadores de transações separados por espaço. Cada identificador é uma sequência de caracteres alfanuméricos sem espaços.

Saída
Uma única linha contendo os identificadores de transações, separados por espaço, sem repetições e na ordem da primeira ocorrência.

Exemplos
A tabela abaixo apresenta exemplos de entrada e saída:

Entrada	                            Saída
TX1001 TX1002 TX1001 TX1003	     TX1001 TX1002 TX1003
AB12 CD34 AB12 EF56 CD34	     AB12 CD34 EF56
QW1 ER2 TY3                      QW1 ER2 TY3
AA BB AA AA BB CC	             AA BB CC

Resoluçãao:

# Leitura da linha de identificadores de transações
entrada = input()

transacoes = entrada.split()
transacoes_unicas = []

for t in transacoes:
    if t not in transacoes_unicas:
        transacoes_unicas.append(t)

print(' '.join(transacoes_unicas))
