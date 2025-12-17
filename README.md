# 🛡️ Portfólio de Cibersegurança: Defesa & Monitoramento

## 📋 Resumo
Repositório dedicado à documentação de laboratórios práticos de Blue Team, focados em Hardening de Sistemas Operacionais e Monitoramento de Eventos de Segurança.

---

## 🚀 Laboratório 1: Hardening de Windows 11
**Objetivo:** Reduzir a superfície de ataque identificando portas abertas e mitigando serviços vulneráveis.

### 🛠️ Ferramentas
* **Kali Linux (Nmap):** Scan de portas.
* **PowerShell:** Configuração de Firewall e análise de processos.

### 📊 Execução
1.  **Reconhecimento:** O scan inicial identificou as portas 139 (NetBIOS), 445 (SMB) e 7070 (AnyDesk) abertas.
![Scan Inicial Nmap](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/Nmap%20Scan.png?raw=true)

2.  **Análise Forense:** Identificação dos processos atrelados às portas via comando `Get-NetTCPConnection`.
![Análise de Processos](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/image_d9ecc7.png?raw=true)

3.  **Mitigação:** Bloqueio de entrada no Firewall, desativação do SMB/NetBIOS e parada do serviço AnyDesk.
![Regra de Firewall](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/image_dac201.png?raw=true)

---

## 👁️ Laboratório 2: Auditoria e Logs (SIEM Básico)
**Objetivo:** Configurar o Windows para registrar tentativas de intrusão e identificar falhas de autenticação.

### 📊 Execução
1.  **Configuração de Auditoria:** Ativação de logs de falha de logon via `auditpol`.
    * Comando: `auditpol /set /subcategory:"Logon" /failure:enable`
2.  **Simulação de Ataque:** Tentativa de acesso com credenciais incorretas (Brute-force manual).
3.  **Detecção:** Identificação do **Event ID 4625** (Falha de Logon) no Visualizador de Eventos, registrando a tentativa de acesso não autorizado.

![Log de Evento 4625](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/Logs.png.png?raw=true)

---
*Laboratórios realizados por [Bragaart](https://github.com/Bragaart)*
