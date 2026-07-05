# Reducao-Inadimplencia-Fintech

---
Imagem Fintech

---
## 📊 Contexto do Projeto
Uma fintech especializada em concessão de crédito pessoal digital vem enfrentando um crescimento expressivo na sua base de clientes nos últimos 18 meses. Com a expansão acelerada da operação, houve também um aumento relevante nos índices de inadimplência, impactando diretamente a rentabilidade da carteira e elevando o custo de aquisição de novos clientes.

Atualmente, a empresa concede crédito com base em regras tradicionais de aprovação, utilizando informações cadastrais, renda declarada, histórico de relacionamento e comportamento transacional. No entanto, a ausência de uma análise mais aprofundada sobre os fatores que influenciam a inadimplência tem gerado aprovações com alto risco e aumento das perdas financeiras.

Além do impacto financeiro, o crescimento da inadimplência compromete indicadores estratégicos como provisão de perdas, liquidez operacional e capacidade de expansão da carteira de crédito.

Diante desse cenário, a área de Dados foi acionada para desenvolver uma análise estruturada com foco na identificação dos principais perfis de risco e na criação de estratégias preventivas para redução da inadimplência.

---
### 🎯 Objetivos
O principal objetivo deste projeto é identificar quais variáveis possuem maior influência sobre a inadimplência dos clientes, permitindo a construção de estratégias mais assertivas para concessão de crédito, revisão de políticas internas e mitigação de perdas financeiras.

---
## 🗂️ Dataset
- Tabela fato credito formato csv.

---
## 🛠️ Tecnologias Utilizadas
- Power Query - Transformação dos dados;
- Github - Documentação do projeto.

---
## 🧱 Modelagem de Dados

---
## 🔄 Pipeline de Dados (ELT)
O pipeline do projeto segue as seguintes etapas:
- Extração: Coleta de dados estruturados a partir de arquivos csv (credito);
- Transformação: Tratamento, limpeza dos dados brutos utilizando o Power Query;
- Visualização: Modelagem e consolidação das informações no Power BI para geração de dashboard e análise de indicadores.

Imagem Arquitetura
---
## 🧭 Estratégia da Solução
Para garantir uma abordagem estruturada, orientada ao negócio e com foco em geração de valor, a estratégia deste projeto será conduzida com base no framework CRISP-DM (Cross Industry Standard Process for Data Mining), amplamente utilizado em projetos de Ciência de Dados, Analytics e Crédito.

Esse modelo permite organizar o desenvolvimento analítico em etapas bem definidas, assegurando que a solução não fique restrita apenas à construção de análises técnicas, mas esteja diretamente conectada ao problema real de negócio: a redução da inadimplência na concessão de crédito.

A aplicação do CRISP-DM neste projeto seguirá as seguintes fases:

</br>

<p align="center">
<img src="https://github.com/user-attachments/assets/7c6b0c8a-875e-47ab-bce1-00ba26b4f109"
" width="500" alt="image">
</p>

#### Etapa 1 - Entendimento de Negócio
Objetivo:

Nesta etapa, o foco está na compreensão do problema enfrentado pela fintech e no alinhamento dos objetivos estratégicos da análise.
Foi identificado que o crescimento da inadimplência está impactando diretamente a rentabilidade da carteira de crédito, aumentando perdas financeiras e reduzindo a eficiência operacional da concessão de empréstimos.

O objetivo de negócio definido foi reduzir a inadimplência por meio da identificação de variáveis de risco e da construção de estratégias preventivas de concessão de crédito.

Antes de iniciar a análise, podemos organizar o problema de inadimplência em uma árvore de decisão. A ideia é separar os fatores que mais estão associados a inadimplência  em grandes hipóteses e, depois, quebrar cada hipótese em causas mais específicas para a análise estatística.


<p align="center">
<img src="https://github.com/user-attachments/assets/0c84443d-0605-4ed4-b96c-afca45833d02"
" width="700" alt="image">
</p>

Premissa:

- Outliers com idades extremas seram excluídas da base;
- Clientes com salário anual acima de 1.000.000,00 não seram considerados na análise, pois a amostragem é mínima.

Critérios de Sucesso:

- 1° Tabelar as variáveis com maior fator de risco com relação a inadimplência;  
- 2° Plano de ação para diminuir a taxa de inadimplência somente das variáveis de maior impacto.



#### Etapa 2 - Entendimento dos Dados
Descrição dos Dados e Coleta:

- Metadados do Projeto

<p align="center">
<img src="https://github.com/user-attachments/assets/7ef413ce-51bb-4f90-955f-95dfcab52ae8"
" width="800" alt="image">
</p>

Análise Exploratória e Sanity Check:







---
## ✅ Resultados

---
## 🚀 Próximos Passos
