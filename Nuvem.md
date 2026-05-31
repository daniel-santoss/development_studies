# ☁️ Guia de Estudos: AZ-900 (Microsoft Azure Fundamentals)

## 1. Conceitos de Nuvem

### **Modelos de Implantação**

| Modelo | Descrição |
| :--- | :--- |
| **Nuvem Pública** | • Oferecida por um provedor externo (como a Microsoft) e compartilhada entre vários clientes.<br>• Acesso geralmente via internet.<br>• Sem custos iniciais de hardware e infraestrutura física. |
| **Nuvem Privada** | • Ambiente em nuvem de uso exclusivo de uma única organização/entidade.<br>• Gestão interna ou terceirizada.<br>• Não fornece acesso a usuários fora da organização. |
| **Nuvem Híbrida** | • Combina nuvem pública e privada, permitindo que dados e aplicações sejam compartilhados entre elas.<br>• Dá flexibilidade para manter dados sensíveis na privada e processamento em massa na pública. |
| **Multicloud** | • Uso de dois ou mais provedores de nuvem **pública** diferentes (ex: Azure + AWS) para gerenciar recursos e evitar dependência de um único fornecedor. |

#### **Extensões de Ambiente**
* **Azure Arc:** Conecta servidores, bancos de dados e clusters Kubernetes fora do Azure (locais ou em outras nuvens) diretamente ao painel do Azure. Permite centralizar governança, políticas e segurança em um só lugar.
* **Solução VMware no Azure:** Serviço que permite rodar ambientes VMware nativos dentro do Azure sem precisar reescrever ou adaptar suas aplicações atuais, garantindo uma migração rápida.

---

### **Modelos Financeiros e de Consumo**

* **CapEx (Capital Expenditure):** Gastos antecipados em infraestrutura física (comprar servidores, construir datacenters). É um valor alto investido inicialmente que vai se depreciando com o tempo.
* **OpEx (Operational Expenditure):** Gastos contínuos com serviços e consumo ao longo do tempo. Na nuvem, você paga apenas pelo que usa (assinaturas, aluguel de recursos), sem custos iniciais de hardware.
* **Modelo Baseado em Consumo:** As organizações pagam somente pelos recursos utilizados e pela duração do uso. Não há custos iniciais, e a capacidade pode ser adicionada ou liberada conforme a demanda aumenta ou diminui.

#### **Controle de Capacidade e Tráfego**
* **Manual:** Alguém da equipe monitora o ambiente e aumenta a capacidade de processamento manualmente no portal. Lento e dependente de monitoramento humano para picos inesperados.
* **Escala Automática (Auto Scale):** Ajuste automatizado baseado em regras pré-configuradas criadas por você. *Exemplo:* "Se o uso de CPU passar de 70%, adicione 1 máquina; se cair para menos de 30%, remova 1 máquina".

---

### **Benefícios da Nuvem**

* **Alta Disponibilidade:** Garante que as aplicações continuem funcionando com o mínimo de tempo de inatividade (SLA), mesmo se ocorrerem falhas de hardware.
* **Escalabilidade:** Capacidade de ajustar os recursos para atender à demanda atual, evitando pagar por capacidade ociosa.
    * **Escala Vertical (Scale Up/Down):** Adicionar ou remover poder de processamento (CPU, RAM) a um recurso existente (ficar com uma máquina mais forte).
    * **Escala Horizontal (Scale Out/In):** Adicionar ou remover instâncias de recursos (adicionar mais máquinas idênticas para dividir o trabalho).
* **Elasticidade:** Capacidade de expandir ou reduzir os recursos **automaticamente** de forma dinâmica com base em picos ou quedas repentinas de demanda.
* **Confiabilidade:** Graças ao design descentralizado global, a nuvem permite implantar recursos em várias partes do mundo. Se uma região falhar, as outras continuam online.
* **Previsibilidade:** Permite prever custos futuros (com calculadoras) e o desempenho do ambiente (com monitoramento estruturado).
* **Segurança:** O provedor oferece ferramentas avançadas nativas, mas a implementação correta de muitas delas deve ser realizada pelo próprio cliente.
* **Gerenciabilidade:** Capacidade de gerenciar recursos via Portal Web, Linha de Comando (CLI), PowerShell ou por modelos pré-configurados de automação.

---

### **Modelos de Serviço e Responsabilidade Compartilhada**

* **IaaS (Infraestrutura como Serviço):** Aluguel de hardware virtualizado (VMs, armazenamento, redes). O cliente gerencia o Sistema Operacional, atualizações (patches) e softwares instalados. Máximo controle de infraestrutura.
* **PaaS (Plataforma como Serviço):** Fornece um ambiente pronto para criar, hospedar e implantar aplicações sem se preocupar com servidores, patches ou sistemas operacionais. Foco total no código.
* **SaaS (Software como Serviço):** O software é entregue pronto via internet e o provedor gerencia absolutamente tudo. Você apenas consome o serviço (ex: Microsoft 365, OneDrive).

