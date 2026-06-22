# Projeto-de-Infraestrutura-Virtualizada-Hibrida

## Proposta do Projeto:

### 📋 Objetivo Geral

O propósito deste projeto é o desenvolvimento, configuração e validação de um ambiente de rede virtualizado e isolado de alta performance, utilizando a stack open-source do Linux (**QEMU/KVM** gerenciada via **libvirt**) sobre o sistema operacional hospedeiro **Arch Linux**.

O laboratório simula uma arquitetura de infraestrutura corporativa real de DMZ/Rede Interna, focando na eficiência de recursos, segurança perimetral e controle estrito do fluxo de pacotes.

---

### 🛡️ Arquitetura e Componentes

O ambiente é segmentado em duas camadas lógicas principais:

1. **Camada de Borda (Gateway/Firewall - `gateway-vm`):**
* **Propósito:** Atuar como o único ponto de entrada e saída de dados do laboratório.
* **Tecnologia:** Implementado sobre o **Alpine Linux (Kernel Virt)** por conta de seu minimalismo extremo, segurança nativa mitigada contra *exploits* de memória e baixíssimo consumo de recursos (sub-30MB de RAM).
* **Função:** Operar com interface dupla (*dual-homed host*), onde uma interface se comunica com a rede externa/Internet e a outra gerencia e distribui a rede privada interna.


2. **Camada de Aplicação (Cliente - `app-vm`):**
* **Propósito:** Hospedar os serviços locais, bancos de dados ou aplicações que necessitam de proteção física e lógica.
* **Função:** Permanecer em uma rede completamente isolada do mundo externo, dependendo exclusivamente do roteamento, regras de firewall e NAT estabelecidos pela máquina de gateway para qualquer comunicação externa.



---

### 🚀 Justificativa e Relevância Técnica

A escolha de distribuições como Arch Linux na base e Alpine Linux nas instâncias virtualizadas justifica-se pela busca por **máxima eficiência de hardware**. Diferente de soluções pesadas baseadas em interfaces gráficas, este laboratório foca puramente no nível de sistema operacional e baixo acoplamento, permitindo simular cenários de rede complexos com consumo de hardware desprezível no computador hospedeiro.

Isso cria a fundação perfeita para estudar:

* Políticas de firewall estritas e tabelas de roteamento.
* Persistência de configurações de rede no Linux (`sysctl`, pontes virtuais e interfaces).
* Comportamento e análise de protocolos em redes isoladas.

---

Essa descrição te ajuda a amarrar o projeto para a faculdade? Se precisar que eu mude o foco para algum tópico específico (como segurança ou gerência de tráfego), é só avisar!
