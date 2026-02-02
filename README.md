# Dominando Modelos de Nuvem e Economia de Cloud ☁️

Este repositório faz parte dos meus estudos para **AZURE AZ-900** e aborda os conceitos fundamentais de modelos de implantação de nuvem.

---

## 🏗️ Modelos de Implantação

### 1. Nuvem Privada (Private Cloud)
Utilizada exclusivamente por uma única empresa em seu próprio datacenter.
* **Controle:** Total sobre os recursos, segurança e hardware.
* **Responsabilidade:** A organização é responsável pela manutenção, atualizações e operação dos serviços.
* **Restrição:** Não fornece acesso a usuários externos à rede da empresa.

### 2. Nuvem Pública (Public Cloud)
Recursos e serviços fornecidos por um provedor (como Azure) e acessados via internet.
* **Agilidade:** Aplicativos podem ser provisionados e removidos rapidamente.
* **Escalabilidade:** Escala vertical e horizontal conforme a demanda.
* **Economia:** Sem despesa de capital inicial; paga-se apenas pelo que for utilizado.

### 3. Nuvem Híbrida (Hybrid Cloud)
O "melhor dos dois mundos", conectando o ambiente local (*on-premises*) à nuvem pública.
* **Flexibilidade:** A empresa define onde executar os recursos com base em segurança e conformidade legal.
* **Interconectividade:** A nuvem privada interage diretamente com a pública para otimizar cargas de trabalho.

---

## 💸 Modelos de Custo: CapEx vs. OpEx

A transição para a nuvem geralmente representa uma mudança do modelo **CapEx** para o **OpEx**.

### CapEx (Despesas de Capital)
Refere-se ao investimento inicial em infraestrutura física.
* **Exemplo:** Construção de um datacenter local.
* **Características:** Gasto inicial elevado; o valor dos ativos reduz (depreciação) com o tempo.

### OpEx (Despesas Operacionais)
Refere-se aos gastos contínuos com produtos e serviços.
* **Exemplo:** Pagamento de máquinas virtuais e serviços em nuvem.
* **Características:** Modelo baseado em consumo; cobrança imediata e proporcional ao uso; sem custos de manutenção de hardware.

---

## 📊 Modelo de Consumo
Na computação em nuvem, o modelo de consumo garante que a empresa:
1.  Pague apenas pelo que utilizar.
2.  Tenha previsão de custos baseada no uso real.
3.  Elimine o desperdício de recursos ociosos.

---


## 🚀 Benefícios e Operação na Nuvem (Azure)

Nesta seção, detalho os pilares que sustentam a infraestrutura da Microsoft Azure, focando em confiabilidade, SLAs e gestão de recursos.

---

### 1. Alta Disponibilidade e SLA (Service Level Agreement)
A disponibilidade é garantida através de contratos de nível de serviço (SLA). Caso a Microsoft não atinja o percentual acordado, créditos de serviço são gerados para o cliente.

> ![Tabela de SLAs da Microsoft](img/TabelaSLA.png)

#### 🖥️ Configuração na Prática (Máquina Virtual)
Ao criar uma **Máquina Virtual**, o campo "Opções de disponibilidade" define o nível de resiliência do hardware. Cada escolha aqui altera o SLA e, consequentemente, o custo da solução.

> ![Configuração de Zona de Disponibilidade na VM](img/Zona-Disp-VM.png)

---

### 2. Redundância de Armazenamento e Impacto no SLA
A persistência e disponibilidade dos dados dependem da estratégia de replicação escolhida. Escrever dados em mais de um lugar diminui drasticamente o tempo de indisponibilidade.

* **LRS (Locally Redundant Storage):** Replicação local.
* **ZRS (Zone-Redundant Storage):** Replicação entre zonas.
* **GRS (Geo-Redundant Storage):** Replicação geográfica em região secundária.
* **GZRS (Geo-Zone-Redundant Storage):** Redundância de zona e geográfica combinadas.
* **RA (Read Access):** Permite leitura na região secundária mesmo se a principal falhar.

> ![Configuração de Redundância de Armazenamento](img/Conta-de-Armazenamento.png)

