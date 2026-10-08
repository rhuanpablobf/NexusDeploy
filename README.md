# 🚀 NexusDeploy

<p align="center">
  <b>Plataforma de Implantação e Orquestração de Aplicações e Serviços em VPS</b><br>
  Automatize a instalação das principais ferramentas de automação, IA, CRM e mensageria em seu servidor Linux.
</p>

---

## 📌 Requisitos Recomendados

- **Sistemas Operacionais Suportados:** Ubuntu 22.04 LTS / 24.04 LTS / 26.04 LTS ou Debian 11 / 12.
- **Hardware Mínimo Recomendado:** 2 vCPU e 4 GB de memória RAM.
- **Ambiente:** Servidor limpo/vazio para evitar conflitos de portas e redes Docker.

---

## 💿 Como Executar no Servidor (Oracle Cloud ou VPS)

Basta conectar no seu servidor via SSH como usuário com permissões de administrador e executar:

```bash
bash <(curl -sSL https://raw.githubusercontent.com/rhuanpablobf/NexusDeploy/main/Setup)
```

Ou, se preferir clonar diretamente o repositório:

```bash
git clone https://github.com/rhuanpablobf/NexusDeploy.git /root/NexusDeploy
cd /root/NexusDeploy
chmod +x Setup NexusDeploy
./Setup
```

---

## 🛠️ Principais Ferramentas Disponíveis

* **Borda e Infraestrutura:** Traefik (Proxy Reverso com SSL automático), Portainer CE.
* **Automação e IA:** n8n, Flowise, Dify AI, Ollama, Typebot, LangFlow, ActivePieces.
* **Mensageria e WhatsApp:** Evolution API (v1, v2, Go), WppConnect, Wuzapi, Quepasa.
* **Atendimento e CRM:** Chatwoot, TwentyCRM, Woofed CRM, Krayin CRM.
* **Bancos de Dados & Storage:** Supabase, PostgreSQL, MinIO, Redis, ClickHouse, MongoDB, Qdrant.
* **Observabilidade:** Grafana, Prometheus, cAdvisor, Uptime Kuma.
* **Produtividade e Segurança:** Keycloak, Vaultwarden, Nextcloud, Passbolt, Stirling PDF.

---

## 🔒 Segurança e Privacidade

- **Sem Telemetria Externa:** O NexusDeploy não envia endereços de IP ou métricas do seu servidor para servidores de terceiros.
- **Isolamento em Redes Docker:** As aplicações comunicam-se de forma segura através da rede interna do Docker Swarm.
- **Certificados TLS Automáticos:** Let's Encrypt nativo integrado ao Traefik para todas as aplicações web.
