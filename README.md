# 🖥️ GLPI Service Desk Lab

Laboratório prático de **Suporte Técnico N1 e Service Desk**, desenvolvido com GLPI, Docker Compose e MySQL.

O projeto simula situações comuns de suporte técnico em um ambiente controlado, com foco em gerenciamento de chamados, investigação de incidentes, troubleshooting e documentação de soluções.

## 🛠️ Tecnologias e ferramentas

| Tecnologia | Aplicação no projeto |
|---|---|
| GLPI | Gerenciamento de chamados e ITSM |
| Docker | Execução de aplicações em contêineres |
| Docker Compose | Orquestração do ambiente |
| MySQL | Banco de dados |
| Linux / Ubuntu (WSL2) | Administração do ambiente |
| Windows | Diagnóstico e suporte técnico |
| Git e GitHub | Versionamento e documentação |
| TCP/IP | Fundamentos de conectividade, IPv4, DHCP e DNS |

## 📋 Cenários de suporte

| Nº | Cenário | Status |
|:---:|---|---|
| 01 | Computador sem acesso à internet | Concluído |
| 02 | Inicialização lenta do Windows | Concluído |
| 03 | Redefinição de senha | Planejado |
| 04 | Impressora não imprime | Planejado |
| 05 | Problemas de conexão Wi-Fi | Planejado |
| 06 | Falha ao acessar um site | Planejado |
| 07 | Instalação de software | Planejado |
| 08 | Pouco espaço em disco | Planejado |
| 09 | Acesso a pasta compartilhada | Planejado |
| 10 | Computador desconectado da rede | Planejado |

## 📂 Documentação e evidências

Cada chamado possui uma documentação individual, com descrição do cenário, investigação, solução registrada, evidências e competências praticadas.

**Chamado 01 — Sem acesso à internet**

[Consultar documentação e evidências](docs/chamados/01-sem-acesso-internet/README.md)

**Chamado 02 — Inicialização lenta do Windows**

[Consultar documentação e evidências](docs/chamados/02-inicializacao-lenta/README.md)

## 🚀 Como executar o laboratório

### Pré-requisitos

- Linux ou Ubuntu via WSL2
- Docker Engine
- Docker Compose v2 ou superior

### 1. Clonar o repositório

```bash
git clone https://github.com/yuoproz/glpi-service-desk-lab.git
cd glpi-service-desk-lab
```

### 2. Configurar as variáveis de ambiente

```bash
cp .env.example .env
nano .env
```

Configure as credenciais locais conforme as variáveis esperadas pelo projeto. Não compartilhe o arquivo `.env`.

### 3. Iniciar o ambiente

```bash
docker compose up -d
```

### 4. Verificar os contêineres

```bash
docker compose ps
```

### 5. Acessar o GLPI

Abra o navegador e acesse:

http://localhost:8080

### 6. Encerrar o ambiente

```bash
docker compose down
```

Os volumes nomeados são preservados por esse comando. Evite `docker compose down -v` caso queira manter os dados do laboratório.

## 🎯 Competências desenvolvidas

- Atendimento e gerenciamento de chamados com GLPI.
- Fundamentos de ITSM e Service Desk.
- Registro e classificação de incidentes.
- Investigação e troubleshooting.
- Diagnóstico básico de conectividade.
- Fundamentos de IPv4, DHCP e DNS.
- Administração básica de Linux e Docker.
- Documentação técnica e versionamento com Git.

## 📌 Status do projeto

**Em desenvolvimento.**

Dois cenários de suporte foram documentados e possuem evidências do laboratório. Os demais serão desenvolvidos e adicionados progressivamente.

> **Nota:** os atendimentos são simulações para fins de aprendizagem. Os testes e resultados são identificados conforme foram efetivamente realizados no ambiente de laboratório.