#### **Divisão de Responsabilidades**

| Componente | IaaS | PaaS | SaaS |
| :--- | :---: | :---: | :---: |
| **Dados e Informações armazenados** | Cliente | Cliente | Cliente |
| **Dispositivos e Contas de acesso** | Cliente | Cliente | Cliente |
| **Aplicativos e Código** | Cliente | Cliente | Provedor |
| **Sistema Operacional** | Cliente | Provedor | Provedor |
| **Datacenter, Rede e Hardware Físico** | Provedor | Provedor | Provedor |

---

## 2. Infraestrutura Global do Azure

### **A Hierarquia Física ao Lógica**

Datacenter ➔ Zona de Disponibilidade ➔ Região ➔ Par de Regiões ➔ Geografia

* **Datacenter:** O prédio físico que contém os servidores com energia, resfriamento e rede independentes.
* **Zona de Disponibilidade (Availability Zone):** Um grupo de um ou mais datacenters isolados dentro de uma mesma região. Se um sofrer um desastre, o outro continua funcionando, garantindo a alta disponibilidade local.
* **Região:** Um conjunto de datacenters próximos geograficamente, conectados por uma rede de baixíssima latência. *Exemplos:* Brazil South (São Paulo), East US, West Europe. Ao criar um recurso, você deve escolher em qual região ele residirá.
* **Par de Regiões:** Duas regiões do mesmo país/área pareadas a pelo menos 480km de distância para recuperação de desastres (DR). Se uma região inteira cair, o par assume.
* **Geografia:** Um mercado discreto, normalmente composto por duas ou mais regiões, que preserva as fronteiras de residência de dados e conformidade legal.

> 🌐 **Foco na Prova: Replicação e Residência de Dados no Brasil**
>
> **Pergunta:** Se uma região inteira cair, os dados do Brasil não iriam para fora do país automaticamente?
> **Resposta:** Depende da sua configuração. O par de regiões existe para disponibilidade técnica, não para conformidade automática. A replicação geográfica (cruzar fronteiras) é uma escolha sua. Se você ativar o GRS no *Brazil South*, seu par padrão é o *South Central US* (EUA), logo seus dados cruzarão a fronteira.
> 
> Para manter a conformidade da LGPD/Residência de dados no Brasil, existem duas opções:
> 1. Usar redundância local/zona (LRS/ZRS) no **Brazil South** e abrir mão da recuperação automática entre regiões distantes.
> 2. Utilizar a região **Brazil Southeast** (Rio de Janeiro), que foi criada especificamente para ser o par local do *Brazil South* dentro do território nacional.

---

### **Níveis de Proteção contra Falhas**

| Proteção Contra | Solução Indicada |
| :--- | :--- |
| Falha de hardware no mesmo rack físico | **Availability Set** (Conjunto de Disponibilidade) |
| Falha de um datacenter inteiro (energia/fogo) | **Availability Zone** (Zona de Disponibilidade) |
| Falha de uma região geográfica inteira | **Par de Regiões** (Regional Pair) |

---

## 3. Hierarquia Organizacional (Governança)

Para organizar e aplicar políticas de segurança e cobrança em escala, o Azure usa quatro níveis de escopo:

1. **Grupos de Gerenciamento (Management Groups):** Recipientes que ajudam a gerenciar políticas, conformidade e orçamentos para múltiplas assinaturas.
2. **Assinaturas (Subscriptions):** Unidade fundamental de cobrança e controle de acesso. Uma empresa pode separar assinaturas por ambientes (*Produção*, *Desenvolvimento*, *Homologação*).
3. **Grupos de Recursos (Resource Groups):** Uma pasta lógica onde os recursos do Azure são implantados e gerenciados. 
    * *Regra de ouro:* Todo recurso deve pertencer a exatamente um grupo de recursos. Se você deletar o grupo, todos os recursos dentro dele são excluídos juntos.
4. **Recursos (Resources):** Instâncias de serviços que você cria no portal (VMs, bancos de dados, redes virtuais).

---

## 4. Serviços de Computação e Contêineres

### **Máquinas Virtuais e Ambientes de Hospedagem**
* **Azure Virtual Machines (VMs):** Computação de IaaS sob demanda. Dá total controle sobre o sistema operacional.
* **Availability Set:** Distribui as suas VMs entre racks físicos diferentes (domínios de falta e atualização) dentro de um único datacenter. Protege contra falhas locais de hardware.
* **VM Scale Sets:** Cria e gerencia um grupo de VMs idênticas que realizam o balanceamento de carga e a **escala automática** com base na variação de demanda.

