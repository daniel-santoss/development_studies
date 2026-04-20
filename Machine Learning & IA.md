# 🧠 Fundamentos de Machine Learning

## 1. Conceitos Principais

### **Machine Learning (Aprendizado de Máquina)**
É um subgrupo dentro da Inteligência Artificial que foca no processamento e análise de dados por meio de algoritmos, com o objetivo de gerar informações úteis para fundamentar a tomada de decisão.

> **PRÁTICA:** Problema e decisão → Necessidade de informação → Coleta e processa dados (Python) → Resumo útil para decisão.



[Image of Machine Learning vs Deep Learning vs Artificial Intelligence]


### **Deep Learning (Aprendizado Profundo)**
É uma subárea do Machine Learning focado no aprendizado profundo com base em redes neurais. É uma técnica específica e mais potente, inspirada na estrutura e no funcionamento dos neurônios do cérebro humano para processar dados e criar padrões para a tomada de decisão.

* **Vantagem:** Capacidade de aprender características automaticamente a partir de dados brutos (sem intervenção humana manual).
* **Requisito:** Necessita de milhões de exemplos para evitar "alucinações" ou o **Overfitting** (decorar em vez de aprender).

---

## 2. Objetivos e Tomada de Decisão

* **Encontrar Padrões:** Seja gerando modelos preditivos (previsões com base em relações estabelecidas) ou análise exploratória (identificar relações ocultas).

* **Data-driven decision making:** Tomar decisões baseadas em análise de dados resulta na redução de incertezas e aumento de eficácia.

* **Ponderação Arbitrária vs. Otimizada:** * **Arbitrária:** Atribuição manual de "pesos" baseada em intuição ou convenção.
    * **Otimizada:** O algoritmo ajusta os pesos matematicamente para encontrar a lógica mais precisa através dos dados.

---

## ⚙️ Fluxo do Machine Learning



[Image of Machine Learning Workflow]


1. **Definição do problema:**
    * Qual é o problema a ser resolvido?
    * Quais são os atributos envolvidos? (Relacionar os dados).

2. **Coleta dos dados:**
    * Fontes: Dados históricos ou em tempo real.
    * Avaliação fundamental da qualidade dos dados.

3. **Tratamento e preparação dos dados:**
    * Junção de bases, limpeza, criação de variáveis e seleção de observações.

4. **Aplicação de análises:**
    * Escolha de técnicas e modelos adequados.
    * Análises exploratórias e modelos multivariados.

5. **Interpretação e tomada de decisão:**
    * Como os resultados podem ser interpretados e colocados em prática.

---

## 🤖 Modelos Supervisionados

O modelo é treinado usando um conjunto de dados que já contém a **resposta correta** (pares de Entrada/Features e Saída/Target).

* **Features (Entrada):** Características ou atributos do que você está analisando.
* **Target (Saída/Rótulo):** Valor final que o modelo deve aprender a prever.



[Image of Supervised vs Unsupervised Learning]


### **Fases do Modelo Supervisionado**
1. **Fase de Treinamento:** O modelo estuda com o "gabarito" (Entrada + Saída) para ajustar seus parâmetros.
2. **Fase de Predição / Teste:** O modelo não tem acesso à saída. Ele gera uma resposta com base no que aprendeu e é avaliado em dados novos.

> **Atenção (Overfitting):** Se o modelo ajustar demais para corrigir detalhes mínimos, ele decora os dados de treino e falha ao receber dados novos.


[Image of Overfitting vs Underfitting]


---

## 🔍 Modelos Não Supervisionados

O algoritmo recebe dados **sem rótulos** e sem respostas pré-definidas. O objetivo é encontrar uma estrutura interna ou padrões ocultos por conta própria.

### **Fases do Modelo Não Supervisionado**
1. **Fase de Treinamento (Descoberta):** Analisa semelhanças matemáticas para criar grupos (clusters) ou regras.
2. **Fase de Predição / Aplicação:** O modelo decide em qual grupo um dado novo se encaixa com base na estrutura descoberta.

