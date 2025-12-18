# 🛡️ Portfólio de Cibersegurança: Blue Team Labs

## 📋 Resumo
Repositório dedicado à documentação de laboratórios práticos de Cibersegurança, demonstrando competências em Hardening, SIEM, Análise de Tráfego e Criptografia (Integridade).

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
2.  **Detecção:** O **Event ID 4625** foi gerado e identificado após uma simulação de brute-force manual.

![Log de Evento 4625](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/Logs.png.png?raw=true)

---

## 📡 Laboratório 3: Análise de Tráfego (Wireshark)
**Objetivo:** Interceptar tráfego de rede em tempo real para entender a estrutura de pacotes.

### 📊 Execução
1.  **Captura:** Utilização do **Wireshark** para interceptar tráfego da interface de rede.
2.  **Análise:** Filtragem de pacotes ICMP para visualizar a troca de mensagens de Request/Reply durante um teste de conectividade.

![Análise Wireshark](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/Log%20de%20ping.png?raw=true)

---

## 🔐 Laboratório 4: Integridade de Arquivos (Hashing)
**Objetivo:** Garantir a integridade dos dados e detectar alterações não autorizadas (Tampering) utilizando Hashing.

### 📊 Execução
1.  **Criação de Prova:** Geração do hash SHA256 de um arquivo confidencial (`segredo.txt`) utilizando PowerShell.
![Hash Original](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/Hash_Original.png.png?raw=true)

2.  **Validação de Integridade:** Após simular uma alteração não autorizada no conteúdo do arquivo, um novo hash foi gerado. A mudança completa do código comprova o **Efeito Avalanche**, permitindo a detecção da fraude.
![Hash Modificado](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/Hash_Modificado.png.png?raw=true)

---
*Laboratórios realizados por [Bragaart](https://github.com/Bragaart)*
