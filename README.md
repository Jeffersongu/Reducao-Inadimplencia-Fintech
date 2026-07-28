# Reducao-Inadimplencia-Fintech
---

<img width="1200" height="500" alt="image" src="https://github.com/user-attachments/assets/292ab99c-b1e7-4d58-8089-e7718993af5f" />

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
- Análise - Tabela Dinâmica;
- GitHub - Documentação do projeto.

---
## 🔄 Pipeline de Dados (ETL)
O pipeline do projeto segue as seguintes etapas:
- Extração: Coleta de dados estruturados a partir de arquivos csv (credito);
- Transformação: Tratamento, limpeza dos dados brutos na própria base;
- Visualização: Consolidação das informações através da Análise do Information Value com o recurso da tabela dinâmica.

</br>
<p align="center">
<img src="https://github.com/user-attachments/assets/3c5edba9-47a2-4e8d-bc0a-44eaa434c5fd"
" width="600" alt="image">
</p>

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

Antes de avançar, validamos a consistência da base:

O Sanity Check foi executado para verificação da qualidade dos dados, validando volumetria, tipos e consistência antes de seguir para a preparação da base.
- Total de empréstimos na base original: 32.581 (32.567 após tratamento).
- 22% de inadimplência é muito alto para uma fintech — o benchmark de mercado gira em torno de 2 a 5%.

Variável Idade:
- Concentração de 95% da base entre 20 e 39 anos (30.816 clientes).
- Faixa 20-29 (Geração Z) é a maior, com 72% da base.
- 50% dos clientes têm até 26 anos.
- Boxplot revelou outliers extremos (idades entre 41 e 144 anos) — recomenda-se excluir apenas os valores mais extremos (94, 123, 144), por indício de erro de digitação, mantendo os demais por não comprometerem a análise.

Variável Renda Anual
- 88% da base concentra-se entre R$ 4.000 e R$ 103.999 (28.626 clientes).
- Sem dados faltantes ou erros de digitação.
- Recomendação exclusão dos 8 clientes com renda acima de R$ 1.000.000 por amostragem insignificante para o método estatístico aplicado.

Variável Tempo de Emprego
- 89% da base concentra-se nas duas primeiras faixas (28.947 clientes).
- Dois outliers extremos (123 anos de tempo de emprego) substituídos pela mediana.
- Grande volume de dados nulos, reocmendação substituir por zero e enquadrar na faixa 0-4 para preservar a análise de concentração.

Variável Valor do Empréstimo
- 75% dos empréstimos concentram-se em três faixas de valor (24.528 clientes).
- Outliers não apresentam comportamento extremo fora do normal — mantidos sem alteração.
- Sem dados faltantes ou erros de inserção.

Variável Taxa de Juros
- 80% dos empréstimos concentram-se nas faixas centrais de 6% a 16% (26.233 clientes).
- 10% dos dados estavam faltantes: reocmendação substituir por zero e agrupa-los na faixa 0-2% para demarcar a frequência sem descartar os registros.

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

#### Analisando a variável Idade:
<img width="1748" height="307" alt="image" src="https://github.com/user-attachments/assets/e1db5c6f-d601-4bb9-b437-a55d3038f360" />

- A taxa de inadimplência dos clientes desta base não demonstra concentração relevante de inadimplência entre as faixas de idade, os percentuais da taxa de inadimplência ficaram muito próximos a taxa média.
- A chance que é a divisão percentual de clientes que não pagaram o empréstimo pelos clientes que pagaram, obteve-se valores próximos a um. Por tanto, a chance do cliente pagar ou não o empréstimo é igual.
- Conclui-se que não há evidências de que a taxa de inadimplência esteja mais associada a uma faixa etária específica.
- O IV Total corresponde a 0,00 com poder de separação classificado como Muito Fraco.

#### Analisando a variável Salário Anual:
<img width="1751" height="396" alt="image" src="https://github.com/user-attachments/assets/544d47e1-61b3-4dd6-960e-ae21c46e8549" />

- A taxa média de inadimplência dos clientes apresentou concentração relevante com relação a faixa salarial entre 4000-53999.
- Clientes na faixa salarial de 4.000,00 a 53.999,00 apresentam probabilidade de inadimplência de 30,78% (9 pp acima da média).
- O IV Total corresponde a 0,28 com poder de separação classificado como Médio.

#### Analisando a variável Tipo de Moradia:
<img width="1747" height="282" alt="image" src="https://github.com/user-attachments/assets/9714e567-b9b4-42ce-a081-10040f1f7c1a" />