---

### 3. Agilidade e Escalabilidade
* **Escalabilidade:** Capacidade de ajustar recursos para atender à demanda (adicionar CPU/RAM ou instâncias).
* **Elasticidade:** O poder de reagir a saltos repentinos de demanda de forma automática ou manual.
* **Confiabilidade:** Graças à arquitetura descentralizada, os recursos podem estar espalhados pelo mundo.

---

### 4. Gestão, Previsibilidade e Segurança
* **Previsibilidade:** Avançar com confiança em custos e desempenho através do **Azure Well-Architected Framework**.
* **Segurança:** A Azure oferece as ferramentas (como firewalls e identidades), mas a implementação correta é de responsabilidade do cliente.
* **Governança:** Auditorias que sinalizam recursos fora de conformidade e ajudam na mitigação de riscos.
* **Gerenciabilidade:** Gerenciamento via **Portal, CLI ou PowerShell**, permitindo implantar recursos pré-configurados sem necessidade de intervenção manual massiva.

---

## 🛠️ Tipos de Serviços e Responsabilidade Compartilhada

Nesta etapa, exploramos os modelos de serviço (IaaS, PaaS, SaaS) e como a responsabilidade pela segurança e manutenção é distribuída entre o provedor (Microsoft) e o cliente.

---

### 📦 Modelos de Serviço

1. **IaaS (Infraestrutura como Serviço):** É o modelo mais flexível. O cliente tem controle sobre servidores, armazenamento e firewalls. É o que mais se aproxima de gerenciar um servidor físico, mas sem o hardware.
2. **PaaS (Plataforma como Serviço):** Focado em desenvolvimento. O cliente não se preocupa com o Sistema Operacional ou hardware, focando apenas na implantação de aplicativos e gerenciamento de bancos de dados.
3. **SaaS (Software como Serviço):** O nível mais alto. O cliente utiliza o software pronto, hospedado e gerenciado pelo provedor (Ex: Microsoft 365).

---

### 🤝 Modelo de Responsabilidade Compartilhada

O sucesso na nuvem depende de entender que a segurança e o gerenciamento são uma via de mão dupla. Dependendo do serviço escolhido, a Microsoft assume mais ou menos responsabilidades.

| Componente | IaaS | PaaS | SaaS |
| :--- | :---: | :---: | :---: |
| **Informações e Dados** | Cliente | Cliente | Cliente |
| **Dispositivos (Móveis/PCs)** | Cliente | Cliente | Cliente |
| **Contas e Identidades** | Cliente | Cliente | Cliente |
| **Identidade e Diretório** | Cliente | Compartilhado | Compartilhado |
| **Aplicativos** | Cliente | Compartilhado | Microsoft |
| **Controles de Rede** | Cliente | Compartilhado | Microsoft |
| **Sistema Operacional** | Cliente | Microsoft | Microsoft |
| **Hosts / Rede / Datacenter Físico** | Microsoft | Microsoft | Microsoft |

---

### 🔍 Detalhamento das Responsabilidades

#### **IaaS (Maior Controle)**
A Microsoft cuida apenas da infraestrutura física (Datacenter, Rede e Hosts). Todo o restante, desde a instalação do **Sistema Operacional** até a proteção dos **Dados**, é responsabilidade do cliente.

#### **PaaS (Foco no App)**
O gerenciamento do SO é transferido para a Microsoft. O cliente divide a responsabilidade em áreas como **Controles de Rede** e **Identidade**, focando seus esforços em gerenciar seus dados e usuários.

#### **SaaS (Menor Esforço)**
Quase tudo é gerenciado pela Microsoft. A única responsabilidade crítica que **sempre** permanece com o cliente, independente do modelo, é a gestão de:
* **Contas e Identidades**
* **Dispositivos**
* **Informações e Dados**

> **💡 Dica de Ouro:** Não importa o modelo (IaaS, PaaS ou SaaS), os **Dados** e a **Identidade** são sempre responsabilidade do cliente!

---

# 🏛️ Arquitetura e Organização do Azure

