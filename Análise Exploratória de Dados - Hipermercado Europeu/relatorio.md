Descrição: Análise exploratória de dados de um hipermercado, investigando as principais variáveis que impactam a lucratividade do negócio. Compreendendo diferenças de desempenho geográficas, de categoria, de produto e a influência da estratégia de descontos atual.

## Considerações Iniciais

Este projeto é desenvolvido em um contexto hipotético e utiliza dados disponibilizados abertamente na internet para criar um cenário de análise.

Logo abaixo, apresento um relatório detalhado do projeto contendo as explicações e as visualizações. Para a análise completa com o código Python utilizado, visite a seguinte página no GitHub: [Projetos de Análise de Dados](https://github.com/L-Pizzetti/Projetos-De-Analise-De-Dados/blob/main/An%C3%A1lise%20de%20Dados%20de%20Hipermercado%20-%20Estudo%20de%20Desempenho%20no%20Varejo%20Europeu/An%C3%A1lise%20de%20Dados%20de%20Hipermercado.ipynb)

## Ferramentas da Análise

Para realizar esta análise, utilizarei as seguintes ferramentas:

- Python: linguagem de programação, utilizada para todo o processo de análise de dados.
- Jupyter Notebook: para escrever e executar o código.
- Tableau: para criar visualizações geográficas.

As seguintes bibliotecas do Python serão utilizadas:

- Pandas: para manipulação e análise de dados.
- Numpy: para manipulação de vetores e matrizes.
- Matplotlib: para criação de gráficos.
- Seaborn: para criação de alguns gráficos específicos.
- Scipy: para estatística e funções matemáticas.

## 1 — Entendimento do Negócio

### 1.1 — Contexto da Empresa

Uma empresa de médio porte, com presença em boa parte do território da União Europeia, procurou um dos seus especialistas em análise de dados para conduzir um estudo estratégico sobre os dados da empresa.

A empresa em questão atua no setor de varejo, comercializando produtos de diversas categorias. No entanto, nosso foco neste estudo será direcionado para as categorias de material de escritório, móveis e tecnologia. Embora a empresa possua lojas físicas espalhadas pelas principais cidades da Europa, a grande maioria das vendas são realizadas online.

O setor de varejo destaca-se como um dos quais mais podem se beneficiar da análise de dados. Lidando com grandes volumes de produtos e pequenas margens de lucro, as empresas deste ramo enfrentam um ambiente extremamente competitivo e complexo que, frequentemente, demanda delas rápidas tomadas de decisões. A fim de garantir que tais decisões sejam eficazes, elas precisam ser devidamente fundamentadas. Neste contexto, a análise de dados é utilizada para realizar estudos aprofundados sobre a realidade da empresa com intuito de fundamentar essas tomadas de decisões.

### 1.2 — Definição dos Objetivos

O objetivo principal deste projeto reside na condução de uma análise exploratória de dados com o foco na lucratividade da empresa. Os objetivos traçados para este estudo são:

#### Análise de Lucratividade:

**Objetivos:**

- Avaliar a lucratividade da empresa ao longo do tempo.
- Compreender sua relação com diferentes variáveis, como segmentos de clientes, países, regiões, estados, categorias, subcategorias e produtos.
- Investigar o quanto a estratégia atual de descontos pode estar prejudicando o lucro da empresa.

**Valor empresarial:**‍

- Compreender como a lucratividade variou ao longo do tempo, se existem padrões ou tendências que nos possam ajudar a explicar o desempenho atual do negócio.
- Identificar os fatores que possam estar influenciando a lucratividade positiva ou negativamente.
- Descobrir possíveis problemas na estratégia atual de descontos e melhorias que possam ser implementadas para aumentar a margem de lucro, garantindo que os descontos não prejudiquem excessivamente o lucro da empresa.

Com os conhecimentos obtidos pela análise, a empresa poderá tomar decisões mais fundamentadas e eficientes, otimizando a utilização de seus recursos e aumentando a sua lucratividade.

## 2 — Coleta dos Dados

### 2.1 — Descrição do Conjunto de Dados

Os dados utilizados para essa análise consistem em um conjunto de dados de vendas de produtos da categoria de escritório, móveis e tecnologia. O conjunto de dados é composto por 20 colunas e 10.000 linhas, e contém informações sobre vendas realizadas entre 2020 e 2023.

### 2.2 — Descrição das Variáveis

As variáveis presentes no conjunto de dados são as seguintes:

- ID da linha: identificação única para cada linha.
- ID do pedido: identificação única do pedido para cada cliente.
- Data do pedido: data do pedido do produto.
- Data de envio: data de envio do produto.
- Modo de envio: modo de envio especificado pelo cliente.
- ID do cliente: identificação única para cada cliente.
- Nome do cliente: nome do cliente.
- Segmento: segmento ao qual o cliente pertence.
- Cidade: cidade de residência do cliente.
- Estado: estado de residência do cliente.
- País: país de residência do cliente.
- Região: região à qual o cliente pertence.
- ID do produto: identificação única do produto.
- Categoria: categoria do produto encomendado.
- Subcategoria: subcategoria do produto encomendado.
- Nome do produto: nome do produto.
- Vendas: valor total pago pelo cliente para compra do produto.
- Quantidade: quantidade do produto.
- Desconto: desconto fornecido.
- Lucro: lucro/prejuízo incorrido.

## 3 — Pré-processamento de Dados

A etapa de pré-processamento tem como objetivo deixar os dados prontos para análise. Alguns dos objetivos mais comuns incluem, verificar se existem erros e inconsistências nos dados, o que poderia alterar os resultados da análise, e, então, corrigi-los ou removê-los.

Para auxiliar na análise de lucratividade, criarei uma nova coluna que representará a margem de lucro bruta da compra. A margem de lucro bruta é uma medida que indica a eficiência da empresa em gerar lucro com suas vendas, sendo calculada pela divisão do lucro pela receita da venda.

Dado que o conjunto de dados original está em italiano, traduzirei o nome das colunas para português e alguns dos valores das principais colunas.

Conclusões depois de realizada a etapa de pré-processamento:

- Uma nova coluna para a “Margem de Lucro Bruta” foi criada.
- Os nomes das colunas foram traduzidos para português.
- Os valores de algumas colunas foram traduzidos para português.
- Os tipos de dados foram atribuídos corretamente.
- Foi verificado a ausência de valores nulos e duplicados.
- A distribuição dos dados está aparentemente normal.
- Os dados estão corretamente formatados.

Até o momento, não identifiquei nenhum problema importante nos dados. As poucas modificações realizadas tiveram como objetivo facilitar a análise, conforme especificado acima. Portanto, podemos prosseguir com a exploração dos dados.

## 4 — Análise Exploratória de Dados

### 4.1 — Análise de Lucratividade

#### 4.1.1 — Lucratividade ao Longo do Tempo

Pergunta: como a lucratividade mudou ao longo do tempo? Existem padrões e tendências?

IMAGEM1

A lucratividade do hipermercado apresenta uma trajetória de crescimento nos últimos 4 anos, atingindo seu maior pico no final do 2° trimestre de 2023, com aproximadamente 40.000 euros de lucro.

Observa-se uma forte tendência de crescimento nos primeiros e segundos trimestres de cada ano, enquanto nos terceiros e quartos trimestres a lucratividade tende a ser mais instável e a diminuir.

#### 4.1.2 — Lucratividade por Segmento de Clientes

Pergunta: quais os segmentos de clientes são mais e menos lucrativos?

IMAGEM2

O segmento de clientes privados destaca-se como o mais lucrativo, seguido pelo segmento das grandes empresas e, por fim, o segmento das pequenas empresas.

Considerando os segmentos de produtos que estamos estudando, ou seja, material de escritório, móveis e tecnologia, poderíamos sugerir aos gestores para que numa próxima análise, seja realizada a investigação das razões que levam que o segmento de pequenas empresas fique tão atrás dos outros. Dependendo do motivo, a empresa poderia ajustar sua estratégia para atingir um desempenho melhor com as pequenas empresas.

#### 4.1.3 — Lucratividade por Região, País e Estados

Pergunta: quais regiões, países e estados são mais e menos lucrativos?

IMAGEM3

As diferenças na lucratividade entre as regiões são grandes, destaca-se a região central da Europa, cujo desempenho dos últimos 4 anos supera a soma das regiões norte e sul.

IMAGEM4

Podemos notar que, especialmente no Reino Unido, França, Alemanha e Espanha, a empresa apresenta um excelente desempenho, com altos lucros quando comparados com os demais países. Enquanto na Dinamarca, Irlanda, Portugal, Suécia e Países Baixos a empresa apresenta prejuízos. A situação nos Países Baixos com um prejuízo de aproximadamente 40.000 euros parece ser particularmente preocupante, investigaremos mais a seguir os possíveis motivos dessa situação.

IMAGEM5

Ao representar os dados graficamente em um mapa, podemos facilmente observar o desempenho da empresa de acordo com sua localização geográfica.

O primeiro mapa representa o lucro total obtido por cada país, cada variação de cor representa um intervalo de lucro ou prejuízo de 25.000 euros. O segundo mapa representa a média da margem de lucro ou prejuízo por estado, em que cada variação de cor representa um intervalo de margem de lucro ou prejuízo de 10%.

Com o auxílio de ambos os mapas, facilmente identificamos que os problemas do prejuízo estão principalmente concentrados em países específicos, uma vez que a mesma tendência negativa é observada fortemente nos seus respectivos estados.

O segundo mapa revela que a situação é mais grave do que inicialmente parecia, indicando margens de lucro médias extremamente baixas em alguns países e estados.

IMAGEM6

Colocando esses dados em perspectiva, torna-se evidente que o problema do prejuízo é motivado pela baixa margem de lucro.

As margens de lucro nesses países deficitários variam aproximadamente de menos 55% a menos 45%. Agora, que descobrimos o motivo do prejuízo, buscaremos as causas que levam as margens de lucro a estarem tão baixas. Com base nas informações disponíveis, podemos supor que a estratégia de preços ou a política de descontos podem ser responsáveis pelo problema, uma vez que as margens atuais não cobrem os gastos da empresa.

IMAGEM7

Este gráfico apresenta a razão pela qual os Países Baixos estão causando grandes prejuízos a empresa. Com margens de lucro negativas e um volume de vendas mais elevado em comparação aos outros países deficitários, os Países Baixos representam uma fonte considerável de perdas.

Dado que a grande maioria das vendas da empresa são realizadas em países com boas margens de lucro, o impacto financeiro desses prejuízos não tem afetado muito a lucratividade geral da empresa. Podemos levantar algumas hipóteses sobre a situação:

1. O pequeno volume de vendas nesses países e estados pode ter escondido o problema para a equipe do hipermercado.
2. O hipermercado pode ter decidido manter a operação nesses países e estados, mesmo com prejuízo, por razões estratégicas.

Para desenvolver essas hipóteses, seria necessário entrar em contato com os responsáveis de determinados setores, apresentando este relatório detalhado dos resultados atuais. Continuaremos a explorar este problema mais abaixo.

#### 4.1.4 — Lucratividade por Categoria de Produto

Pergunta: quais categorias de produtos são mais e menos lucrativas?

IMAGEM8

#### 4.1.5 — Lucratividade por Subcategoria de Produto

Pergunta: quais são as subcategorias de produtos mais e menos lucrativas?

IMAGEM9

A análise agregada das subcategorias mostra que a grande maioria contribui positivamente para o lucro do hipermercado, com exceção da subcategoria “Mesas” que gerou um prejuízo de 20.000 euros nos últimos 4 anos. Para compreender o motivo desse desempenho negativo persistente, investigaremos mais afundo as informações que possuímos sobre a subcategoria.

Pergunta: desde quando e por que a subcategoria de produtos "Mesas" está causando prejuízo?

IMAGEM10

A subcategoria de produtos "Mesas" está causando prejuízo para a empresa desde antes de 2020, com oscilações persistentes, vem mantendo-se consistentemente negativa na maior parte do tempo.

IMAGEM11

IMAGEM12

A causa pela qual a subcategoria “Mesas” está gerando prejuízo é devido ao fato de que a maioria dos produtos vendidos nessa subcategoria tem sido comercializado com altos descontos.

Com o auxílio do gráfico de dispersão, do histograma, da correlação de Pearson e do valor-p, podemos concluir com certeza que esses prejuízos estão fortemente correlacionados aos altos níveis de desconto e não a estratégia de precificação, pois todos os produtos vendidos sem desconto geraram lucro. A correlação de Pearson entre as variáveis "desconto" e "lucro" é de −0,70, com um valor-p menor que 0,001.

A correlação de Pearson tem como objetivo medir a força e a direção do relacionamento entre variáveis. O valor de −0,70 indica uma forte correlação negativa entre as variáveis "desconto" e "lucro". Isso significa que, à medida que o desconto aumenta, o lucro tende a diminuir bastante. O valor-p menor que 0,001 mostra que a correlação é estatisticamente significativa, ou seja, não é devido ao acaso, e sim, a uma relação real entre as variáveis.

Essas observações me levam a perguntar se não seria a estratégia de descontos da empresa o principal motivo dos prejuízos não apenas da subcategoria “Mesas”, mas, também, no prejuízo geral da empresa, colaborando com a análise anterior que apontava a média de margem de lucro como um problema em determinados países e estados.

#### 4.1.6 — Lucratividade por Produto

Pergunta: quais produtos são mais e menos lucrativos?

Nas categorias que temos disponíveis para análise, o catálogo do hipermercado possui 1856 produtos. Dada a grande quantidade de produtos e sendo o foco desta análise os aspectos principais da lucratividade do negócio, iniciaremos a investigação visualizando os 10 produtos mais lucrativos e os 10 produtos que geram maior prejuízo.

IMAGEM13

IMAGEM14

Observa-se que existem vários produtos que estão gerando bastante impacto negativo nos resultados da empresa.

IMAGEM15

As informações apresentadas nos gráficos acima são extremamente importantes para empresa. Ao somar o desempenho de cada produto nos últimos 4 anos, constatamos que existe um conjunto de produtos que vem consistentemente gerando prejuízo ao hipermercado.

O hipermercado oferta 1856 produtos nas categorias em nosso estudo, sendo que 1444 estão gerando lucro, enquanto 412 estão causando prejuízo, ou seja, 77,8% são geradores de lucro, enquanto 22,2% são produtos deficitários.

IMAGEM16

Somando o prejuízo desses produtos deficitários ao longo dos últimos 4 anos, o valor total dos prejuízos atingi o alto valor de 109 mil euros. São 109 mil euros de perda que, possivelmente, poderiam ter sido evitados.

Identificar esses produtos o mais rápidos possível é crucial para o bom desempenho do hipermercado. Caso análises de desempenho fossem realizadas com mais frequência, possivelmente esses problemas poderiam ter sido identificados e resolvidos antes que os prejuízos se acumulassem. Dependendo da situação, uma solução simples e eficaz poderia ser a retirada desses produtos do catálogo ou a revisão das estratégias da empresa de preços e descontos.

A situação dos produtos deficitários parece ser preocupante. Ter prejuízo em algumas vendas é normal, especialmente por questões estratégicas, como temporariamente diminuir os preços de um produto ou de alguns produtos para atrair mais clientes que, ao comprarem esses produtos, também adquirem outros, gerando lucro e fortalecendo a reputação da empresa. No entanto, ter 22,2% dos produtos consistentemente causando prejuízo não parece ser uma questão de estratégia, mas sim um possível erro interno de precificação de produtos ou de concessão de descontos.

Na próxima etapa, investigaremos o impacto dos descontos nos lucros da empresa para confirmar se a hipótese de que a estratégia de descontos que tem causado prejuízo na subcategoria de produtos “Mesas” é a razão por trás dos prejuízos gerais da empresa e de seus produtos.

#### 4.1.7 —  Análise do Impacto da Estratégia de Descontos no Lucro

Pergunta: até que ponto os descontos estão afetando o lucro da empresa?

Anteriormente, buscando compreender as razões por trás dos prejuízos que estavam afetando o lucro geral da empresa, sugeri duas hipóteses iniciais, um problema na estratégia de preços ou um problema na estratégia de descontos. A fim de concluir a análise, veremos o impacto da estratégia atual de desconto na empresa.

IMAGEM17

IMAGEM18

Para a criação do gráfico de distribuição, optei por retirar os valores extremos dos dados com desconto e sem desconto, isso foi feito para evitar que os valores extremos distorcessem a visualização dos dados.

Realizando a análise anteriormente conduzida na subcategoria de produtos “Mesas”, observamos a mesma tendência de correlação negativa entre as variáveis “desconto” e “lucro” nos produtos deficitários. Ambas observações colaboram para a conclusão que o problema não reside na precificação original dos produtos, já que todos os produtos vendidos sem desconto geraram lucro para a empresa. Assim, podemos inferir que o preço original dos produtos está correto, sendo a estratégia de descontos a razão do prejuízo.

Vamos agora verificar o quanto a estratégia de descontos afeta todas as vendas da empresa.

IMAGEM19

IMAGEM20

IMAGEM 21

Novamente, vemos que o problema não está na precificação original dos produtos, mas sim na estratégia de descontos da empresa. Apesar do o grave problema dos descontos estar nos produtos deficitários, a estratégia de descontos também está impactando negativamente a lucratividade geral da empresa.

IMAGEM22

Ao mapear os dados de maneira geográfica, a visualização de nossa conclusão fica ainda mais clara.

No primeiro mapa, observa-se que os países deficitários apresentam uma média de desconto de aproximadamente 50%. Conforme analisado anteriormente, esse problema somente não está causando muitos prejuízos, pois as vendas dos segmentos em estudo nesses países são relativamente baixas.

## Conclusão

Através deste estudo, conduzi uma análise exploratória nos dados das categorias de material de escritório, móveis e tecnologia vendidas por um hipermercado, com o objetivo de avaliar quais eram as variáveis que mais estavam afetando a lucratividade do negócio. Segue um pequeno resumo com as principais conclusões:

#### 1. Lucratividade por Região, País e Estados:

- Identificamos que os países da Dinamarca, Irlanda, Portugal, Suécia e, em especial, os Países Baixos, estão acarretando consistentes prejuízos para a empresa.

#### 2. Lucratividade por Subcategoria e por Produtos:

- Identificamos uma subcategoria de produtos e uma grande lista de produtos deficitários, que estão consistentemente gerando prejuízo para empresa.
- A subcategoria “Mesas” causou aproximadamente 20 mil euros de prejuízo nos últimos 4 anos.
- Os produtos que identificamos como deficitários causaram uma perda de 109 mil euros de prejuízo no últimos 4 anos.

#### 3. Análise do Impacto da Estratégia de Descontos no Lucro:

- Depois de identificar em várias áreas da empresa problemas com a estratégia de descontos, foi realizado um estudo mais aprofundado para confirmar se essa era a verdadeira causa dos problemas e qual era o impacto real disso.

#### 4. Recomendações e Conclusões:

- Foi identificado de forma precisa as causas que levam os países, a subcategoria “Mesas” e os produtos deficitários a causar grande prejuízo para empresa, além disso, ofereci ao longo do relatório soluções e recomendações para a solução dos problemas.
- Destaco que a identificação precoce de produtos que estão acarretando perdas para empresa é de extrema importância, se o problema dos produtos deficitários fosse identificado mais cedo poderia ter sido resolvido e a empresa poderia ter deixado de perder dezenas de milhares de euros.
- A causa geral dos problemas se deve a estratégia de desconto, essa deve ser revisado por completo e de forma detalha para evitar ainda mais perdas futuras.
- Foram mencionados durante o relatório recomendação de possíveis estudos futuros.

Este relatório não visou apenas descrever e diagnosticar a lucratividade da empresa, mas também apontar as formas que estes problemas poderiam ser resolvidos. Adotando medidas corretivas fundamentadas nessas conclusões, a empresa poderá alinhar suas estratégias de maneira mais eficaz, impulsionando sua lucratividade e fortalecendo sua posição competitiva no mercado.