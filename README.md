# 🖥️ GLPI Service Desk Lab

Laboratório prático de **Suporte Técnico N1 e Service Desk**, desenvolvido com GLPI, Docker Compose e MySQL.

O projeto tem como objetivo simular atendimentos de TI, praticar investigação de incidentes, troubleshooting e documentação técnica.

## 🛠️ Tecnologias utilizadas

- GLPI — gerenciamento de chamados e ITSM.
- Docker e Docker Compose — ambiente containerizado.
- MySQL — banco de dados.
- Linux / Ubuntu via WSL — administração do ambiente.
- Windows — diagnóstico e suporte técnico.
- Git e GitHub — versionamento e documentação.
- Redes TCP/IP — conectividade, IPv4, DHCP e DNS.

## 📋 Cenários de suporte

| Nº | Cenário | Status |
|---|---|---|
| 01 | Sem acesso à internet | Concluído |
| 02 | Inicialização lenta do Windows | Concluído |
| 03 | Redefinição de senha | Planejado |
| 04 | Impressora não imprime | Planejado |
| 05 | Problemas de conexão Wi-Fi | Planejado |
| 06 | Falha ao acessar um site | Planejado |
| 07 | Instalação de software | Planejado |
| 08 | Pouco espaço em disco | Planejado |
| 09 | Acesso a pasta compartilhada | Planejado |
| 10 | Computador desconectado da rede | Planejado |

## 📂 Documentação dos chamados

- [Chamado 01 — Sem acesso à internet](docs/chamados/01-sem-acesso-internet/README.md)
- [Chamado 02 — Inicialização lenta do Windows](docs/chamados/02-inicializacao-lenta/README.md)

## 🚀 Como executar

### Pré-requisitos

- Docker Engine.
- Docker Compose.
- Linux ou Ubuntu via WSL.

### 1. Clonar o repositório

```bash
git clone https://github.com/yuoproz/glpi-service-desk-lab.git
cd glpi-service-desk-lab