### **Métricas de Otimização**
* **Coesão (Inércia):** Garante que os pontos dentro de um mesmo grupo estejam próximos.
* **Separação:** Garante que os diferentes grupos estejam o mais distantes possível.
* **Método do Cotovelo (Elbow Method):** Identifica o número ideal de grupos onde o ganho de precisão estabiliza.
* **Silhouette Score:** Nota de -1 a 1 que mede o encaixe de cada ponto no seu grupo.



---

## 📊 Estrutura e Tipos de Variáveis

O banco de dados segue uma estrutura tabular (Excel, CSV) organizada em:
1. **Observações:** Unidade de análise (linhas).
2. **Variáveis:** Características e atributos medidos (colunas).

### **Classificação das Variáveis**

| Tipo | Nome | Características | Exemplos |
| :--- | :--- | :--- | :--- |
| **Quantitativas** | Métricas | Mensuráveis ou contáveis. Usam Média, Mediana, Variância. | Idade, Renda, Peso. |
| **Qualitativas** | Não Métricas | Categóricas. Representadas por tabelas de frequência (Absoluta/Relativa). | Nacionalidade, Estado Civil. |

### **Variáveis Dummy**
Essenciais para transformar categorias (texto) em números (0 ou 1) para que o processador entenda sem criar uma **Hierarquia Falsa**.

* **Exemplo:** Se usar C#=1, Java=2 e Python=3, o modelo pode achar que Python vale mais que C#. Com Dummy, cada linguagem vira uma coluna de sim (1) ou não (0).
* **Vantagens:** Compatibilidade matemática e interpretabilidade dos pesos (coeficientes).
# 🤖 Azure AI Foundry & Machine Learning (AI-102)

O Azure AI Foundry é o portal unificado da Microsoft onde você cria projetos de IA, implanta modelos, testa no playground e conecta serviços.

---

## 🏗️ Organização do Ambiente

| Recurso | Nível | Função |
| :--- | :--- | :--- |
| **Hub** | Organizacional | Agrupa projetos e recursos compartilhados. |
| **Project** | Trabalho | Ambiente específico para o desenvolvimento de uma solução. |
| **Deployment** | Entrega | Modelo implantado e pronto para receber chamadas de API. |

---

## 📚 Model Catalog

Biblioteca de modelos disponíveis no Foundry. Inclui modelos da OpenAI (GPT-4o, GPT-4), da Microsoft (Phi-4), da Meta (Llama) e outros. Você filtra por tarefa, custo e capacidade antes de implantar.

### **Modelos comparados no Lab**

| Atributo | Phi-4 (Microsoft) | GPT-4o (OpenAI) |
| :--- | :--- | :--- |
| **Tipo** | Modelo pequeno (SLM) | Modelo grande (LLM) |
| **Tamanho** | ~14B parâmetros | ~200B+ parâmetros |
| **Custo** | ● Baixo | ● Alto |
| **Velocidade** | ● Rápida | ● Moderada |
| **Raciocínio** | ● Bom | ● Excelente |
| **Melhor para** | Edge, apps leves | Lógica complexa, multimodal |

---

## 🧠 SLM x LLM

* **SLM (Small Language Model):** Econômica, ágil, boa com tarefas simples do dia a dia.
    * **Usa-se quando:**
    * App precisa rodar barato em escala;
    * Tarefa é simples: resumo, classificação, FAQ;
    * Precisa de resposta rápida (ex: chatbot de atendimento);
    * Rodar em dispositivo local / edge.

* **LLM (Large Language Model):** Resolve problemas complexos, possui mais contexto, porém tem mais custos (tokens/dinheiro) e demora um pouco mais para gerar uma saída.

