# Desafio Engenharia de Dados - Visagio Rocket Lab 2026

Este repositório guarda o projeto que desenvolvi para a atividade prática do processo seletivo Rocket Lab da Visagio. 

O objetivo do desafio foi atuar como Engenheiro de Dados para estruturar as informações de um grande e-commerce (dataset Olist). 

## O que eu aprendi e utilizei
Durante este projeto, tive a oportunidade de estudar e utilizar na prática:
* **Databricks:** Para criar todo o ambiente de processamento de dados em nuvem.
* **Python e PySpark:** As linguagens que usei para ler, limpar e transformar as informações.
* **Arquitetura Medalhão:** O conceito que usei para organizar os dados em etapas claras (Camadas Bronze, Silver e Gold).

## Como o projeto foi estruturado

Dividi o trabalho em três passos principais (cada um em um notebook):

1. **Camada Bronze (Dados Brutos):** Peguei os arquivos CSV originais do e-commerce e carreguei no Databricks. Também fiz uma conexão com a API do Banco Central para puxar a cotação do dólar. Salvei tudo nessa primeira camada exatamente como veio da origem, apenas adicionando a data e hora em que os dados entraram no sistema.

2. **Camada Silver (Limpeza e Tratamento):** Traduzi os nomes das colunas e dos status dos pedidos do inglês para o português, removi informações duplicadas e calculei coisas novas, como a diferença de dias no tempo de entrega de cada pedido. Também tratei dados vazios e datas inválidas para o código não quebrar.

3. **Camada Gold (Dados Prontos para o Negócio):** Com os dados limpinhos da camada anterior, criei as tabelas finais focadas em responder às perguntas da empresa. Fiz uma tabela com a visão comercial (receita em real e dólar, ticket médio, produtos mais vendidos) e outra com a visão de qualidade (satisfação dos clientes e avaliação dos vendedores).

## Automação
Para fechar o projeto, criei um Workflow (Job) no Databricks. Ele serve para rodar os três códigos automaticamente, na ordem certa (Bronze > Silver > Gold), todos os dias no horário agendado. 

O print do arquivo `.yaml` com essa configuração e um print mostrando que a execução funcionou certinho estão disponíveis aqui nos arquivos do repositório!
