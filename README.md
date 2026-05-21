# Análise de Churn e Impacto Financeiro em Operações de Telecom

Análise preditiva e financeira de Churn (cancelamentos de clientes) desenvolvida para identificar falhas técnicas recorrentes, calcular o tempo de vida dos contratos e projetar o impacto real no caixa da empresa.

##  O Problema de Negócio (O Porquê)
No setor de provedores de internet (ISPs), a perda de clientes (Churn) gera um impacto duplo: a perda imediata da receita mensal recorrente (MRV) e o desperdício do custo de aquisição do cliente (CAC). O objetivo deste projeto foi cruzar os dados contratuais de cancelamento com o histórico de ordens de serviço (O.S.) técnico para entender se falhas operacionais/técnicas na rede estavam motivando as saídas e quantificar o prejuízo anualizado.

## 🛠️ O Que Foi Feito (O Como)
O script realiza um pipeline completo de Engenharia e Análise de Dados utilizando Python:

1. **Limpeza e Padronização:** Extração de IDs de strings complexas, tratamento de strings (normalização de assuntos de chamados para caixa alta) e conversão de valores monetários e datas.
2. **Isolamento de Falhas Reais:** Criação de uma lista de exclusão de O.S. de rotina (ex: retirada de equipamento, mudança de endereço) para filtrar estritamente eventos de falhas, quedas e lentidão de sinal.
3. **Engenharia de Recursos (Feature Engineering):** 
   * Cálculo do tempo de casa (Lifetime) dos clientes em meses.
   * Agrupamento por cliente para calcular o total de visitas técnicas gerais e a quantidade de chamados por defeito.
   * Identificação da falha técnica principal por cliente através de agregação de moda (`value_counts().index[0]`).
4. **Análise Financeira Avançada:** Projeção de perda anualizada e cálculo do prejuízo real acumulado no caixa de maio a dezembro de 2026.

## 📊 Relatórios Visuais Gerados
O projeto automatiza a geração de 5 visões gráficas executivas (utilizando `Seaborn` e `Matplotlib`) com identidade visual institucional:
* **Volume e Receita Perdida por Cidade:** Exibe o Churn absoluto e o valor financeiro perdido por região operada.
* **Distribuição de Cancelamentos por Motivo:** Gráfico de Pareto implícito mostrando as principais justificativas dos clientes.
* **Ciclo de Vida do Cliente:** Identificação de faixas críticas de tempo de contrato (ex: identificar se os clientes cancelam mais nos primeiros 3 meses).
* **Previsão de Prejuízo Anualizado:** Projeção estatística caso o ritmo de cancelamentos se mantenha por 12 meses.
* **Buraco no Caixa até o Fim do Ano:** Cálculo realista de receita que deixará de entrar de maio a dezembro de 2026.

## 🚀 Tecnologias Utilizadas
* **Python**
* **Pandas** (Manipulação, Joins e Engenharia de Dados)
* **NumPy** (Tratamento de dados nulos)
* **Matplotlib & Seaborn** (Data Visualization Executiva)

## 📁 Estrutura do Repositório
* `analise_cancelamentos.py`: Script principal com a lógica de tratamento e plots.
* `dados_ficticios/`: Pasta contendo bases mascaradas (com dados falsos) para testes e validação da lógica do script, garantindo a segurança de dados sensíveis.
