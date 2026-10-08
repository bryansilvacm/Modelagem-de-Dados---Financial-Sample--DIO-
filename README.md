# Modelagem de Dados - Financial Sample (DIO)
Desafio de Projeto do Bootcamp da DIO de análise e modelagem de dados com Power BI.

## Descrição do Desafio de Projeto
Utilizaremos a tabela única de Financial Sample para criar as tabelas dimensão e fato do nosso modelo baseado em Star Schema.  
O processo consiste na criação das tabelas com base na tabela original. A partir da cópia, serão selecionadas as colunas que irão compor a visão da nova tabela.  

## Objetivos
Desenvolver habilidades de modelagem de dados colocando em prática a modelagem em Star Schema, a fim de aprimorar e memorizar os conteúdos aprendidos em aula.

## Introdução
Star Schema é um método de modelagem de dados estruturado para uma melhor visualização dos dados de acordo com um contexto desejado. Sua estrutura contém uma Tabela Fato, a qual representa cada evento ou fato que ocorreu. Como um complemento à tabela fato, existem as tabelas Dimensão, que por sua vez são as tabelas que darão mais contexto aos fatos, contendo detalhes e informações dos eventos. Elas representam o que, como e quando ocorreu, são menores e as instâncias não se repetem.

## Desenvolvimento
A partir da amostra de dados de vendas disponibilizada pela instrutora, iniciou-se o processo de criação de cada tabela Dimensão e da tabela Fato. As tabelas geradas foram:

* **d_Produto:** Gerada utilizando a função de agregação para somar a quantidade de vendas por produto e adquirir as medidas de mínimo, máximo, média e mediana do valor de venda. Também foi criada a coluna de ID do produto utilizando a função de coluna índice.
* **d_Descontos:** Duplicação da tabela original, limpando e excluindo as colunas inválidas, a fim de deixar somente informações mais interessantes sobre os descontos, como ID_produto, Discount e Discount Band. Criamos também o ID_Produto utilizando a ferramenta de coluna condicional de acordo com os parâmetros da tabela produto.
* **d_Produto_Detalhes:** Também gerada a partir de uma lapidação da tabela original, a fim de conter detalhes como vendas e preço unitário em relação a cada produto.
* **d_Detalhes:** Contém todas as informações de todas as instâncias de vendas.  
* **d_Calendário:** Criada por DAX com `CALENDAR()`, possibilitando análises mais detalhadas, como o somatório de vendas dia a dia, entre outras possibilidades.  
* **f_Vendas:** A tabela Fato criada para ser o alvo da análise, contendo as informações principais das vendas (SK_ID, ID_Produto, Produto, Units Sold, Sales Price, Discount Band, Segment, Country, Sellers, Profit, Date).

---

Após todas as criações e transformações de cada tabela, foi feita a criação de cada relacionamento, buscando conectar cada tabela dimensão à tabela fato por meio dos IDs e índices.

## Representação do Schema Gerado
<img width="1057" height="741" alt="image" src="https://github.com/user-attachments/assets/8164b801-aec0-4063-aa21-760e14c611df" />

## Conclusão
Com base nos objetivos propostos, a introduçã e o desenvolvimento prático apresentados, concluí-se que a aplicação bem-sucedida do modelo *Star Schema* permitiu transformar dados brutos e planos em uma estrutura dimensional organizada e eficiente, praticando conceitos de ETL e Modelagem. Esse processo consolidou os conhecimentos em modelagem de dados e Power BI, garantindo melhor desempenho nas consultas, clareza nas relações e uma base sólida para a geração de insights analíticos precisos.

---

Tecnologias Utilizadas:


- Power BI   <img width="20" height="20" align="absmiddle" alt="Power BI" src="https://github.com/user-attachments/assets/b5e8ba59-496e-426f-858c-1f4c1e9616cc" />
<br>

- Power Query   <img width="20" height="20" align="absmiddle" alt="Power Query" src="https://github.com/user-attachments/assets/3a4e133e-d247-42d9-b014-31dafa6bf1f4" />
<br>

- Excel   <img width="20" height="20" align="absmiddle" alt="Excel" src="https://github.com/user-attachments/assets/9a9698a3-8806-4481-a044-9651e34dce88" />
<br>

- DAX   <img width="40" height="20" align="absmiddle" alt="DAX" src="https://github.com/user-attachments/assets/1bb98e4d-10a5-48b6-96d3-abb9bb4b7142" />
