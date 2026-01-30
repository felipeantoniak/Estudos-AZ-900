# Dominando Modelos de Nuvem e Economia de Cloud ☁️

Este repositório faz parte dos meus estudos na **DIO (Digital Innovation One)** e aborda os conceitos fundamentais de modelos de implantação de nuvem e a diferença financeira entre CapEx e OpEx.

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
*Estudos focados na certificação Microsoft Azure (AZ-900).*