### **PaaS e Serverless**
* **Azure App Service:** Serviço PaaS focado na hospedagem de aplicações web, APIs e backends móveis. Você se preocupa apenas com o código; o Azure cuida de patches, SO e servidores.
* **Azure Functions (Serverless):** Executa código baseado em eventos (um arquivo que chega, uma nova linha no banco). Você não gerencia servidores e paga estritamente pelo tempo de execução do código (processamento intermitente).

#### **Diferença Crucial para a Prova**
* **App Service:** O aplicativo fica sempre rodando; a cobrança é por hora com base no plano escolhido. Ideal para sites e APIs contínuas.
* **Azure Functions:** Executa sob demanda; a cobrança é por execução. Ideal para tarefas pontuais disparadas por eventos.

### **Contêineres**
* **Azure Container Instances (ACI):** A forma mais rápida e simples de rodar um contêiner isolado no Azure, sem precisar gerenciar ou provisionar servidores virtuais.
* **Azure Kubernetes Service (AKS):** Um serviço de orquestração robusto para gerenciar múltiplos contêineres em escala, ideal para arquiteturas complexas de microsserviços.

### **Azure Virtual Desktop**
* Um serviço de virtualização de desktop e aplicativos executado na nuvem. Muito associado em provas com cenários de "trabalho remoto", "funcionários usando dispositivos pessoais (BYOD)" e "redução de custos com hardware físico corporativo".

---

## 5. Serviços de Armazenamento (Azure Storage)

### **Tipos de Armazenamento de Dados**
* **Blob Storage:** Otimizado para armazenar volumes massivos de dados não estruturados (imagens, vídeos, logs, backups, arquivos genéricos). *Blob = Binary Large Object*.
* **Azure Files:** Compartilhamentos de arquivos totalmente gerenciados na nuvem, acessíveis por meio do protocolo padrão **SMB** (Server Message Block). Permite montar como uma unidade de rede no Windows/Linux.
* **Queue Storage:** Serviço para armazenamento e recuperação de grandes volumes de mensagens, permitindo o desacoplamento e a comunicação assíncrona entre aplicações.
* **Table Storage:** Banco de dados NoSQL do tipo chave-atributo, ideal para armazenar dados estruturados simples e não relacionais de forma barata.
* **Disk Storage:** Discos persistentes e virtuais anexados diretamente a Máquinas Virtuais (computação).

#### **Camadas de Acesso do Blob (Storage Tiers)**

| Camada | Custo de Armazenamento | Custo de Acesso | Cenário Ideal |
| :--- | :---: | :---: | :--- |
| **Hot** (Frequente) | Alto | Baixo | Dados acessados e modificados frequentemente. |
| **Cool** (Esporádico) | Médio | Médio | Dados armazenados por pelo menos 30 dias (acesso mensal). |
| **Cold** (Raro) | Baixo | Alto | Dados armazenados por pelo menos 90 dias (acesso raro). |
| **Archive** (Arquivo) | Muito Baixo | Muito Alto | Backups de longo prazo (mínimo 180 dias). Fica offline e leva horas para reidratar. |

---

### **Estratégias de Redundância de Armazenamento**

* **LRS (Locally Redundant Storage):** Cria 3 cópias dos dados dentro de um **único** datacenter na região primária. É a opção mais barata, mas vulnerável a falhas totais do prédio.
* **ZRS (Zone-Redundant Storage):** Cria 3 cópias distribuídas entre 3 zonas de disponibilidade diferentes na região primária. Protege contra a queda de um datacenter inteiro.
* **GRS (Geo-Redundant Storage):** Faz a replicação LRS na região primária + replica assincronamente (LRS) em uma **região secundária par**. Protege contra falhas regionais completas.
* **GZRS (Geo-Zone-Redundant Storage):** Combina a alta disponibilidade do ZRS na região primária com a proteção contra desastres regionais do GRS (enviando cópias LRS para a região par). É a opção mais resiliente e cara.

---

## 6. Identidade, Acesso e Segurança

### **Microsoft Entra ID (Antigo Azure AD)**
É o serviço de gerenciamento de identidades e acessos baseado em nuvem da Microsoft. Cuida da autenticação (quem você é) e autorização (o que você pode acessar).

* **SSO (Single Sign-On):** Permite que o usuário faça login uma única vez e ganhe acesso a múltiplos sistemas e aplicações sem precisar digitar as credenciais novamente ("um login para tudo").
* **MFA (Multi-Factor Authentication):** Exige dois ou mais fatores de verificação para garantir o acesso seguro: algo que você sabe (senha) + algo que você possui (celular/token) + algo que você é (biometria).
* **Passwordless:** Autenticação moderna que elimina o uso de senhas tradicionais utilizando chaves de segurança físicas, Windows Hello ou o aplicativo Microsoft Authenticator.

