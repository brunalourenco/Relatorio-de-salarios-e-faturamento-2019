# Relatorio-de-salarios-e-faturamento-2019

Repositório de dashboard desenvolvido em Power BI como exercício de curso da Hashtag Treinamentos.

## Objetivo
Fazer uma análise de uma empresa prestadora de serviços de consultoria.

## Dados
* **Cadastro Funcionários**: Tem as informações de cada funcionário: Nome, Data de Nascimento, Salário, Cargo, etc 
* **Cadastro Clientes** : Tem as informações de cada cliente: Nome, Valor de Contrato Anual (quanto que ele paga pra empresa todo ano pela prestação do serviço). 
* **Cadastro Cargos** : Tem as informações de cada Cargo da empresa: Qual é o nível (Diretor, Estagiário, analista, etc) e a área (Administrativo, Logística, etc). 
* **Base Serviços Prestados** : Uma tabela com as informações sobre os serviços de consultoria que são prestados. Na primeira coluna, tem o ID do funcionário que está 
realizando aquele serviço, o ID do cliente que solicitou o serviço e a Data de contratação desse serviço. Nessa planilha, só tem os clientes que ainda estão 
recebendo o serviço da empresa (ou seja, todos ainda são nossos clientes até hoje).

## Medidas
Os cálculos foram feitos através das medidas descritas abaixo:

* % de funcionários que fecharam contrato = divide([Funcionários que fecharam contrato],[Total funcionários])
* Cliente com maior valor de contrato = CALCULATE(MAX(d_Clientes[Valor Contrato Anual]),d_Clientes[Cliente])
* Faturamento Total = SUMX(f_Servicos,f_Servicos[Duracao contrato] * RELATED(d_Clientes[Valor Contrato Anual]))
* Funcionários que fecharam contrato = DISTINCTCOUNT(f_Servicos[ID Funcionário])
* Maior Valor de contrato = Max(d_Clientes[Valor Contrato Anual])
* Qtde contratos = counta(f_Servicos[ID Cliente])
* Salarios Administrativo = CALCULATE(SUM(d_Funcionarios[Total Gastos]),d_Cargos[Área]=="Administrativo")
* Ticket médio contratos = average(d_Clientes[Valor Contrato Anual])
* Total contratos = sum(d_Clientes[Valor Contrato Anual])
* Total funcionários = COUNTA(d_Funcionarios[ID Funcionário])
* Total salarios = sum(d_Funcionarios[Total Gastos])
