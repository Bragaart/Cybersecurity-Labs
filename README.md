# 🛡️ Portfólio de Cibersegurança: Blue Team Labs

## 📋 Resumo
Repositório dedicado à documentação de laboratórios práticos de Cibersegurança, focados em Hardening, Monitoramento e Análise de Redes.

---

## 🚀 Laboratório 1: Hardening de Windows 11
**Objetivo:** Reduzir a superfície de ataque identificando portas abertas e mitigando serviços vulneráveis.

### 📊 Execução
1.  **Reconhecimento:** Scan com **Nmap** identificou portas críticas abertas (139, 445, 7070).
![Scan Inicial Nmap](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/Nmap%20Scan.png?raw=true)

2.  **Mitigação:** Bloqueio de portas no Firewall e desativação de serviços (SMB/NetBIOS).
![Regra de Firewall](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/image_dac201.png?raw=true)

---

## 👁️ Laboratório 2: Auditoria e Logs (SIEM Básico)
**Objetivo:** Configurar o Windows para registrar tentativas de intrusão e identificar falhas de autenticação.

### 📊 Execução
1.  **Configuração:** Ativação de logs de falha de logon via `auditpol`.
2.  **Detecção:** O **Event ID 4625** foi gerado e identificado após uma simulação de brute-force manual (erros de senha propositais).

![Log de Evento 4625](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/Logs.png.png?raw=true)

---

## 📡 Laboratório 3: Análise de Tráfego (Wireshark)
**Objetivo:** Interceptar tráfego de rede em tempo real para entender a estrutura de pacotes e protocolos de comunicação.

### 📊 Execução
1.  **Captura:** Utilização do **Wireshark** com driver Npcap para interceptar tráfego da interface de rede.
2.  **Filtragem:** Aplicação do filtro `icmp` para isolar os pacotes de teste.
3.  **Análise:** Identificação clara da negociação de conexão (Three-Way Handshake não se aplica ao ICMP, mas vemos a troca de mensagens):
    * **Echo (ping) request:** Minha máquina solicitando resposta.
    * **Echo (ping) reply:** O servidor (8.8.8.8) confirmando o recebimento.

![Análise Wireshark](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/Log%20de%20ping.png?raw=true)

---
*Laboratórios realizados por [Bragaart](https://github.com/Bragaart)*
