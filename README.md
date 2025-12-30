# 🛡️ Portfólio de Cibersegurança: Blue Team Labs

## 📋 Resumo
Repositório dedicado à documentação de laboratórios práticos de Cibersegurança, demonstrando competências em Hardening, SIEM, Análise de Tráfego e Criptografia (Integridade).

---

## 🚀 Laboratório 1: Hardening de Windows 11
**🛠 Ferramenta:** Nmap & Windows Firewall  
  
**🎯 Objetivo:** Reduzir a superfície de ataque bloqueando portas críticas (ex: 139, 445).  
  
**📝 Descrição:** Identificação e mitigação de serviços vulneráveis na estação de trabalho para impedir acesso não autorizado via rede.  
  
**⚙️ Metodologia:** 
1. **Reconhecimento:** Scan com Nmap para listar portas abertas.
2. **Mitigação:** Regras de bloqueio no Firewall e desativação de serviços (SMB).
3. **Validação:** Novo scan confirmando o fechamento das portas.
  
### 📊 Execução
1.  **Reconhecimento:** Scan com **Nmap** identificou portas críticas abertas (139, 445, 7070).
![Scan Inicial Nmap](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/Nmap%20Scan.png?raw=true)

2.  **Mitigação:** Bloqueio de portas no Firewall e desativação de serviços (SMB/NetBIOS).
![Regra de Firewall](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/image_dac201.png?raw=true)  
  
**🔒 Conclusão:** O fechamento de portas não utilizadas (Princípio do Menor Privilégio) é a defesa primária contra exploração remota e movimentação lateral.  
  
---

## 👁️ Laboratório 2: Auditoria e Logs (SIEM Básico)
**🛠 Ferramenta:** Auditpol & Event Viewer  
  
**🎯 Objetivo:** Configurar auditoria para detectar tentativas de intrusão (Brute-force). 
  
**📝 Descrição:** Habilitação de logs de segurança para registrar falhas de autenticação e permitir a correlação de eventos suspeitos.  
  
**⚙️ Metodologia:** 
1. **Configuração:** Ativação de auditoria de logon via auditpol.
2. **Simulação:** Execução de tentativas de acesso com senhas erradas.
3. **Detecção:** Identificação do Event ID 4625 (Falha de Logon) nos logs.
  
### 📊 Execução
1.  **Configuração:** Ativação de logs de falha de logon via `auditpol`.
2.  **Detecção:** O **Event ID 4625** foi gerado e identificado após uma simulação de brute-force manual.

![Log de Evento 4625](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/Logs.png.png?raw=true)
  
**🔒 Conclusão:** A auditoria ativa é essencial para identificar ataques em andamento (como força bruta) que o firewall sozinho não bloqueia. 
  
---

## 📡 Laboratório 3: Análise de Tráfego (Wireshark)  
**🛠 Ferramenta:** Wireshark  
  
**🎯 Objetivo:** Interceptar e analisar a estrutura de pacotes de rede (foco em ICMP).  
  
**📝 Descrição:** Monitoramento de tráfego em tempo real para compreender o fluxo de comunicação e realizar troubleshooting de conectividade.  
  
**⚙️ Metodologia:**  

1. **Captura:** Sniffing na interface de rede principal.
2. **Filtro:** Isolamento do protocolo ICMP.
3. **Análise:** Visualização do handshake de Echo Request e Reply.
  
### 📊 Execução
1.  **Captura:** Utilização do **Wireshark** para interceptar tráfego da interface de rede.
2.  **Análise:** Filtragem de pacotes ICMP para visualizar a troca de mensagens de Request/Reply durante um teste de conectividade.

![Análise Wireshark](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/Log%20de%20ping.png?raw=true)  

**🔒 Conclusão:** A análise de pacotes permite visualizar o comportamento real dos protocolos e diagnosticar falhas de rede com precisão.

---

## 🔐 Laboratório 4: Integridade de Arquivos (Hashing)
**🛠 Ferramenta:** PowerShell (Get-FileHash)  

**🎯 Objetivo:** Garantir a integridade dos dados e detectar alterações não autorizadas (Tampering) utilizando Hashing.  

**📝 Descrição:** Uso de algoritmos de hash (SHA256) para validar matematicamente se arquivos críticos sofreram modificação.  

**⚙️ Metodologia:**  
1. **Baseline:** Geração do hash do arquivo original.
2. **Tampering:** Simulação de alteração maliciosa no conteúdo
3. **Validação:** Comparação dos hashes comprovando o "Efeito Avalanche".
   
### 📊 Execução
1.  **Criação de Prova:** Geração do hash SHA256 de um arquivo confidencial (`segredo.txt`) utilizando PowerShell.
![Hash Original](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/Hash_Original.png.png?raw=true)

2.  **Validação de Integridade:** Após simular uma alteração não autorizada no conteúdo do arquivo, um novo hash foi gerado. A mudança completa do código comprova o **Efeito Avalanche**, permitindo a detecção da fraude.
![Hash Modificado](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/Hash_Modificado.png.png?raw=true)

**🔒 Conclusão:** Hashes criptográficos são fundamentais para garantir a imutabilidade e validade jurídica de evidências digitais e nesse laboratório foi possivel comprovar que o documento foi modificado  

---

## 🛡️ Laboratório 5: Gestão de Vulnerabilidades (DAST)
**🛠 Ferramenta:** OWASP ZAP 
  
**🎯 Objetivo:** Identificar vulnerabilidades conhecidas em aplicações web utilizando varredura automatizada (DAST) para mitigar riscos antes de um ataque real.  
  
**📝 Descrição:** Execução de uma Varredura dinâmica (DAST) contra ambiente de teste (testphp.vulnweb.com) para identificar vulnerabilidades em aplicações e mitigar riscos antes de um ataque real.
  
**⚙️ Metodologia:**  
1. **Scan:** Execução de varredura automatizada (Spidering + Active Scan)
2. **Análise:** Classificação dos alertas de risco.
3. **Resultado:** Identificação da falta de Content Security Policy (CSP).  
  
### 📊 Execução
![Análise de Vulnerabilidade ZAP](Zaproxy%20CSP%20.png)  

**🔒 Conclusão:**
*Impacto:* Sem o cabeçalho CSP, a aplicação não valida a origem dos scripts, deixando o sistema vulnerável a ataques de **Cross-Site Scripting (XSS)** e injeção de dados.   



 ---
 
##  🕵️ Laboratório 6: Network Forensics - Análise de Tráfego e Captura de Credenciais

**🛠 Ferramenta:** Wireshark  
  
**🎯 Objetivo:** Demonstrar a vulnerabilidade de protocolos não criptografados (HTTP) e a capacidade de interceptar dados sensíveis na rede.

**📝 Descrição:**
Simulei a atuação de um analista de segurança monitorando o tráfego de rede para identificar riscos de arquitetura. O foco foi capturar credenciais transmitidas em texto claro (*Clear Text*) para comprovar a necessidade mandatória de SSL/TLS.
  

**⚙️ Metodologia:**
1.  **Sniffing:** Captura de pacotes em tempo real com **Wireshark**.
2.  **Alvo:** Acesso a aplicação vulnerável (`http://testphp.vulnweb.com/login.php`) via HTTP.
3.  **Análise:** Filtragem de tráfego (`http.request.method == POST`) e reconstrução de fluxo TCP.
4.  **Resultado:** Intercepção bem-sucedida de usuário e senha.

### 📊 Execução
![Captura Wireshark](https://github.com/Bragaart/Cybersecurity-Labs/blob/main/user%20%2B%20senha%20(Wireshark).png?raw=true)

**🔒 Conclusão:**
A ausência de criptografia permite que qualquer agente na rede capture dados críticos. A mitigação exige implementação de HTTPS em todas as camadas. 
  
*Laboratórios realizados por [Bragaart](https://github.com/Bragaart)*
