# Excel-American_non_voters
Olá pessoal! Segue a minha resolução para o case proposto pelo Andre Yukio da Universidade dos Dados! 

O título do desafio é "O que é considerado "ser americano" para o eleitor dos EUA?", e consiste em responder algumas perguntas de negócio com base em um dataset feito pela Ipsos da FiveThirtyEight.  O dataset "Nonvoters" apresenta dados provenientes de pesquisas conduzidas pela Ipsos, utilizando o KnowledgePanel da Ipsos e uma amostra online baseada em probabilidade para ser representativa de toda a população dos EUA. 

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

![Faixa salarial x raça](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte1/8_faixa_salarial_rac%CC%A7a.png)

Para aprofundar mais a análise, o gráfico abaixo foi gerado destacando a raça no eixo X, permitindo analisar a faixa salarial por raça mais facilmente. Podemos observar que a maioria dos que se declararam negros na pesquisa possui uma faixa salarial menor que $40k anuais, 35,84% mais especificamente. Apenas 13,63% dos entrevistados negros tem uma faixa salarial acima dos $125k anuais.

A maioria dos que se declararam hispânicos possui uma renda anual de até $125k (80,57%), a maioria com faixa salarial entre $75k e $125k (28,41%). Os que declararam sua raça como Other/Mixed tem em sua maioria pessoas que ganham $125k ou mais de salário anual (33,07%), com quase 60% dessas pessoas ganhando a partir de $75k por ano.

A maioria dos que se declararam brancos ganham na faixa de $75-$125k por ano (28,84%), e 21,13% ganham menos que $40k anuais.

![Raça x Faixa salarial](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte1/7_rac%CC%A7a_faixa_salarial.png)

**Ainda assumindo que temos uma amostra representativa, podemos dizer que nível educacional e poder aquisitivo estão correlacionados?**

Observamos que existe sim uma correlação entre o nível educacional e o poder aquisivo, pois a maioria das pessoas que ganham mais de $125k por ano possuem ensino superior completo, quase 41%. Em contrapartida, a maioria das pessoas que tem até o ensino médio completo, 43,54%, ganham menos que $40k por ano. Além disso, podemos observar que as maiores faixas salariais são da população que concluiu o ensino médio, e a maioria das menores faixas salariais são da população que concluiu até o ensino médio.

![Nível educacional x salário](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte1/9_nivel_educacional_salario.png)

## Parte 2 - O que é considerado ser um bom americano?

**Um nível educacional maior implica em maior responsabilidade em relação a votar?**

Foi questionado aos participantes sobre a importância de uma série de itens para ser considerado um bom americano. Dentre os itens, um deles se refere a o quão importante é votar nas eleições. A classificação da importância se deu em uma escala de 1 a 4, onde 1 é "muito importante", 2 é "importante", 3 é "não tão importante" e 4 é "não é importante". O -1 no gráfico refere-se a quem não quis ou não soube responder. 

Analisando os resultados dessa pergunta em relação ao nível educacional, 81,52% dos entrevistados acredita que votar nas eleições é muito importante, independente do nível de escolaridade. Levando em consideração o nível de escolaridade, a maioria pertence ao grupo de pessoas que tem o ensino superior completo (43%). Já para o grupo de pessoas que consideram que votar não é importante, a maioria é de pessoas que tem até o ensino médio completo (58,75%).

![Nível educacional x Importância do voto](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte2/3_nivel_educ_importancia_voto.png)

**Dentre os não-brancos, o que é mais importante para ser um bom americano: votar em eleições, demonstrar a bandeira americana ou apoiar o exército?**

Para a maioria das pessoas negras, hispânicas e outras, votar nas eleições é muito importante. Para quase 82% das pessoas que se consideram negras, quase 80% dos hispânicos e 78% dos que se consideram de outras raças, votar é sim, um ato muito importante.

![Importância do voto para não-brancos](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte2/4_importancia_voto.png)

