# Documento Base de Arquitetura e Engenharia: NexusDeploy

## 1. Visão Geral do Projeto

O **NexusDeploy** é uma plataforma automatizada em terminal para provisionamento, orquestração e gerenciamento de ecossistemas conteinerizados em servidores Linux (Debian e Ubuntu). O objetivo primordial é fornecer uma esteira ágil e confiável para implantação de aplicações de automação, mensageria, inteligência artificial, bancos de dados e ferramentas de suporte operacional em nuvem ou servidores dedicados.

---

## 2. Princípios Arquiteturais e Diretrizes

1. **Privacidade e Segurança por Padrão (Zero External Leaks):**
   * Nenhuma informação da infraestrutura (como endereços de IP público, nomes de domínio ou credenciais) deve ser transmitida para serviços externos de rastreamento.
   * Credenciais geradas localmente devem ser armazenadas com permissões estritas de leitura (`chmod 600`).

2. **Idempotência e Resiliência:**
   * Rotinas de instalação e validação devem ser tolerantes a falhas parciais e permitir reexecução sem corrupção de estado.
   * Utilização de comandos nativos do sistema operacional Linux (`nproc`, `free`, `ip`, `systemctl`) para coleta de métricas e hardware, eliminando dependências externas descontinuadas (como `neofetch`).

3. **Isolamento de Camadas e Serviços:**
   * Borda (*Ingress*): Traefik gerenciando roteamento reverso e certificados TLS automáticos (Let's Encrypt).
   * Orquestração: Docker Swarm em nó único com redes virtuais dedicadas (*overlay*).
   * Gerenciamento: Portainer CE integrado para controle de stacks conteinerizadas.

---

## 3. Estrutura do Ecossistema

* **Script de Inicialização (`Instalador`):** Responsável por preparar os pacotes fundamentais do sistema operacional, configurar o motor Docker e acionar o módulo principal de implantação.
* **Módulo Principal (`NexusDeploy`):** Responsável pelos menus interativos, validação de recursos do host, leitura de credenciais, geração de configurações Docker Compose e execução das stacks.
* **Diretório de Artefatos Locais (`dados_vps`):** Armazena de forma privada as credenciais, domínios e parâmetros gerados pelo operador do servidor.
* **Diretório de Recursos Adicionais (`Extras`):** Contém modelos, dashboards, traduções e configurações especializadas para serviços específicos.

---

## 4. Requisitos de Ambiente

* **Sistemas Operacionais Homologados:**
  * Ubuntu 22.04 LTS / 24.04 LTS / 26.04 LTS
  * Debian 11 / 12
* **Recursos Mínimos Recomendados:**
  * 2 vCPUs
  * 4 GB de memória RAM
  * 40 GB de armazenamento em disco
