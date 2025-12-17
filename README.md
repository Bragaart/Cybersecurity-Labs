# 🛡️ Laboratório: Hardening de Windows & Análise de Vulnerabilidades

## 🎯 Objetivo
Reduzir a superfície de ataque de uma estação Windows 11, identificando portas abertas com Kali Linux (Nmap) e mitigando os serviços desnecessários.

## 🛠️ Ferramentas Utilizadas
* **Atacante:** Kali Linux (Nmap)
* **Alvo:** Windows 11
* **Defesa:** PowerShell, Firewall do Windows, Configurações de Serviços (dcomcnfg).

## 📊 Passo a Passo

### 1. Reconhecimento (Scan Inicial)
Realizei um scan agressivo na rede interna para identificar portas expostas.
* **Comando:** `nmap -Pn 192.168.15.181`
* **Resultado:** Encontradas portas críticas abertas: 139 (NetBIOS), 445 (SMB) e 7070 (AnyDesk).

![Print do Nmap Inicial](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/Nmap%20Scan.png?raw=true)

### 2. Análise Forense (Identificação de Processos)
Antes de bloquear, investiguei quais processos estavam utilizando as portas suspeitas usando o PowerShell.
* **Comando:** `Get-NetTCPConnection` combinado com `Get-Process`.
* **Descoberta:** Identifiquei que a porta 7070 pertencia ao processo do AnyDesk (PID 4020) e a porta 135 ao sistema (svchost).

![Análise de Processos](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/image_d9ecc7.png?raw=true)

### 3. Hardening (Ações de Defesa)
Para mitigar os riscos, executei os seguintes procedimentos:
* **SMB (445):** Desativado via configurações da Placa de Rede.
* **NetBIOS (139):** Desativado nas configurações de TCP/IP.
* **AnyDesk (7070):** Serviço parado e desabilitado.
* **Firewall:** Criação de regra de bloqueio total ("Bloqueio Lab Cyber") para conexões de entrada.

![Configuração do Firewall](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/image_dac201.png?raw=true)

### 4. Conclusão e Resultados
Após as configurações, rodei um novo scan que confirmou o fechamento das portas críticas (445, 139 e 7070), reduzindo drasticamente a exposição da máquina.

---
*Laboratório realizado por [Bragaart](https://github.com/Bragaart)*
