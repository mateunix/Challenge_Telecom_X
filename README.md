#📡 Telecom X - Análise de Evasão de Clientes (Churn)
##📋 Sobre o Projeto
A Telecom X enfrenta um desafio crítico: uma alta taxa de cancelamento de clientes (Churn). Este projeto de Data Analytics tem como objetivo identificar os perfis de risco, entender os motivos da evasão e fornecer recomendações baseadas em dados para a equipe de negócios.

O projeto abrange desde a extração de dados brutos (API/JSON) até a análise exploratória e visualização estratégica.

##🛠️ Pipeline de Dados (ETL)
O script main.py executa um fluxo de trabalho automatizado:

Extração: Coleta de dados via requisição HTTP (simulação de API) de um dataset JSON aninhado.

Transformação (Normalização): Uso de pd.json_normalize para "achatar" colunas complexas (customer, phone, internet, account).

Limpeza (Data Cleaning):

Tratamento de strings vazias na variável alvo (Churn).

Conversão de Charges.Total de texto para float.

Padronização de textos (remoção de espaços).

Engenharia de Atributos (Feature Engineering):

Criação de Custo_Diario (Mensalidade / 30).

Criação de Qtd_Servicos (Soma dos serviços adicionais contratados).

Padronização: Tradução de todas as colunas para Português e codificação de variáveis binárias (Sim/Não → 1/0).

##📊 Principais Descobertas e Insights
Com base na Análise Exploratória de Dados (EDA), identificamos os seguintes padrões de comportamento:

1. O Fator Contratual 🚨
Diagnóstico: Clientes com Contrato Mensal representam a esmagadora maioria das evasões.

Dado: A taxa de churn cai drasticamente em contratos de 1 ou 2 anos.

Ação Sugerida: Criar campanhas agressivas de migração para planos anuais, oferecendo descontos ou benefícios exclusivos.

2. Tecnologia e Preço 💸
Diagnóstico: Usuários de Fibra Óptica tendem a cancelar mais do que usuários de DSL, apesar de ser uma tecnologia superior.

Hipótese: Correlação direta com o preço (Cobranca_Mensal mais alta) ou insatisfação técnica específica.

Ação Sugerida: Revisar a estratégia de precificação da Fibra e investigar chamados de suporte técnico nessa categoria.

3. A "Zona de Perigo" (Tenure) ⏳
Diagnóstico: A maior parte dos cancelamentos ocorre nos primeiros meses de contrato.

Ação Sugerida: Implementar um programa de Onboarding (boas-vindas) focado na retenção durante os primeiros 6 meses.

4. Meios de Pagamento 💳
Diagnóstico: O método "Cheque Eletrônico" apresenta uma taxa de evasão muito superior aos pagamentos automáticos (Cartão de Crédito/Transferência).

Ação Sugerida: Incentivar o cadastro de débito automático para reduzir o atrito de pagamento mensal.
