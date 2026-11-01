# 🖥️ GLPI Service Desk Lab — Simulação de Suporte Técnico N1

Laboratório prático de Service Desk e Suporte Técnico N1 utilizando GLPI, Docker Compose e MySQL. O projeto foi desenvolvido para praticar o gerenciamento de incidentes, a investigação inicial, o registro de evidências e a documentação de soluções de TI.

O cenário simula um chamado envolvendo um computador do setor financeiro sem acesso à internet. O objetivo é demonstrar o fluxo de atendimento, o planejamento dos testes de diagnóstico e o encerramento documentado do chamado.

> **Transparência:** o chamado é fictício. Os testes de rede foram realizados no computador utilizado no laboratório, não no equipamento fictício do solicitante. A falha de DHCP e sua correção foram documentadas como uma hipótese de simulação, e não como um reparo realizado em um equipamento real.

## 🛠️ Tecnologias utilizadas

- **GLPI:** gerenciamento de serviços de TI (ITSM) e registro de chamados.
- **Linux / Ubuntu via WSL2:** ambiente utilizado para executar e administrar o laboratório.
- **Docker Engine:** execução dos serviços em contêineres.
- **Docker Compose:** configuração e gerenciamento dos serviços.
- **MySQL:** banco de dados utilizado pelo GLPI.
- **Redes TCP/IP:** estudo de conectividade, endereçamento IPv4, DHCP e DNS.
- **Comandos de diagnóstico:** utilização de `ipconfig`, `ping` e `nslookup`.
- **Git e GitHub:** versionamento e documentação do projeto.

## 🚀 Funcionalidades e atividades praticadas

- **Gerenciamento de chamados:** criação e acompanhamento de um incidente no GLPI.
- **Classificação do incidente:** definição de prioridade, impacto e urgência no cenário simulado.
- **Documentação da investigação:** registro dos testes iniciais, dos resultados observados e das limitações.
- **Registro da solução:** documentação de uma hipótese de falha de configuração DHCP.
- **Encerramento do chamado:** conclusão do fluxo simulado no GLPI.
- **Ambiente containerizado:** execução do GLPI e do MySQL por meio do Docker Compose.
- **Persistência de dados:** utilização de volumes Docker para armazenar os dados dos serviços.
- **Proteção de credenciais:** utilização de um arquivo `.env` local, excluído do versionamento por meio do `.gitignore`.

## ⚙️ Como executar o projeto

### Pré-requisitos

- Linux ou Ubuntu via WSL2.
- Docker Engine.
- Docker Compose v2 ou superior.

### 1. Clonar o repositório

```bash
git clone https://github.com/yuoproz/glpi-service-desk-lab.git
cd glpi-service-desk-lab
```

### 2. Configurar as variáveis de ambiente

Crie o arquivo `.env` a partir do modelo:

```bash
cp .env.example .env
```

Abra o arquivo `.env` e configure as variáveis utilizadas pelo projeto:

```bash
nano .env
```

Utilize credenciais próprias e não publique o arquivo `.env`. Ele contém informações privadas e deve permanecer fora do versionamento.

**Importante:** os valores do `.env` precisam corresponder às credenciais esperadas pelo banco de dados. Em instalações existentes com volumes persistentes, alterar o arquivo `.env` não modifica automaticamente as credenciais já armazenadas no MySQL.

### 3. Validar a configuração

```bash
docker compose config --quiet
```

Se o comando terminar sem erros, prossiga.

### 4. Iniciar os serviços

```bash
docker compose up -d
```

### 5. Verificar os contêineres

```bash
docker compose ps
```

Confirme se os serviços do GLPI e do MySQL estão em execução.

### 6. Acessar o GLPI

Abra o navegador e acesse:

http://localhost:8080

Na primeira execução, siga as instruções de instalação do GLPI, caso necessário.

### 7. Parar os serviços

```bash
docker compose down
```

Esse comando para e remove os contêineres, mas preserva os volumes nomeados utilizados para armazenar os dados.

> **Atenção:** evite executar `docker compose down -v` se quiser preservar os dados do laboratório. Essa opção também remove os volumes declarados no projeto.

## 🔎 Exemplo de investigação de rede

Durante o laboratório, foram executados comandos básicos de diagnóstico no computador utilizado para os testes.

### 1. Consultar a configuração de rede

```cmd
ipconfig
```

Permite consultar informações como endereços IP, máscaras de sub-rede e gateways das interfaces de rede.

### 2. Testar a conectividade IP

```bash
ping 1.1.1.1
```

**Resultado observado:** os quatro pacotes enviados receberam resposta, sem perda.

Esse resultado indica conectividade IP com o endereço testado naquele momento. Isoladamente, não comprova que todos os sites ou serviços estejam acessíveis.

### 3. Verificar a resolução DNS

```bash
nslookup google.com
```

O comando foi utilizado para verificar a resolução do nome de domínio.

**Limitação:** os resultados demonstram apenas o comportamento observado no computador de teste. Não foi identificada a causa real do incidente fictício registrado no GLPI.

## 📋 Cenário do chamado simulado

**Título:** Sem acesso à internet no computador — setor financeiro.

**Problema relatado:** o usuário informa que está conectado ao Wi-Fi, mas não consegue acessar sites nem o sistema financeiro.

**Impacto:** as atividades do setor financeiro seriam comprometidas no cenário proposto.

**Investigação inicial:** registro do incidente e planejamento dos testes necessários no computador do solicitante, incluindo a verificação da configuração IPv4, do gateway e do DHCP.

**Hipótese de solução documentada:** falha temporária na obtenção da configuração IPv4 via DHCP, com proposta de atualização da configuração de rede e posterior validação da conectividade.

**Estado final:** chamado encerrado no GLPI após o registro da solução simulada.

> A hipótese de falha DHCP não foi confirmada experimentalmente no computador fictício. A solução registrada faz parte da simulação e não deve ser interpretada como um diagnóstico real.

## 📸 Evidências do projeto

Esta seção será complementada com capturas de tela do ambiente e das atividades realizadas:

- Painel principal do GLPI.
- Chamado criado e sua classificação.
- Histórico da investigação inicial.
- Solução registrada e encerramento do chamado.
- Contêineres em execução no Docker Compose.

As imagens devem representar o funcionamento real do ambiente e não podem expor senhas, tokens ou outras informações confidenciais.

## 🎯 Competências praticadas

- Fundamentos de Service Desk e ITSM.
- Registro, classificação e documentação de incidentes.
- Planejamento de investigação inicial e interpretação de evidências.
- Fundamentos de IPv4, DHCP, DNS e conectividade.
- Utilização de comandos básicos de diagnóstico de rede.
- Execução de aplicações com Docker Compose.
- Administração básica de ambiente Linux via WSL2.
- Documentação técnica e proteção de credenciais.

## 📌 Status do projeto

- **Ambiente:** GLPI e MySQL executados localmente com Docker Compose.
- **Atendimento:** fluxo praticado por meio de um chamado fictício, documentado e encerrado.
- **Documentação:** instruções de execução e configuração disponíveis no repositório.
- **Próximas melhorias:** adicionar capturas de tela reais, melhorar a reprodução do ambiente, documentar backup e restauração e ampliar o laboratório com novos cenários de suporte.
