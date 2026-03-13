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