- A taxa média de inadimplência dos clientes apresentou concentração relevante com relação a dois tipos de moradia: Rent e Other.
- Clientes com tipo de moradia de Aluguel apresenta probabilidade de inadimplência de 31,58% (10 pp acima da média).
- O cenário se mantém semelhante para o tipo Outros onde a probabilidade de inadimplência atinge 30,84%, o que representa 9 pontos percentuais (pp) acima da média geral do portfólio.
- O IV Total corresponde 0,38 com poder de separação classificado como Forte.

#### Analisando a variável Tempo de Emprego:
<img width="1748" height="348" alt="image" src="https://github.com/user-attachments/assets/37858302-bea5-4711-9105-547f0e6f4e8e" />

- A taxa de inadimplência dos clientes desta base não demonstra concentração relevante de inadimplência com as faixas de tempo de emprego.
- A chance que é a divisão percentual de clientes que não pagaram o empréstimo pelos clientes que pagaram, obteve-se resultados próximos de um. Por tanto, a chance do cliente pagar ou não o empréstimo é igual.
- Conclui-se que não há evidências de a taxa de inadimplência esteja mais associada a uma faixa de tempo de emprego específica.
- O IV Total corresponde a 0,05 com poder de separação classificado como Fraco.

#### Analisando a variável Objetivo:
<img width="1746" height="322" alt="image" src="https://github.com/user-attachments/assets/dfe0b68e-d167-4665-b40f-3691ae08aa7a" />

- A taxa de inadimplência dos clientes desta base não demonstra concentração relevante de inadimplência por objetivo do empréstimo, os percentuais da taxa de inadimplência ficaram próximas a taxa média.
- A chance que é a divisão percentual de clientes que não pagaram pelos clientes que pagaram, obteve-se valores muito próximos, ou seja, o resultado fica próximo de 1. Logo, a chance do cliente pagar ou não é igual.
- Conclui-se que não há evidências que a taxa de inadimplência esteja mais associada a um objetivo específico.
- O IV Total corresponde a 0,10 com poder de separação classificado como Fraco.

#### Analisando a variável Categoria:
<img width="1745" height="348" alt="image" src="https://github.com/user-attachments/assets/8f5fecd6-8ddd-4bb3-b33e-d663c1c6ccef" />

- A taxa de inadimplência dos clientes apresentou concentração relevante nas categorias D, E, F e G progressivamente.
- Clientes na categoria D apresentam uma inadimplência de 59,05% (37 pp acima da média).
- Clientes na categoria E apresentam uma inadimplência de 64,42% (43 pp acima da média).
- Clientes na categoria F apresentam uma inadimplência de 70,54% (49 pp acima da média).
- O cenário é ainda mais severo na categoria G, onde a probabilidade de inadimplência atinge 98,44%, representando 77 pp acima da média geral da base. No entanto, é uma amostra muito pequena frente as demais.
- O IV Total corresponde a 0,88 com poder de separação classificado como Muito Bom.

#### Analisando a variável Valor do Empréstimo:
<img width="1750" height="393" alt="image" src="https://github.com/user-attachments/assets/726fe246-8b8c-490e-b9eb-12eb64951193" />

- A taxa de inadimplência dos clientes desta base não demonstra concentração relevante de inadimplência entre as faixas do valor do empréstimo.
- Conclui-se que não há evidências que a taxa de inadimplência esteja mais associada a uma faixa de valor do empréstimo específica.
- O IV Total corresponde a 0,08 com poder de separação classificado como Fraco.

#### Analisando a variável Taxa de Juros:
<img width="1747" height="373" alt="image" src="https://github.com/user-attachments/assets/79259374-5149-49ec-be09-fa810bbcfd2b" />

- A taxa de inadimplência dos clientes apresenta uma tendência de alta clara conforme a taxa de juros aumenta, tornando-se crítica a partir de 14% ao ano.
- Clientes na faixa de 14% a 16% de juros apresentam uma inadimplência de 47,05% (25 pp acima da média).
- O cenário é ainda mais severo na faixa superior a 16%, onde a probabilidade de inadimplência atinge 62,85%, o que representa 41 pontos percentuais (pp) acima da média geral do portfólio.
- O IV Total corresponde a 0,67 com poder de separação classificado como Muito Bom.

#### Analisando a variável Percentual de Comprometimento da Renda:
<img width="1747" height="326" alt="image" src="https://github.com/user-attachments/assets/690d687d-72d5-4f89-b8d3-df49c5c9e9e3" />

- A taxa de inadimplência dos clientes apresenta uma tendência de alta clara conforme o percentual de comprometimento da renda aumenta, tornando-se cítica a partir de 30%.
- Clientes na faixa de 30% a 40% de comprometimento da renda apresenta uma inadimplência de 61,76% (40 pp acima da média).
- Clientes na faixa de 40% a 50% de comprometimento da renda aprensenta uma inadimplência de 72,49% (50 pp acima da média).
- O cenário é ainda mais severo na faixa superior a 50%, onde a probabilidade de inadimplência atinge 78,63%, que representa 57 pontos percentuais (pp) acima da média geral do portfólio.
- O IV Total corresponde a 0,86 com poder de separação classificado como Muito Bom.

