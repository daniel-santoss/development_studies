<h2>MACHINE LEARNING:</h2> 
É um subgrupo dentro da Inteligência Artificial que foca no processamento e análise de dados por meio de algoritmos, com o objetivo de gerar informações úteis para fundamentar a tomada de decisão.<br>
PRÁTICA: Você tem um problema e uma decisão para ser tomada -> Você precisa de informações para tomar a melhor decisão -> Coleta e processa os dados por meio dos algoritmos em python -> Resumo das informações que sejam úteis para as tomadas de decisão.<br><br>

DEEP LEARNIG: É uma subárea do Machine Learning focado no aprendizado profundo com base em redes neurais. É uma técnica específica e mais potente, inspirada na estrutura e no funcionamento dos neurônios do cérebro humano para processar dados e criar padrões para a tomada de decisão.<br>
Sua principal vantagem é a capacidade de aprender características automaticamente a partir de dados brutos, sem a necessidade de intervenção humana manual para extrair os atributos.
É necessário milhões de exemplos para aprender os padrões sozinho sem "alucinar" ou decorar (overfitting).<br>

Em geral, o machine learning tem o objetivo de encontrar padrões nos dados, seja gerando modelos preditivos (modelos onde você consegue a partir daquela relação estabelecida fazer previsões com base nos seus resultados) ou análise exploratória para identificar padrões, relações latentes, ocultas nesses dados.

Data-driven decision making: Tomar decisões baseadas em análise de dados: Redução de incertezas, aumento de eficácia.


<h3>FLUXO DO MACHINE LEARNING:</h3>

1. Definição do problema:
 - Qual é o problema a ser resolvido?
 - Quais são os atributos envolvidos? Relacionar os dados.

2. Coleta dos dados:
 - Fontes: Dados históricos; dados atualizados em tempo real.
 - Provenientes de várias fontes ou já estão consolidados em local únicos.
 - É fundamental avaliar a qualidade dos dados.

3. Tratamento e preparação dos dados:
 - Junção de bases, limpeza, criação de variáveis, seleção de observações etc.
 
4. Aplicação de análises:
 - Escolha das técnicas e modelos mais adequados as características dos dados.
 - Análises exploratórias dos dados e modelos multivariados de machine learning.

5. Interpretação e tomada de decisão:
 - Como o resultado podem ser interpretados e colocados em prática.

 <h2>PONDERAÇÃO ARBITRÁRIA</h2>

 - Ocorre quando atribuímos "pesos" (importância) a determinadas variáveis ou entradas de forma manual, baseada apenas no nosso julgamento pessoal, intuição ou convenção, em vez de deixar que o modelo descubra esses valores através dos dados.
 - No Machine Learning, buscamos substituir a ponderação arbitrária pela ponderação otimizada, onde o algoritmo ajusta esses pesos matematicamente para encontrar a "lógica" mais precisa.

<h2>MODELOS SUPERVISIONADOS</h2>

O modelo é treinado usando um conjunto de dados que já contém a resposta correta. Nesse caso, fornecemos ao algoritmo pares de entrada(features) que são as características ou atributos do que você está analisando e as saída(target) que é o rótulo, a categoria ou o valor final que você quer que o modelo aprenda a prever.
- Mesmo quando o modelo acerta, ele precisa da confirmação da saída para saber que o caminho que ele seguiu internamente está correto e deve ser reforçado.
- Com base nos resultados, ele ajusta os parâmetros para tentar obter um resultado mais preciso.
- Se o modelo ajustar demais para corrigir até os mínimos detalhes  (0,0001), ele pode acabar decorando os dados de treino em vez de aprender a lógica gerada, resultando em grandes falhas nos resultados quando são apresentados novos dados.

<h4>FASES DO MOLELO SUPERVISIONADO:</h4>

1: Fase de treinamento:
- O modelo tem acesso aos pares (Entrada + Saída). Ele usa a saída para ajustar seus parâmetros internos. É aqui que ele "estuda" com o gabarito do lado.

2: Fase de Predição / Teste:

 - Nessa fase, ele não tem mais acesso à saída.
 - O modelo precisa "se virar" com o que aprendeu.
 - Ele gera uma resposta e é avaliado se ele está performando bem em dados que ele nunca viu antes.

 <h2>MODELOS NÃO SUPERVISIONADOS:</h3>

- O algoritmo recebe dados sem rótulos e sem respostas pré-definidas. O modelo deve explorar os dados e encontrar uma estrutura interna ou padrões ocultos por conta própria.
- O objetivo é modelar a estrutura ou distribuição subjacente dos dados para aprender mais sobre eles.
- O algoritmo agrupa os dados por semelhança ou reduz a complexidade deles sem saber previamente o que cada grupo representa

