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

### Análise Exploratória e Sanity Check:


#### Etapa 3 - Preparação dos Dados
Limpeza e Formatação dos Dados:

- Exclusão somente dos outliers extremos na variável idade com presença insignificante quanto a frequência absoluta.
- Optou-se pela exclusão dos outliers com salário anual acima de 1.000.000 pois é uma amostragem insignificante (8 clientes) para o método estátistico que utilizaremos.
- A variável tempo de emprego apresentou dados null em grande quantidade, sendo substituída por zero para se enquadrar numa faixa exclusiva para entender a sua concentração. Além da substiuição de outliers exrtemos pela mediana.
- Taxa de juros apresentou 10% de dados faltantes sendo subtituídos por zero e inseridos na faixa de 0 a 2% para demarcar sua frequência. 


#### Etapa 4 - Desenvolvendo o Estudo ou Modelo
Escolha da Técnica Estatística que Responde o Problema:

Para verificar quais fatores/variáveis estão mais relacionados com a taxa de inadimplência, vamos utilizar a técnica estatística Information Value (IV).

Essa técnica é responsável por mensurar o "poder de separação" que uma variável possui sobre a nossa variável target (no caso, inadimplência).

Se uma variável tem poder forte, isso significa que uma ou mais categorias da variável tem um alto ou baixo nível de inadimplência, sendo útil estuda-las com mais profundidade.

Quais fatores separam um cliente inadimplente de um adimpente? Idade, Renda Anual, Moradia, Tempo de Emprego, Objetivo do Empréstimo, Categoria, Valor do Empréstimo, Taxa de Juros, Comprometimendo da Renda, Histórico de Inadimplência e Tempo de Histórico de Crédito.


<p align="center">
<img src="https://github.com/user-attachments/assets/300c8371-2772-4670-8747-91ef65ac9752"
" width="500" alt="image">
</p>


Desenvolvimento do Estudo Analítico ou Modelo:

Colunas da tabela.
- Frequência Absoluta (contagem dos clientes inadimplentes e adimplentes);
- Frequência Relativa (percentual de clientes inadimplentes e adimplentes);
- Taxa de Inadimplência (é a probalidade de inadimplência dos clientes);
- Odds (é a proporção que compara o evento ocorrer com a probabilidade de um evento não ocorrer);
- LN (é utilizado para transformar a razão em uma escala mais estável);

O cálculo é desenvolvido da seguinte forma:
Primeiramente, encontra-se a frequência absoluta das categorias da variável selecionada com uma contagem simples dos clientes, em seguida a frequência relativa, dividindo a quantidade de clientes da categoria pelo Total Geral dos Clientes.

Em seguida, calcula-se a Taxa de Inadimplência que é a quantidade de clientes inadimplentes pelo total da categoria da variável selecionada. O resultado é o valor percentual da taxa de inadimplência por categoria e a taxa média.

Para cálcular o Infomation Value necessitamos da Odds (chance) que é a divisão do percentual relativo da inadimplência pelo percentual relativo da inadimplência da categoria.

Encontra-se o LN da Odds, para enfim encontrar o valor do Information Value da categoria da variável: percentual da inadimplência menos o percentual de adimplentes multiplicados pelo LN, para fnalizar o IV Total será o somário de todos os IV das categorias da variável selecionada para verificar o poder de separação.

<img width="1748" height="307" alt="image" src="https://github.com/user-attachments/assets/e1db5c6f-d601-4bb9-b437-a55d3038f360" />



---
## ✅ Resultados

---
## 🚀 Próximos Passos
