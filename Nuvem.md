# ☁️ Introdução ao AZ-900

## 1. Conceitos de Nuvem

### **Modelos de Implantação**
| Modelo | Descrição |
| :--- | :--- |
| **Nuvem Privada** | • Ambiente em nuvem somente para uma única entidade;<br>• Gestão interna ou terceirizada;<br>• Não fornecem acesso aos usuários fora da organização. |
| **Nuvem Pública** | • Oferecida por um provedor externo e compartilhada entre vários clientes;<br>• Acesso via internet (geralmente). |
| **Nuvem Híbrida** | • Usuários podem escolher com flexibilidade quais serviços manter na nuvem pública e quais implantar na infraestrutura de nuvem privada;<br>• Dados sensíveis ficam na privada;<br>• Processamento e serviços na pública;<br>• Integração entre ambientes. |
| **Multicloud** | • Lida com dois (ou mais) provedores de nuvem PÚBLICA e gerencia recursos e segurança em ambos os ambientes;<br>• Pode ter iniciado seu percurso de nuvem com um provedor e esteja em processo de migração para um provedor diferente |
| **Azure Arc** | • Conecta servidores, bancos de dados e clusters fora do Azure ao Azure.;<br>• Pode Gerenciar servidores locais pelo Azure, aplicar políticas (governança), monitorar tudo em um só lugar, controlar segurança centralizada, usar serviços do Azure fora da nuvem Azure |

## Solução VMware no Azure

* **O que é o VMware?:** Tecnologia que permite rodar várias máquinas virtuais em um único servidor físico.
* **O que é esse solução?:** Serviço que permite rodar ambientes VMware dentro do Azure sem precisar mudar quase nada.
* **Benefícios:** Continuar usando as mesmas ferramentas VMware; Evitar reescrever/adaptar aplicações; Rápida migração.

### **Modelos Financeiros**
| Conceito | Definição |
| :--- | :--- |
| **CapEx** | • Gastos antecipados em infraestrutura física;<br>• Valor que vai se reduzindo com o tempo, por exemplo um investimento em novos equipamentos e ambientes, que depois só será feito a manutenção.<br>• Pagamento imediato. |
| **OpEx** | • Gastos contínuos com serviços ao longo do tempo;<br>• Serviços de nuvem, assinatura, aluguel;<br>• Pagamento conforme uso. |
| **Modelo Baseado em Consumo** | • As organizações pagam somente pelos recursos e duração de uso.<br>• Não há custos iniciais para infraestrutura de hardware ou datacenter (provedor cuida disso).<br>•Não é necessário comprar e gerenciar a capacidade que pode ser subutilizada.<br>• A capacidade de adicionar recursos quando a demanda aumenta.<br>• A capacidade de liberar recursos quando a demanda diminui. |

## Controle de tráfego para alteração de capacidade

* **Quem controla isso?:** Pode ser automático OU manual, depende de como você configura.
* **Manual:** Alguém da equipe precisa ir no Azure e aumentar a capacidade de processamento, porém depende de monitoramento humano e não é rápido para picos inesperados.
* **Escala automática (Auto Scale):** NÃO é feito do nada, alguém precisa criar as regras antes para o devido funcionamento. Exemplo: Se CPU > 70% -> adicionar 1 máquina || Se CPU < 30% -> remover 1 máquina.

---

## 2. Benefícios da Nuvem

* **Alta disponibilidade (SLA):** Acordo de nível de serviço: Serviços podem ficar por um tempo indisponíveis; O cliente recebe créditos caso o tempo estipulado no contrato ultrapasse o padrão definido.

* **Escalabilidade:**
    * Ajustar recursos para atender à demanda;
    * Não paga além do necessário pelos serviços;
    * Se a demanda cair, você pode reduzir seus recursos e, assim, reduzir os custos;
    * **Escala vertical:** Adicionar mais CPUs ou RAM se precisar de mais capacidade de processamento.

* **Elasticidade:**
    * Seus recursos implantados poderiam ser expandidos (automaticamente ou manualmente) se tivesse um salto repentino na demanda;
    * Redimensiona o ambiente com base em requisições;
    * Se houver uma queda significativa na demanda, os recursos implantados poderão ser reduzidos horizontalmente.

* **Confiabilidade:**
    * Devido ao design descentralizado, a nuvem naturalmente dá suporte a uma infraestrutura confiável e resiliente;
    * Permite recursos implantados em várias regiões do mundo;
    * Mesmo que ocorra um imprevisto em uma região, as outras regiões ainda estarão em funcionamento.

* **Previsibilidade:** Permite que você avance com confiança no desempenho ou no custo.

* **Segurança:**
    * A nuvem oferece ferramentas de segurança que atendem às necessidades dos cliente, porém a implementação de muitas delas devem ser realizadas pelo próprio cliente;
    * **IaaS:** Fornecerá os recursos físicos caso você queira o controle máxima da segurança. Isso permite que você gerencia os SOs, softwares instalados, incluindo patches e manutenção;
    * **PaaS ou SaaS:** Podem ser as melhores opções, caso você queira que a aplicação de patches e a manutenção sejam tratadas automaticamente.

* **Gerenciabilidade:**
    * Gerenciar seu ambiente de nuvem e seus recursos por meio de um portal da web, ou linha de comando, APIs, PowerShell etc;
    * Implantar recursos com base em modelo pré-configurado, removendo a necessidade de configuração manual.

---

## 3. Serviços em Nuvem e Responsabilidade

### **Modelos de Serviço**
* **IaaS:** Aluguel de hardware virtualizado como servidores, máquinas virtuais, armazenamento, redes e sistemas operacionais. Responsabilidade do cliente: configuração. Provedor: segurança física, energia e conectividade.
* **PaaS:** Fornece um ambiente para a criação, hospedagem, teste e a implantação de aplicativos de software, sem focar no gerenciamento da infraestrutura. Meio termo entre IaaS e SaaS.
* **SaaS:** Você acessa o software pronto diretamente pela internet com o provedor controla absolutamente tudo.

### **Divisão de Responsabilidades**
| Ator | Responsabilidade Sempre |
| :--- | :--- |
| **Você (Cliente)** | • Informações e dados armazenados;<br>• Dispositivos permitidos (celulares, PCs);<br>• Contas e identidades de pessoas/serviços. |
| **Provedor** | • Datacenter físico;<br>• Rede física;<br>• Hosts físicos (máquinas reais/hardware). |

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

> 💡 **Monitoramento:** O processo pode levar tempo; acompanhe pelas notificações. Na aba **Visão Geral**, localize o campo **Host** para se conectar via SSMS.



