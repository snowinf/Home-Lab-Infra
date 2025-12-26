# 🏠 Home-Lab-Infra

## 🎯 Objetivo
Este projeto tem como objetivo montar um **home lab** que reproduza uma infraestrutura de rede corporativa, integrando serviços essenciais como **Active Directory, DNS, DHCP, File Server e Backup**.  
A implementação segue práticas de segurança modernas, incluindo **firewall restritivo, segmentação de rede por VLANs** e o uso do **Tier Model (T0, T1, T2)**, garantindo organização, controle de acesso e maior proteção dos recursos.

### Metas
- Aprender arquitetura de redes e identidade corporativa  
- Implementar controles de segurança reais  
- Simular cenários de ataque e defesa  

---

## 📌 Escopo do Projeto
- Active Directory (AD DS + DNS + DHCP)  
- Segmentação por VLAN  
- Firewall com políticas restritivas  
- Modelo de acesso **Tier 0 / 1 / 2**  
- Jump Servers e administração segura  

### Fora do Escopo (neste momento)
- Alta disponibilidade  
- Disaster Recovery / Backup off-site  
- Cloud  

---

## 🏗️ Arquitetura Geral
O ambiente é baseado em um **hypervisor Proxmox**, com um **firewall virtual (pfSense)** responsável pelo roteamento entre VLANs e controle de acesso.  
Todos os serviços internos utilizam o firewall como gateway padrão.

### Modelo de Segurança
- 🔒 **Default deny firewall**  
- 🔀 Segmentação de rede por função e nível de confiança  
- 🖥️ Administração centralizada via Jump Servers  
- 🔑 Separação de credenciais por Tiers  
- 🚫 Nenhuma administração a partir de máquinas de usuário  

---

## 🌐 Segmentação de Rede

| VLAN | Função          | Subnet        |
|------|-----------------|---------------|
| 10   | Tier 0 (AD)     | 10.10.10.0/24 |
| 20   | Tier 1          | 10.10.20.0/24 |
| 30   | Tier 2          | 10.10.30.0/24 |
| 31   | Tier 2 (extra)  | 10.10.31.0/24 |
| 40   | Infra           | 10.10.40.0/24 |
| 99   | Jump/Admin      | 10.10.99.0/24 |

---

## 🛡️ Cenários de Simulação
Este laboratório foi desenhado para permitir a simulação de:
- Movimentação lateral entre VLANs  
- Tentativas de escalada de privilégio  
- Abuso de credenciais  
- Impacto de regras de firewall incorretas  

> ⚠️ O foco não é impedir todos os ataques, mas **entender como decisões arquiteturais influenciam os resultados**.

---

## 📂 Estrutura de Diretórios
- **docs/** → Documentação técnica e decisões  
- **diagrams/** → Diagramas (draw.io / PDF)  
- **labs/** → Cenários de ataque e defesa  
- **screenshots/** → Evidências visuais selecionadas  

---

## 🚀 Status do Projeto
- [x] Planejamento e arquitetura  
- [ ] Implementação completa das VLANs  
- [ ] Criação de regras do firewall e isolamento de identidade  
- [ ] Hardening do Active Directory  
- [ ] Simulação de ataque  

---

## 🔮 Próximos Passos
1. Configuração das VLANs no pfSense  
2. Implementação do AD DS + DNS + DHCP  
3. Criação de Jump Servers e segregação de credenciais  
4. Aplicação de políticas de firewall (default deny + regras específicas)  
5. Hardening do AD e testes de segurança  
6. Execução dos cenários de ataque/defesa  