Para a maioria das pessoas negras, demonstrar a bandeira americana é um ato que não é tão importante. Cerca de 52% consideraram esse ato não tão importante ou até mesmo não importante. Ao contrário das pessoas negras, a maioria dos hispânicos considera mostrar a bandeira americana um ato importante. Cerca de 64% consideram esse ato muito importante ou importante. Por fim, a maioria das pessoas que se consideram de outras raças acredita que mostrar a bandeira é um ato não tão importante (aproximadamente 30%).

![Mostrar a bandeira dos EUA](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte2/5_mostrar_bandeira.png)

Para a maioria dos entrevistados não-brancos, apoiar o exército é um ato muito importante (57,38%). Para pouco mais de 59% das pessoas que se consideram negras, 59% dos hispânicos e 49% dos que se consideram de outras raças, apoiar o exército é sim, um ato muito importante.

![Apoiar o exército](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte2/6_apoio_exercito.png)

Considerando somente as respostas "Muito Importante", a preferência predominante é o ato de votar em eleições, seguido pelo apoio aos militares, e por fim, mostrar a bandeira dos EUA.

![Preferência da população](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte2/9_pref_pop_grafico.png)

**Existe uma diferença na preferência de não-brancos de maior poder aquisitivo vs menor poder aquisitivo?**

Para responder essa pergunta, além da tabela e gráficos dinâmicos, utilizei a Segmentação de dados do Excel para filtrar os resultados de acordo com a faixa salarial dos entrevistados. Considerando maior poder aquisitivo igual a faixa de salário $125k e o menor poder aquisitivo a faixa de salário menor que $40k, temos o seguinte resultado.

*Maior poder aquisitivo*

![Maior poder aquisitivo](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte2/10_maior_poder_aquisitivo.png)

Considerando um poder aquisitivo maior e uma maior importância do voto, os hispânicos são a maioria. Em relação a variável mostrar a bandeira, a maioria das pessoas com maior poder aquisitivo consideram esse ato não tão importante. Por fim, a maioria das pessoas não-brancas com alto poder aquisitivo consideram apoiar o exército uma prática muito importante.

*Menor poder aquisitivo*

![Menor poder aquisitivo](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte2/11_menor_poder_aquisitivo.png)

Considerando um poder aquisitivo menor e uma maior importância do voto, os negros são a maioria. Em relação a variável mostrar a bandeira, o mesmo número de pessoas consideram esse ato importante ou não tão importante, com destaque para a maioria dos hispânicos considerando esse ato muito importante e a maioria dos negros considerando esse ato importante. Por fim, a maioria das pessoas não-brancas com baixo poder aquisitivo consideram apoiar o exército uma prática muito importante.

Considerando ambos os gráficos, podemos notar que o poder aquisitivo influencia mais na importância ou não em mostrar a bandeira dos EUA e menos em relação a importância do voto e o apoio ao exército.

**Considerando que respeitar a opinião dos outros (Q2_8) é um indício de tolerância, ao compararmos as gerações de 18-30 anos, 31-50 anos e +51, qual é a mais tolerante e a menos tolerante?**

Para criar as faixas etárias sugeridas pelo enunciado do exercício, utilizei a função SE do Excel. O resultado pode ser visto na figura abaixo:

![Função SE](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte2/12_exemplo_func%CC%A7a%CC%83o_se.png)

Com as faixas etárias criadas, mais uma vez utilizei uma tabela dinâmica para criar um gráfico de barras para visualizar os resultados. A pergunta feita aos entrevistados estava relacionada ao quanto é considerado importante ou não respeitar as opiniões de quem discorda da sua opinião. Assim como nas outras variáveis, a classificação da importância se deu em uma escala de 1 a 4, onde 1 é "muito importante", 2 é "importante", 3 é "não tão importante" e 4 é "não é importante". O -1 no gráfico refere-se a quem não quis ou não soube responder. O resultado pode ser visto no gráfico abaixo:

![Nível de tolerância](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte2/13_nivel_tolerancia.png)