### **RBAC (Role-Based Access Control)**
Controle de acesso baseado em funções. Define **quem** pode fazer o quê em determinados recursos do Azure.

| Função Básica | Permissões |
| :--- | :--- |
| **Owner** (Proprietário) | Controle total sobre todos os recursos, incluindo o poder de delegar acesso a terceiros. |
| **Contributor** (Colaborador) | Pode criar e gerenciar todos os tipos de recursos do Azure, mas não pode conceder acesso a outros usuários. |
| **Reader** (Leitor) | Pode visualizar os recursos existentes, mas não pode realizar nenhuma alteração ou exclusão. |

### **Azure Policy**
Enquanto o RBAC foca em *quem* tem acesso, o Azure Policy foca no **o que** pode ser feito nos recursos, independentemente de quem esteja operando. Ajuda a manter padrões corporativos e governança.
* *Exemplos:* Bloquear a criação de VMs fora da região *Brazil South*; exigir que todas as contas de armazenamento usem HTTPS; obrigar o uso de tags específicas.

### **Tags (Marcas)**
Pares de chave-valor aplicados diretamente aos recursos para fins de organização e rastreamento de custos.
* *Exemplo:* `Departamento: TI`, `Ambiente: Producao`.
* Não afetam o funcionamento do recurso, mas ajudam o Azure Cost Management a emitir relatórios de gastos detalhados por setor.

---

## 7. Gerenciamento de Custos e Suporte

### **Ferramentas de Estimativa e Análise**
* **Azure Cost Management:** Ferramenta interna gratuita para monitorar, analisar e otimizar os gastos atuais do Azure. Permite criar orçamentos e disparar alertas caso o consumo chegue perto do limite definido.
* **Calculadora de Preços:** Utilizada para **estimar os custos mensais** antes de criar os recursos no ambiente do Azure.
* **Calculadora de TCO (Total Cost of Ownership):** Utilizada para **comparar os custos** de manter uma infraestrutura física local (on-premises) versus migrar toda a operação para a nuvem da Microsoft.

#### **Diferença Prática entre as Calculadoras**

| Calculadora de Preços | Calculadora de TCO |
| :--- | :--- |
| Estima os custos dos serviços dentro do Azure. | Compara custos de infraestrutura física vs. Nuvem. |
| Utilizada **antes** de criar um novo recurso. | Utilizada **antes** de decidir se vale a pena migrar. |

---

### **Planos de Suporte do Azure**

* **Basic:** Gratuito para todas as contas. Dá acesso apenas à documentação, fóruns e suporte técnico para problemas de faturamento e limites de assinatura.
* **Developer:** Indicado para ambientes de teste e desenvolvimento. Suporte técnico disponível apenas em horário comercial por e-mail.
* **Standard:** Indicado para ambientes de produção. Suporte técnico 24 horas por dia, 7 dias por semana (telefone/e-mail) com tempos de resposta mais rápidos.
* **Professional Direct:** Indicado para empresas com dependência crítica do Azure. Inclui suporte prioritário, gerenciamento proativo e suporte de arquitetos da Microsoft.

---

## 8. Governança, Compliance e Privacidade

* **Microsoft Purview:** Uma família de soluções de governança, risco e conformidade de dados. Ajuda a mapear, catalogar e descobrir dados confidenciais (como informações protegidas pela LGPD/GDPR) em todo o seu ambiente.
* **Central de Confiabilidade (Trust Center):** Portal público da Microsoft contendo informações detalhadas, relatórios de auditoria externa e certificações que provam o cumprimento das normas de privacidade, segurança e conformidade da infraestrutura em nuvem.

---

## 🗄️ Guia Prático: Banco de Dados (Azure SQL)

### **Pré-requisitos**
- [ ] **Assinatura do Azure:** Ter uma conta ativa.
- [ ] **Permissões:** Função de Colaborador da Instância Gerenciada de SQL.

### **Passo a Passo no Portal**
1. **Acesso:** Pesquise por "Azure SQL" ou acesse [aka.ms/azuresqlhub](https://aka.ms/azuresqlhub).
2. **Criação:** Clique em `+ Criar` > `Instância Gerenciada de SQL`.
3. **Aba Básico:** Selecione Assinatura, Grupo de Recursos, Nome, Região e Credenciais do Admin.
4. **Configuração:** Defina a camada (Uso Geral/Crítico), vCores e Armazenamento.
5. **Rede:** Configure VNet, sub-rede dedicada e Ponto de Extremidade Público (se necessário).
6. **Revisar:** Clique em `Revisar + criar` e depois em `Criar`.

> 💡 **Monitoramento:** O processo de provisionamento pode levar algum tempo; acompanhe o andamento pelas notificações do portal. Na aba **Visão Geral** do recurso gerado, localize o campo **Host** para utilizá-lo na conexão via SSMS (SQL Server Management Studio).