> **Nota:** Uma SLM pode superar um LLM em tarefas específicas quando é bem treinada com dados relevantes e ajustada para aquele contexto, especialmente em problemas simples ou bem definidos.

---

## 📊 Métricas e Conceitos Técnicos

* **Parâmetros:** É basicamente um número interno que o modelo ajusta durante o treinamento para aprender a relacionar conceitos e prever textos. Quanto mais parâmetros, mais o modelo consegue guardar relações complexas entre ideias. Um modelo com 14 bilhões de parâmetros tem 14 bilhões desses números armazenados. É um tamanho, uma característica mensurável e concreta.

* **Capacidade:** Quantidade de conhecimento absorvido durante o treinamento como entender linguagem, raciocinar, generalizar (resolver problemas novos que ele nunca viu antes, usando o que aprendeu), memorizar padrões, manter contexto (lembrar de conversas).

* **TPM (Tokens Per Minute):** Quantos tokens o modelo processa por minuto. Se o limite for 1000 TPM, não é possível mandar um prompt com 2000 tokens, pois causará um erro. É possível ajustar a quota.
    * **Cálculo:** `Total de tokens = prompt(entrada) + Completion(Saída - Resposta da IA)`

* **RPM (Requests Per Minute):** Quantas chamadas ele suporta simultaneamente.

---

## ⚡ Boas Práticas de Prompt

**Por que não enviar tudo em um único prompt para economizar RPM?**
Pode ser vantajoso as vezes, porém o TPM será maior, e se a resposta for muito grande o modelo pode:
* Cortar a resposta se o limite de tokens forem atingidos;
* Perder precisão e se esquecer de responder certas perguntas;
* Maior tempo de resposta.

**Se precisar passar todo um contexto em um único prompt:**
Deverá estar de forma explícita no prompt que deve ser feita apenas uma análise completa e pedir para não gerar novas funcionalidades/mudanças. Caso for alteração/criação em múltiplos arquivos, solicitar ao modelo uma saída apenas uma de cada vez é uma boa prática.

---

## 🚀 Tipos de Implantação (Deployment)

### **Modelos de Capacidade e Roteamento**

| Tipo | Infraestrutura | Modelo de Custo | Recomendação de Uso |
| :--- | :--- | :--- | :--- |
| **Standard** | Compartilhada com outros clientes Azure. | Pague por token consumido (Pay-as-you-go). | Desenvolvimento, testes e projetos de pequeno porte. |
| **Global Standard** | Roteamento automático para o datacenter mais próximo/disponível. | Baseado em consumo, com foco em baixa latência global. | Apps em produção com usuários espalhados geograficamente. |
| **Provisioned (PTU)** | Capacidade dedicada e exclusiva (como um servidor alugado). | Pagamento por capacidade reservada (independente do uso). | Apps críticos, volume alto e previsível (Bancos, Hospitais). |



* **Observação sobre Standard:** Por ser capacidade compartilhada, se o servidor estiver lotado, pode haver fila no processamento.

* **Observação sobre Provisioned (PTU):** Garante desempenho constante e sem filas, pois a capacidade é reservada exclusivamente para o seu projeto.

---

### **Serverless - Models as a Service (MaaS)**

Modelo hospedado pelo provedor onde você não gerencia nenhuma infraestrutura.

* **Funcionamento:** Você não implanta nada, acessa o modelo diretamente via API, como um serviço externo. 

* **Modelos de Terceiros:** Muito comum para modelos que estão no catálogo mas não são nativos da Microsoft/OpenAI, como **Llama (Meta)** ou **Mistral**.

* **Melhor para:** Experimentar modelos open-source rapidamente sem precisar configurar nada ou gerenciar recursos de computação.

---

## 🎓 Foco na Certificação

> **Por que esse comparativo cai na prova:** o exame cobra muito cenários do tipo "qual modelo usar para X situação". Entender o trade-off custo vs. capacidade entre SLMs e LLMs é fundamental.