Podemos concluir que a maioria das pessoas de todas as faixas etárias consideram muito importante respeitar opiniões contrárias. Porém, a faixa de idade que considera mais importante respeitar as opiniões contrárias é a de 51 anos ou mais. Quase 59% das pessoas que consideram muito importante respeitar opiniões contrárias estão nessa faixa etária. Podemos então, considerar essa faixa etária como a mais tolerante. Em contrapartida, a maioria das pessoas que consideram não ser importante respeitar opiniões contrárias também pertencem a faixa etária dos 51 anos ou mais, correspondente a 42% das pessoas que escolheram a opção 4.

## Parte 3 - Escolhas partidárias

**Qual escolha partidária, incluindo pessoas sem partido (Q30), possui eleitores mais jovens? E qual possui mais mulheres como apoiadoras?**

Para responder essa pergunta, utilizei as mesmas faixas etárias da pergunta anterior. A pergunta feita para os entrevistados foi sobre qual a sua orientação política. As respostas foram enumeradas de 1 a 5, sendo 1 = republicano, 2 = democrata, 3 = independente, 4 = outros, 5 = sem preferência. O -1 refere-se aos que não souberam ou não quiseram responder.

Na faixa dos eleitores mais jovens, ou seja, eleitores entre 18 e 30 anos de idade, a maioria prefere o partido democrata (36,29%), seguido pelos que preferem partidos independentes (quase 26%) e pelos republicanos (18,50%). Destaca-se também os quase 16% dos entrevistados que não tem preferência por um partido.

![Partido x faixa etária](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte3/0_escolha_partidaria_18-30.png)

Em relação as mulheres, a maioria (37,5%) apoiam o partido democrata, seguido pelo partido republicano (quase 28%) e as que apóiam partidos independentes (quase 20%). Destaca-se também os 13% de mulheres entrevistadas que não tem preferência partidária.

![Mulheres x partido](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte3/2_apoio_mulheres.png)

**Qual o perfil do público sem partido (independent ou no preference), em termos de idade e gênero? E dos republicanos? E dos democratas?**

Para responder essas perguntas, deixei as pessoas que não souberam ou não quiseram responder de fora. Além disso, utilizei as faixas etárias definidas anteriormente. Foi questionado para as pessoas que apóiam partidos independentes, outros, ou que não tem preferência, se a pessoa se considera mais como republicano (1) ou democrata (2). Em termos de idade, em todas as faixas etárias, as pessoas se consideram mais democratas do que republicanas. A maior diferença é observada na faixa dos 18-30 anos. Quase 62% desse público se considera democrata. Na faixa dos 51+, a diferença entre democratas e republicanos é de apenas uma pessoa.

![Idade x público sem partido](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte3/3_sem_partido_idade1.png)

Em termos de gênero, a maioria de homens e mulheres se consideram mais democratas do que republicanos. A diferença entre os homens é menor (51% a 49% a favor dos democratas) em relação às mulheres (57% a 43% a favor dos democratas).

![Gênero x público sem partido](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte3/4_sem_partido_genero1.png)

O perfil dos eleitores republicanos foi gerado a partir da pergunta Q31, que considerou os entrevistados que são republicanos como mais (1) ou menos (2) adeptos as idéias do partido. Também retiramos da análise aqueles que não souberam ou não quiseram responder. Em termos de idade, a maioria dos republicanos possuem 51 anos ou mais (63,40%), e em relação ao gênero, quase 51% são mulheres.

![Republicanos x idade](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte3/5_republicanos_idade1.png)
![Republicanos x gênero](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte3/6_republicanos_genero2.png)

O perfil dos eleitores democratas foi gerado a partir da pergunta Q32, que considerou os entrevistados que são republicanos como mais (1) ou menos (2) adeptos as idéias do partido. Também retiramos da análise aqueles que não souberam ou não quiseram responder. Em termos de idade, a maioria dos democratas possuem 51 anos ou mais (57%), e em relação ao gênero, 54% são mulheres.

![Democratas x idade](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte3/7_democratas_idade1.png)
![Democratas x gênero](https://github.com/guibusanello/Excel-American_non_voters/blob/main/assets/parte3/8_democratas_genero1.png)

**Existe uma correlação entre idade e propensão a votos (voter_category)?**