<h4>FASES DO MODELO NÃO SUPERVISIONADO</h4>

1: Fase de Treinamento (Descoberta):
- O modelo tem acesso apenas aos dados de Entrada.
- Ele não tem "gabarito". O objetivo é analisar as semelhanças matemáticas para criar grupos ou regras por conta própria.

2: Fase de Predição / Aplicação:

- O modelo recebe um dado novo e, com base na estrutura que ele descobriu, ele decide em qual grupo esse dado se encaixa melhor.
- A avaliação é feita pela coesão (se o dado realmente se parece com os outros do grupo).

<h4>Diferenças de aprendizado:</h4>

- Diferente do supervisionado, não há uma "resposta certa" (rótulo). O modelo melhora através da otimização matemática da estrutura dos dados.
O algoritmo busca o equilíbrio entre dois conceitos:
- Coesão (Inércia): Garante que os pontos dentro de um mesmo grupo estejam o mais próximos possível entre si.
- Separação: Garante que os diferentes grupos (clusters) estejam o mais distantes possível uns dos outros.
Como não sabemos quantos grupos existem nos dados, é utilizado uma técnica para encontrar o "número ideal":
- Método do Cotovelo (Elbow Method): Identifica o ponto onde adicionar mais grupos para de trazer ganhos significativos de precisão.
- Silhouette Score: Uma nota de -1 a 1 que mede o quão bem cada ponto se encaixa no seu grupo atual em relação aos vizinhos.

<h2>BANCO DE DADOS</h2>

O banco de dados no Machine Learning são organizados em duas dimensões:

1: Observações:
- Unidade de análise que você trás os dados com as características e atributos medidos.

2: Variáveis:
- Características/atributos observados, medidos e organizados.

A inserção do banco de dados no Python segue uma estrutura tabular, como em uma planilha de excel, arquivo CSV, etc.

<h2>TIPOS DE VARIÁVEIS</h2>

 <h4>1. Métricas: Quantitativas</h4>
 
 - Apresentam características que podem ser mensuradas ou contadas.

Principais características:

 - Podem ser representadas por diversas ferramentas descritivas, como medidas de posição, dispersão, e gráficos gerados a partir delas.
 Recorrentemente utilizam variáveis métricas:
 - Medidas de posição: Média, mediana e quartis e Medidas de dispersão: Variância e desvio padrão.

 <h4>2. Não métricas: Qualitativas ou categóricas</h4>
 
Indicam as características que não podem ser medidas.

Principais características:

- Tem sua representação feita por tabelas de frequência (observa as contagens em cada categoria) ou gráficos formados a partir delas.
Tipos de Frequência:
 - Frequência Absoluta: Contagem de ocorrência em cada categoria.
 - Frequência Relativa: Porcentual de cada categoria em relação ao total de observações (100%).
 
 Não é possível obter medidas descritivas como média ou desvio padrão. Exemplo: Não é possível ter uma média de nacionalidade, região, estado civil, etc.

<h4>3. Variáveis Dummy</h4>

São essenciais para transformar dados que não são números (categorias, nomes ou estados) em um formato numérico que os algoritmos de Machine Learning consigam processar.

- São colunas binárias (0 ou 1) criadas para representar dados categóricos. Elas permitem que modelos matemáticos processem informações qualitativas sem criar uma hierarquia falsa entre as categorias.

Características:

- Elimina a Hierarquia Falsa: Este é o motivo mais importante. Se você usar números simples (1, 2, 3) para representar categorias como "C#", "Java" e "Python", o modelo matemático vai assumir que: Python(3) > C#(1). O modelo pode achar que Python tem "mais valor" que C#, o que estragaria a lógica.
- Compatibilidade Matemática: Algoritmos como Regressão Linear, Redes Neurais e SVM baseiam-se em cálculos de distância e multiplicações de matrizes. Ao transformar o texto "São Paulo" em 0 em 1 o processador passa a entender corretamente.
- Interpretabilidade dos Pesos: Ao usar variáveis dummy, o modelo atribui um coeficiente (peso) para cada categoria, permitindo auditar a decisão. Fórmula de Exemplo (Score de 0 a 100): Score = 40 + (0,005 x Renda) + (25 x Moradia_Propria) - (10 x Moradia_Alugada)

É fundamental a identificação do tipo da variável para a escolha da técnica que será utilizada na análise dos dados, principalmente as variáveis ambíguas (que podem possuir duas ou mais interpretações).
Motivo: As melhores técnicas estatísticas e os modelos de machine learning são escolhidos em função do tipo de variável.


