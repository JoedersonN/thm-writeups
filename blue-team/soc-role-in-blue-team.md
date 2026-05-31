# TryHackMe — SOC Role in Blue Team

**Plataforma:** TryHackMe  
**Categoria:** Blue Team / SOC  
**Dificuldade:** Easy  
**Status:** ✅ Concluída  

---

## Objetivo

Compreender o funcionamento de um SOC (Security Operations Center), o papel do analista Blue Team e os frameworks, ferramentas e processos utilizados no dia a dia de operações defensivas.

---

## Conceitos Abordados

### O que é um SOC

Um SOC é o centro nervoso da defesa cibernética de uma organização. É a equipe responsável por monitorar continuamente o ambiente, detectar anomalias, investigar alertas e responder a incidentes antes que causem dano real. A room contextualiza bem essa dinâmica: o analista não age de forma reativa apenas — ele precisa entender o comportamento normal do ambiente para identificar o que está fora do padrão.

### Cyber Kill Chain

Framework desenvolvido pela Lockheed Martin que mapeia os estágios sequenciais de um ataque cibernético:

| Estágio | Descrição |
|---|---|
| Reconnaissance | Coleta de informações sobre o alvo |
| Weaponization | Criação do payload/exploit |
| Delivery | Entrega do payload (phishing, exploit web, etc.) |
| Exploitation | Execução do código malicioso |
| Installation | Persistência no sistema |
| Command & Control | Comunicação com o atacante |
| Actions on Objectives | Objetivo final (exfiltração, ransomware, etc.) |

Para um analista SOC, entender o Kill Chain é essencial: quanto mais cedo no ciclo o ataque for detectado, menor o impacto.

### MITRE ATT&CK

Base de conhecimento que cataloga as táticas, técnicas e procedimentos (TTPs) utilizados por grupos de ameaça reais. Diferente do Kill Chain, o ATT&CK é granular — permite mapear exatamente *como* um atacante age em cada fase, facilitando a criação de regras de detecção e a investigação de incidentes.

Exemplo prático: se um alerta aponta execução de `mimikatz.exe`, o analista consulta o ATT&CK e identifica a técnica T1003 (OS Credential Dumping), entende o contexto e sabe quais outros indicadores buscar.

### SIEM vs. EDR

Duas ferramentas centrais de um SOC com propósitos distintos:

- **SIEM (Security Information and Event Management):** agrega e correlaciona logs de múltiplas fontes (firewall, servidores, endpoints, DNS). Dá visibilidade ampla do ambiente. Exemplos: Splunk, Microsoft Sentinel, Wazuh.
- **EDR (Endpoint Detection and Response):** monitora comportamento em endpoints (workstations, servidores) em tempo real. Detecta processos suspeitos, movimentação lateral, persistência. Exemplos: CrowdStrike, SentinelOne, Defender for Endpoint.

Na prática: o SIEM vê o macro, o EDR vê o micro. Um analista SOC usa os dois em conjunto.

---

## Tarefa Prática — Simulação de Triagem

A parte mais valiosa da room é a simulação de um turno como analista júnior. O fluxo:

1. **Painel de alertas** com múltiplos eventos gerados pelo SIEM
2. **Triagem:** classificar cada alerta como falso positivo ou verdadeiro positivo
3. **Investigação:** correlacionar o evento com logs, IP de origem, usuário afetado
4. **Resposta:** seguir o playbook — isolar a máquina comprometida, escalar para o nível adequado, documentar

O ponto crítico que a room ensina: **a maioria dos alertas em um SOC real são falsos positivos**. A habilidade de triagem rápida e precisa é o que diferencia um analista eficiente de um que deixa o verdadeiro incidente passar no ruído.

---

## Principais Aprendizados

- O analista SOC Tier 1 é a primeira linha de defesa — seu trabalho é triar, não necessariamente resolver
- Frameworks como MITRE ATT&CK e Cyber Kill Chain são linguagens comuns entre times de segurança, não só teoria acadêmica
- SIEM e EDR são complementares; entender o que cada um detecta (e o que não detecta) é fundamental
- Documentação e follow do playbook não são burocracia — são o que garante resposta consistente e auditável

---

## Ferramentas Relacionadas

`SIEM` `EDR` `MITRE ATT&CK` `Cyber Kill Chain` `Splunk` `Wazuh`

---

*Writeup por [JoedersonN](https://github.com/JoedersonN) · [TryHackMe Profile](https://tryhackme.com/p/Joe.Sk)*