Nesta seção, abordo os componentes estruturais da Microsoft Azure, desde a infraestrutura global até a organização lógica de recursos e assinaturas.

---

## 🌎 Infraestrutura Global

### Regiões e Zonas de Disponibilidade
* **Regiões:** Conjunto de datacenters implantados em um perímetro definido por latência. Atualmente, a Azure conta com mais de 60 regiões em 140 países.
* **Custos:** O preço dos serviços varia conforme a região escolhida devido a impostos e infraestrutura local.
* **Zonas de Disponibilidade:** Datacenters fisicamente separados dentro de uma região (geralmente 3). Se um falha, o outro assume, garantindo **Alta Disponibilidade**.
* **Backbone Microsoft:** Todos os datacenters são conectados por uma rede de fibra ótica própria e privada da Microsoft.

### Pares de Regiões (Region Pairs)
Cada região possui um par geográfico (geralmente a 500km de distância). 
* **Replicação:** Permite a replicação automática de dados para recuperação em caso de desastres em escala regional.
* **Recuperação:** Em caso de interrupção global, uma região do par é priorizada para restabelecimento rápido.

### Regiões Soberanas
Atendem requisitos específicos de conformidade e legalidade (como a LGPD no Brasil):
* **Azure Government (EUA):** Instância isolada para agências governamentais dos EUA, acessada apenas por pessoal autorizado.
* **Azure China:** Operada pela 21Vianet, garante que todos os dados permaneçam dentro do território chinês conforme a legislação local.

> 🔗 **Dica:** Explore o mapa interativo em [Azure Globe](https://datacenters.microsoft.com/globe/explore/) para visualizar os pares de datacenters.

---

## 🗄️ Organização de Recursos

A Azure utiliza uma hierarquia para gerenciar custos e acessos:

1. **Grupos de Gerenciamento:** Gerenciam múltiplas assinaturas, aplicando políticas e conformidades que são herdadas.
2. **Assinaturas:** Unidade de faturamento e limites de acesso. Uma conta pode ter várias assinaturas (ex: uma para RH, outra para TI).
3. **Grupos de Recursos:** Containers lógicos para agrupar serviços de uma mesma solução (ex: Web + BD).
    * **Nota:** Recursos podem estar em regiões diferentes do seu grupo, mas pertencem a apenas um grupo por vez. Não é possível renomear um Grupo de Recursos após criado.
4. **Recursos:** As instâncias individuais (VMs, Storage, Redes).

---

## 🧪 Laboratório: Criando um Grupo de Recursos e Rede Virtual

Abaixo, os passos realizados para a criação e gestão de recursos no portal.

### 1. Criando o Grupo de Recursos (RG)
No painel lateral, acessei **Grupo de Recursos** e configurei os seguintes campos:
* **Assinatura:** Definição de qual conta será faturada.
* **Nome:** Identificação sugestiva do projeto.
* **Região:** Central Canada.
* **Tags (Marcações):** Utilizadas para organizar centros de custo e identificação de projetos (opcional, mas recomendado).

![Criação de Grupo de Recursos](img/Sobr-Pagina-1.png)

### 2. Ferramentas de Gerenciamento Interno
Dentro do grupo criado, explorei as seguintes abas:
* **Log de Atividades:** Auditoria completa de quem criou ou alterou algo.
* **Controle de Acesso (IAM):** Definição de níveis de permissão (seguindo o princípio do menor privilégio).
* **Visualizador de Recursos:** Exibição de um organograma visual das conexões entre os recursos.
* **Eventos:** Automação de tarefas e agendamentos.

### 3. Implementando uma Rede Virtual (VNet)
Para que uma VM funcione, ela precisa de uma rede. Criei uma **Rede Virtual** dentro do grupo de recursos anterior.
* **Interessante:** O Grupo de Recursos está no **Canada**, mas criei a Rede Virtual no **Brazil South**, demonstrando a flexibilidade da Azure em manter recursos de diferentes regiões sob o mesmo container lógico.

![Rede Virtual no Grupo de Recursos](img/Rede-Virtual.png)

---
*Estudos focados na certificação Microsoft Azure (AZ-900).*
