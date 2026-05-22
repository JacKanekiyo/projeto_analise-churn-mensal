# Análise de Churn e Impacto Financeiro em Operações de Telecom

Análise preditiva e financeira de cancelamentos de clientes desenvolvida para identificar falhas técnicas recorrentes, calcular o tempo de vida dos contratos e projetar o impacto real no caixa da empresa.

### O Problema de Negócio
No setor de provedores de internet, a perda de clientes gera um impacto duplo: a perda imediata da receita mensal recorrente e o desperdício do custo de aquisição do cliente. O objetivo deste projeto foi cruzar os dados contratuais de cancelamento com o histórico de ordens de serviço técnico para entender se falhas operacionais na rede estavam motivando as saídas e quantificar o prejuízo anualizado.

### O Que Foi Feito
O script realiza uma rotina de engenharia e análise de dados utilizando Python:

1. Limpeza e Padronização: Extração de IDs de strings complexas, tratamento de strings (normalização de assuntos de chamados para caixa alta) e conversão de valores monetários e datas.
2. Isolamento de Falhas Reais: Criação de uma lista de exclusão de ordens de serviço de rotina (como retirada de equipamento e mudança de endereço) para filtrar estritamente eventos de falhas, quedas e lentidão de sinal.
3. Engenharia de Recursos: Cálculo do tempo de casa dos clientes em meses, agrupamento por cliente para calcular o total de visitas técnicas gerais, quantidade de chamados por defeito e identificação da falha técnica principal por cliente através de agregação de moda.
4. Análise Financeira Avançada: Projeção de perda anualizada e cálculo do prejuízo real acumulado no caixa de maio a dezembro de 2026.

### Relatórios Visuais Gerados
O projeto automatiza a geração de cinco visões gráficas executivas utilizando Seaborn e Matplotlib com identidade visual institucional:
* Volume e receita perdida por cidade.
* Distribuição de cancelamentos por motivo declarado.
* Ciclo de vida do cliente com identificação de faixas críticas de tempo de contrato.
* Previsão de prejuízo anualizado caso o ritmo de cancelamentos se mantenha por 12 meses.
* Impacto financeiro de receita que deixará de entrar no caixa até o fim do ano vigente.

### Tecnologias Utilizadas
* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn

### Relatórios Visuais Gerados
O projeto automatiza a geração de cinco visões gráficas executivas utilizando Seaborn e Matplotlib com identidade visual institucional:

* Volume e receita perdida por cidade.

![Volume de Churn por Cidade](./Imagens/Captura de tela 2026-05-22 093655.png)

* Ciclo de vida do cliente com identificação de faixas críticas de tempo de contrato.

![Ciclo de Vida do Cliente](./Imagens/Captura de tela 2026-05-22 093705.png)

### Estrutura do Repositório
* analise_cancelamentos.py: Script principal com a lógica de tratamento e geração de gráficos.
* dados_ficticios/: Diretório contendo bases mascaradas com dados fictícios para testes e validação da lógica do script, garantindo a segurança de dados sensíveis da operação.
* imagens/: Diretório contendo as visualizações gráficas geradas pelo script para exibição e documentação dos resultados no relatório.
