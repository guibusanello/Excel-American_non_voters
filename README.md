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

1) Qual o perfil da amostra analisada? Verifique a distribuição de idade, gênero, raça, nível educacional e salarial.

A média de idade da população que respondeu a pesquisa é de 51,69 anos, e a maioria das pessoas que respondeu a pesquisa está na faixa dos 59 aos 67 anos, seguido pelas pessoas entre 22 e 31 e 49 e 58 anos respectivamente. Essas informações podem ser vistas no Box Plot e no Histograma abaixo:




