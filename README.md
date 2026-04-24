# 📊 Grafana - Monitoramento de Tráfego de Rede lab.gomes.local

Este repositório contém a stack e as configurações do **Grafana**, implementado para fornecer observabilidade detalhada sobre a infraestrutura de rede.

## 🎯 Finalidade

O Grafana é a nossa camada de visualização central. Sua principal missão neste projeto é monitorar em tempo real a **entrada e saída de internet** de toda a secretaria, permitindo identificar gargalos, picos de consumo e garantir a disponibilidade dos serviços educacionais e administrativos.

## 🚀 Foco do Monitoramento: Link de Internet

O dashboard principal foi desenvolvido para entregar métricas críticas de conectividade:

* **📈 Tráfego de Entrada (Inbound):** Monitoramento da largura de banda consumida pelos usuários e serviços internos.
* **📉 Tráfego de Saída (Outbound):** Análise de requisições enviadas ao mundo externo e serviços de borda.
* **⏱️ Latência:** Verificação do tempo de resposta dos links principais.
* **🚨 Alertas:** Notificações automáticas caso o consumo atinja níveis críticos ou haja queda de link.

## 🏗️ Infraestrutura

O Grafana está integrado ao nosso ecossistema de containers e alta disponibilidade:

* **Ambiente:** Docker Swarm (rodando em cluster de 5 nós).
* **Persistência:** Dados e dashboards armazenados em **Storage NFS** (`/storage/grafana`), garantindo que as métricas não sejam perdidas entre restarts.
* **Coleta de Dados:** (Ex: Integrado via Prometheus / SNMP Exporter / Zabbix) para buscar métricas diretamente dos switches e roteadores de borda.



## ✅ Vantagens para a SEDUC

1.  **Tomada de Decisão:** Dados concretos para planejar upgrades de link de internet.
2.  **Segurança:** Identificação de comportamentos anômalos que possam indicar ataques ou vazamento de dados.
3.  **Transparência:** Dashboards técnicos que facilitam o troubleshoot para a equipe de infraestrutura e redes.
4.  **Histórico:** Armazenamento de dados históricos para auditorias e relatórios mensais de utilização.

## ⚙️ Acesso ao Serviço

O painel está disponível internamente através do nosso Proxy Reverso:

* **URL:** `http://grafana.lab.gomes.local`
* **Autenticação:** Integrada (LDAP/AD se configurado).

---
*Equipe de Infraestrutura de TI - lab.gomes.local-PA*