#### Analisando a variável Histórico de Inadimplência:
<img width="1745" height="241" alt="image" src="https://github.com/user-attachments/assets/23246bdc-822d-43fe-9834-f998241268c8" />

- A taxa de inadimplência dos clientes apresentou concentração com relação ao histórico de inadimplência.
- Clientes com histórico positivo tem probabilidade de inadimplência de 37,81% (16 pp acima da média).
- O IV Total corresponde a 0,16 com poder de separação classificado como Médio.

#### Analisando a variável Tempo de Crédito:
<img width="1747" height="328" alt="image" src="https://github.com/user-attachments/assets/1bddc5bd-6083-4f02-b2aa-541ddc104c2d" />

- A taxa de inadimplência dos clientes desta base não demonstra concentração relevante de inadimplência por tempo de crédito, os percentuais da taxa de inadimplência ficaram próximos a taxa média.
- A chance que é a divisão percentual de clientes que não pagaram pelos clientes que pagaram, obteve-se resultados muito próximos de um.  Logo, a chance do cliente pagar ou não é igual.
- Conclui-se que não há evidências que a taxa de inadimplência esteja mais associada a uma faixa de tempo de histórico de crédito específica.
- O IV Total corresponde a 0,00 com poder de separação classificado como Muito Fraco.


#### Etapa 5 - Validação do Trabalho
Verificação do Critério de Sucesso:

1° Tabelar as variáveis com maior fator de risco com relação a inadimplência;

Critério adotado com sucesso, a tabela apresenta as variáveis com o valor do Information Value em ordem decrescente do grau de separação. As variáveis com maior poder de influência sobre a inadimplência são: Categoria, Percentual de comprometimendo da renda, Taxa de juros e Tipo de moradia.

<p align="center">
<img src="https://github.com/user-attachments/assets/3539654d-7d1d-4ad0-b68e-5ab88680f9a0"
" width="800" alt="image">
</p>

2° Plano de ação para diminuir a taxa de inadimplência somente das variáveis de maior impacto.

<img width="1467" height="529" alt="image" src="https://github.com/user-attachments/assets/685ac081-6258-431f-8140-060220c1acba" />

#### Etapa 6 - Deploy - Implantação
Plano de implantação e Monitoramento do Estudo ou Modelo:

Adotaremos o plano de ação 2 com o estabelecimento um teto máximo de comprometimento de renda em 30%, pois a inadimplência salta de 21% para 61,76%, na próxima etapa será mensurado o impacto financeiro desse plano.

---
## 💲 Valor
Mensurando o impacto financeiro do plano de ação 2, o cálculo será desenvolvido em três operações:
- Operação de Crédito antes da Análise de Dados
  
  O total do empréstimo corresponde a soma dos clientes adimplentes e inadimplentes da base, a Receita Esperada é formada por 40% de juros em média dessa operação do total do empréstimo concedido a base de clientes, a perda esperada é dada pelos clientes inadimplentes. O ROE é obtido pela receita esperada menos a perda dada pela inadimplência dividido pelo total do empréstimo com um resultado de 15%, o lucro dessa operação resultou em R$ 47.795.275,00.

- Operação de Crédito depois da Análise de Dados (Plano de Ação 2)

  Com a implementação do plano de ação 2, houve uma redução no total do empréstimo, pois aplicamos um limite sobre o percentual de comprometimento da renda em até 30% com isso a uma redução no número de empréstimos, a receita esperada também reduziu, porém a perda esperada reduziu e o ROE aumentou para 26%, com um aumento na lucratividade em R$ 62.730.705,00.
  
- Efeito da Melhoria

  A inadimplência antes de 21,83% caiu para 15,21% somente com a aplicação de um único plano de ação, em contrapartida a receita reduziu em R$ 26.674.920,00, já perda esperada pela inadimplência reduziu em R$ 41.610.350,00. O ROE teve um aumento de 10 pontos pencetuais e aumento no lucro de R$ 14.935.430,00.

<img width="2165" height="709" alt="image" src="https://github.com/user-attachments/assets/bcf7c951-d6b5-419a-90e0-56f0d5997b9c" />


---
## 🚀 Próximos Passos
- Criação de um dashboard de acompanhamento da inadimplência com os grupos controle e teste para cada plano de ação implementado;
- Realizar a limpeza dos dados com auxílio do Power Query ou outra ferramenta de tratamento para garantir automação.
