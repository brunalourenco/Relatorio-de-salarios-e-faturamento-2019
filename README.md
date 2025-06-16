# Relatorio-de-salarios-e-faturamento-2019

Repositório de dashboard desenvolvido em Power BI como exercício de treinamento da Hashtag Treinamentos.

## Objetivo
Fazer uma análise de uma empresa prestadora de serviços de consultoria.

## Dados

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
