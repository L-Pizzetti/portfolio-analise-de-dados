# Portfólio de Análise de Dados.

Este repositório reúne projetos voltados à análise de dados, abordando desde a exploração e tratamento até a interpretação dos resultados. O foco está na aplicação de técnicas estatísticas e computacionais para extrair informações relevantes e embasar a tomada de decisão em diferentes contextos.

## Projetos.

Abaixo está uma lista de projetos contendo descrições detalhadas, links para o código e relatórios completos.

| Projeto                                     | Descrição                                                                                                                                                                                  | Tecnologias                                                                  | Código                          | Relatório                      |
| ------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------- | ------------------------------- | ------------------------------ |
| Análise Exploratória - Hipermercado Europeu | Estudo de 10.000 transações comerciais (2020-2023) em países da União Europeia, identificando padrões de lucratividade, prejuízos de 109 mil euros e falhas na estratégia de descontos. | Python, Pandas, NumPy, Matplotlib, Seaborn, SciPy, Tableau, Jupyter Notebook | [analise\_hipermecado.ipynb](https://github.com/leonardopizzetti/portfolio-analise-de-dados/blob/main/An%C3%A1lise%20Explorat%C3%B3ria%20de%20Dados%20-%20Hipermercado%20Europeu/notebook.ipynb) | [relatorio\_hipermecado.md](https://github.com/leonardopizzetti/portfolio-analise-de-dados/blob/main/An%C3%A1lise%20Explorat%C3%B3ria%20de%20Dados%20-%20Hipermercado%20Europeu/relatorio.md) |

## Detalhes dos projetos.

### Análise exploratória de dados: estudo de desempenho de hipermercado no varejo europeu.

- **Objetivo**: avaliar os fatores que impactam a lucratividade do hipermercado por meio de análise exploratória.
- **Escopo**: análise de 10.000 vendas de produtos (escritório, móveis e tecnologia) realizadas em países da União Europeia entre 2020 e 2023.
- **Metodologia**:
  - **Pré-processamento de dados**: tradução do italiano para o português, criação da métrica de margem de lucro bruta, verificação de valores ausentes, duplicados e dos tipos de dados.
  - **Análise estatística e exploratório**: avaliação da lucratividade ao longo do tempo, cálculo da correlação de Pearson entre variáveis, segmentação por clientes, regiões e categorias de produtos.
  - **Visualização de dados**: uso de gráficos temporais, mapas geográficos, gráficos de dispersão entre descontos e lucro e histogramas da distribuição das margens por categoria.
  - **Principais descobertas**: identificação de 412 produtos deficitários (perda acumulada de 109 mil euros) e comprovação da relação inversa entre descontos elevados e lucratividade.
- **Arquivos**:
  - **`analise_hipermecado.ipynb`**: código em Python contendo as etapas de limpeza de dados, análises estatísticas e visualizações.
  - **`relatorio_hipermecado.md`**: documento com um relatório completo, gráficos e recomendações estratégicas voltadas para gestores e tomadores de decisão.
- **Conclusões**:
  - Os descontos aplicados atualmente reduzem a rentabilidade do negócio.
  - Dinamarca, Irlanda, Portugal, Suécia e Países Baixos apresentam margens negativas entre 45% e 55%.
  - A subcategoria "Mesas" gerou um prejuízo acumulado de aproximadamente 20 mil euros ao longo de quatro anos.
  - Sugere-se a reformulação da política de descontos e um monitoramento frequente dos produtos deficitários.

## Como utilizar este repositório.

1. Consulte a tabela de projetos acima para encontrar uma análise de interesse.
2. Acesse o código no Jupyter Notebook para detalhes técnicos ou visualize o relatório em Markdown para uma análise voltada à tomada de decisão.
3. Para sugestões ou colaborações, sinta-se à vontade para abrir uma *issue* ou entrar em contato!

## Contato.

- **LinkedIn**: [www.linkedin.com/in/leonardopizzetti](www.linkedin.com/in/leonardopizzetti)

Agradeço por sua visita! Feedbacks são sempre bem-vindos.
