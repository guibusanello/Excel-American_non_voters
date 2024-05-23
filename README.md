# Excel-American_non_voters
Olá pessoal! Segue a minha resolução para o case proposto pelo Andre Yukio da Universidade dos Dados! 

O título do desafio é "O que é considerado "ser americano" para o eleitor dos EUA?", e consiste em responder algumas perguntas de negócio com base em um dataset feito pela Ipsos for FiveThirtyEight.  O dataset "Nonvoters" do FiveThirtyEight apresenta dados provenientes de pesquisas conduzidas pela Ipsos, utilizando o KnowledgePanel da Ipsos, uma amostra online baseada em probabilidade recrutada para ser representativa da população dos EUA. 

A pesquisa foi realizada de 15 a 25 de setembro entre uma amostra de cidadãos americanos, com oversampling de respondentes jovens, negros e hispânicos, totalizando 8.327 entrevistados, sendo uma parte descartada por não corresponder aos critérios específicos. O dataset inclui 5.239 indivíduos que responderam e se emparelharam com o arquivo eleitoral e 597 indivíduos que responderam que não se emparelharam, mas se descreveram como votando "raramente" ou "nunca", todos elegíveis para pelo menos 4 eleições.

Para resolver esse desafio, utilizei o Microsoft Excel para tratar os dados e criar novas variáveis, mas principalmente, utilizei o recurso Tabela Dinâmica para criar as tabelas de frequência e os gráficos para a análise e geração dos insights.

Link do repositório: https://github.com/fivethirtyeight/data/tree/master/non-voters

Link para a Universidade dos Dados: https://universidadedosdados.com/

## Entendimento das variáveis

O repositório conta com um documento em PDF explicando como a pesquisa foi conduzida, mostrando as perguntas realizadas e os números atribuídos a cada resposta. Apesar das respostas estarem no formato de número, podemos considerá-las como variáveis qualitativas, pois para cada resposta pré-determinada, foi atribuído um número. Perguntas como qual a raça, gênero, escolaridade, faixa salarial e frequência de voto também também são consideradas variáveis qualitativas, tendo somente uma variável quantitativa no dataset, que é a Idade.

## Parte 1 - Público da pesquisa

**Qual o perfil da amostra analisada? Verifique a distribuição de idade, gênero, raça, nível educacional e salarial.**

A média de idade da população que respondeu a pesquisa é de 51,69 anos, e a maioria das pessoas que respondeu a pesquisa está na faixa dos 59 aos 67 anos, seguido pelas pessoas entre 22 e 31 e 49 e 58 anos respectivamente. Essas informações podem ser vistas no Box Plot e no Histograma abaixo:

![Box Plot - Idade](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte1/1_box_plot_idade.png)
![Histograma - Idade](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte1/2_hist_idade.png)

Houve equilíbrio em relação ao gênero das pessoas entrevistadas. A maioria foram homens, com pouco mais de 50% dos entrevistados.

![Gênero](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte1/3_genero.png)

Pouco mais de 63% das pessoas entrevistadas se consideram brancas (White), seguidos por negros (Black), hispânicos (Hispanic) e outros.

![Raça](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte1/4_rac%CC%A7a.png)

Quase 40% dos entrevistados concluíram o ensino superior (College), seguidos pelos que concluíram até o ensino médio (High School or less) e para aqueles que ainda estão ou que não concluíram o ensino superior.

![Escolaridade](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte1/5_nivel_educacional.png)

A maioria dos entrevistados (27,90%) tem um salário anual entre $75k e $125k, e a minoria (23,89%) ganha na faixa de $125k+ anuais.

![Faixa salarial](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte1/6_faixa_salarial.png)

**Assumindo que a amostra representa adequadamente a população americana, qual a raça que possui maior poder aquisitivo? E menor?**

De acordo com os dados levantados na pesquisa, os que se declararam brancos (White) são os que tem maior e menor poder aquisitivo, conforme o gráfico abaixo. Esse fato pode ser justificado pela grande maioria dos entrevistados ser da raça branca (63,57%).

![Faixa salarial x raça](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte1/8_faixa_salarial_rac%CC%A7a.png))

Para aprofundar mais a análise, o gráfico abaixo foi gerado destacando a raça no eixo X, permitindo analisar a faixa salarial por raça mais facilmente. Podemos observar que a maioria dos que se declararam negros na pesquisa possui uma faixa salarial menor que $40k anuais, 35,84% mais especificamente. Apenas 13,63% dos entrevistados negros tem uma faixa salarial acima dos $125k anuais.

A maioria dos que se declararam hispânicos possui uma renda anual de até $125k (80,57%), a maioria com faixa salarial entre $75k e $125k (28,41%). Os que declararam sua raça como Other/Mixed tem em sua maioria pessoas que ganham $125k ou mais de salário anual (33,07%), com quase 60% dessas pessoas ganhando a partir de $75k por ano.

A maioria dos que se declararam brancos ganham na faixa de $75-$125k por ano (28,84%), e 21,13% ganham menos que $40k anuais.

![Raça x Faixa salarial](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte1/7_rac%CC%A7a_faixa_salarial.png)

**Ainda assumindo que temos uma amostra representativa, podemos dizer que nível educacional e poder aquisitivo estão correlacionados?**

Da mesma forma que na pergunta anterior, para responder essa questão foram gerados dois gráficos para compreender melhor essa correlação entre nível educacional e poder aquisitivo.









