<h2>Um prompt otimizado tem:</h2>

- Instruções: uma tarefa para o grande modelo de linguagem. Fornece uma descrição da tarefa ou instruções sobre o que o modelo deve fazer.
- Contexto: informação externa para guiar o modelo.
- Dados de entrada: a entrada para a qual você deseja obter uma resposta.
- Indicador de saída: o tipo ou formato de saída.

<h2>Boas Práticas:</h1>

- Os prompts devem ser claros e evitar ambiguidades.
- Adicionar contexto, exemplo: Faça um resumo desse artigo para o LinkedIn, instagram, etc..
- Especificar o tipo de saída desejada (faça dessa forma) e citar exemplos.
- Iniciar prompts com uma pergunta.
- Dividir um grande problema em pequenas tarefas até o objetivo final.


<h2>Temperatura:</h2>

Esse parâmetro controla a aleatoriedade ou criatividade da saída do modelo. Uma temperatura mais alta torna a saída mais diversificada e imprevisível, já uma temperatura mais baixa a torna mais concentrada e previsível. A temperatura é definida entre 0 e 1.

<h2>TOP-P:</h2>

Top p é uma configuração que controla a diversidade do texto, limitando o número de palavras das quais o modelo pode escolher conforme as probabilidades. O top p também é definido em uma escala de 0 a 1.

<h4>Se p = 0.85:</h4>

- "Azul" (40%) -> Soma = 40%
- "Limpo" (30%) -> Soma = 70%
- "Nublado" (15%) -> Soma = 85% (Parou aqui!)

Nesse caso, o conjunto de escolhas foi até a terceira palavra. Se a primeira palavra sozinha tivesse 90% de chance, apenas ela seria considerada.

- Vantagem: Ele se adapta à "confiança" do modelo. Se a IA está muito certa, o leque de opções diminui. Se ela está incerta, o leque aumenta.

<h2>TOP-K:</h2>

O top k limita o número de palavras às k palavras mais prováveis, independentemente de suas probabilidades percentuais.<br>
Por exemplo, se o top k for definido como 50, o modelo considerará apenas as 50 palavras mais prováveis para a próxima palavra da sequência

- Vantagem: É simples e evita que a IA escolha palavras completamente sem sentido.
- Problema: Ele é rígido. Se em um contexto existirem 20 palavras ótimas, ele corta 17. Se só existir 1 palavra boa e o resto for lixo, ele ainda assim vai manter as outras $k-1$ palavras ruins na disputa.

<h2>Zero-Shot:</h2>
A elaboração de prompts zero-shot é uma técnica em que um usuário apresenta uma tarefa a um modelo generativo sem oferecer nenhum exemplo ou treinamento explícito para essa tarefa específica. Nessa abordagem, o usuário confia no conhecimento geral e nos recursos do modelo para entender e executar a tarefa sem nenhuma exposição prévia, ou exemplos (shots), de tarefas semelhantes. 

<h2>Few-Shot:</h2>
A elaboração de prompts few-shot é uma técnica que envolve oferecer ao modelo de linguagem exemplos contextuais para orientar a compreensão e a saída esperada para uma tarefa específica.<br>
Nessa abordagem, você complementa o prompt com amostras de entradas e as saídas correspondentes, fornecendo ao modelo alguns exemplos (few shots) ou demonstrações para condicioná-lo à tarefa solicitada.

<h2>Prompts com Cadeia de Pensamento (CoT)</h2>
A elaboração de prompts com cadeia de pensamento (CoT) é uma técnica que divide tarefas complexas de raciocínio em etapas menores e intermediárias.<br>
Essa abordagem pode ser empregada usando técnicas de elaboração de prompts zero-shot ou few-shot.  

<h2>Riscos e usos indevidos de prompt:</h2>

<h3>Envenenamento</h3>
O envenenamento é a introdução intencional de dados maliciosos ou tendenciosos no conjunto de dados de treinamento de um modelo.
Isso pode fazer com que o modelo produza saídas tendenciosas, ofensivas ou prejudiciais, seja de forma intencional ou não.

<h3>Sequestro e injeção de prompt</h3>
Sequestro e injeção de prompt se referem à técnica de influenciar as saídas dos modelos generativos incorporando instruções específicas nos próprios prompts
com o objetivo de sequestrar o comportamento do modelo e fazer com que ele produza saídas que se alinhem às intenções do invasor, como gerar desinformação ou executar código malicioso.

<h3>Exposição</h3>
A exposição se refere ao risco de expor informações sensíveis ou confidenciais a um modelo generativo durante o treinamento ou a inferência. Um FM pode acabar revelando acidentalmente esses dados sigilosos presentes no corpus de treinamento, gerando possíveis vazamentos de dados ou violações de privacidade. Além disso, existe a possibilidade do sistema divulgar acidentalmente informações sobre histórico de navegação ou compras de outros pessoas em meio às recomendações geradas para novos clientes.

<h3>Vazamento de prompt</h3>

O vazamento de prompts se refere à divulgação ou vazamento não intencional dos prompts ou algoritmos usados em um modelo.
O vazamento não expõe necessariamente os dados protegidos.
Mas ele pode expor outros dados usados pelo modelo, o que pode revelar informações sobre como o modelo funciona e isso pode ser usado contra ele.

<h3>Jailbreak</h3>

Jailbreak é a prática de modificar ou contornar as restrições e medidas de segurança implementadas em um modelo generativo ou em um assistente de IA
para obter acesso ou funcionalidade não autorizados.

