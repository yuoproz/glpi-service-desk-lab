# 🖥️ GLPI Service Desk Lab — Simulação de Suporte Técnico N1

Um laboratório prático de **Service Desk e Suporte Técnico N1**, utilizando **GLPI**, **Docker Compose** e **MySQL**, desenvolvido para praticar o gerenciamento de incidentes, a investigação inicial e a documentação de soluções de TI.

O projeto simula o atendimento de um chamado envolvendo um computador do setor financeiro sem acesso à internet. O objetivo é demonstrar o fluxo de atendimento, o registro das evidências, a análise inicial e o encerramento documentado do chamado.

---

## 🛠️ Tecnologias Utilizadas

- **GLPI:** sistema de gerenciamento de serviços de TI (ITSM) para registro, acompanhamento e resolução de chamados.
- **Linux / Ubuntu via WSL:** ambiente utilizado para executar e administrar o laboratório.
- **Docker:** execução dos serviços em containers.
- **Docker Compose:** configuração e gerenciamento dos serviços GLPI e MySQL.
- **MySQL:** banco de dados utilizado pelo GLPI.
- **Redes TCP/IP:** prática de conceitos de conectividade, endereçamento IPv4, DHCP e DNS.
- **Comandos de diagnóstico:** utilização de `ipconfig`, `ping` e `nslookup`.
- **Git & GitHub:** versionamento e documentação do projeto.

---

## 🚀 Funcionalidades e Atividades Praticadas

- [x] **Gerenciamento de Chamados:** criação e acompanhamento de um incidente no GLPI.
- [x] **Classificação do Incidente:** definição de prioridade, impacto e urgência.
- [x] **Documentação da Investigação:** registro dos testes iniciais, dos resultados e das limitações encontradas.
- [x] **Registro de Solução:** documentação de uma solução hipotética para um problema de configuração DHCP.
- [x] **Aprovação e Encerramento:** conclusão do fluxo do chamado no GLPI.
- [x] **Ambiente Containerizado:** execução do GLPI e do MySQL por meio do Docker Compose.
- [x] **Persistência de Dados:** utilização de volumes Docker para armazenar os dados dos serviços.
- [x] **Segurança de Credenciais:** utilização de um arquivo `.env` local, excluído do versionamento por meio do `.gitignore`.

> **Importante:** o chamado de suporte é fictício. Os testes de rede foram executados no computador utilizado no laboratório, e não no computador fictício do solicitante. A falha DHCP e sua correção foram documentadas como parte da simulação, não como um reparo realizado em um equipamento real.

---

## ⚙️ Como executar o projeto

### 🐳 Via Docker Compose

#### 1. Pré-requisitos

- Linux ou Ubuntu via WSL2.
- Docker Engine.
- Docker Compose v2 ou superior.

#### 2. Clonar o repositório

```bash
git clone https://github.com/yuoproz/glpi-service-desk-lab.git
cd glpi-service-desk-lab
```

#### 3. Configurar as variáveis de ambiente

Crie o arquivo `.env` a partir do modelo fornecido:

```bash
cp .env.example .env
```

Abra o arquivo `.env` e configure as variáveis necessárias para o GLPI e o MySQL.

**Importante:** utilize credenciais próprias e não publique o arquivo `.env`. Ele contém informações privadas e deve permanecer fora do Git.

#### 4. Validar a configuração

```bash
docker compose config --quiet
```

Se o comando terminar sem erros, prossiga.

#### 5. Iniciar os serviços

```bash
docker compose up -d
```

#### 6. Verificar os contêineres

```bash
docker compose ps
```

Confirme se os serviços do GLPI e do MySQL estão em execução.

#### 7. Acessar o GLPI

Abra o navegador e acesse:

http://localhost:8080

Na primeira execução, siga as instruções de instalação exibidas pelo GLPI, caso necessário.

#### 8. Parar os serviços

```bash
docker compose down
```

Esse comando para e remove os contêineres, mas preserva os volumes de dados.

**Atenção:** evite executar `docker compose down -v` se quiser preservar os dados do laboratório, pois esse comando também remove os volumes declarados pelo projeto.

## 🔎 Exemplo de Investigação de Rede

Durante o laboratório, foram praticados comandos básicos de diagnóstico no computador utilizado para os testes.

**1. Consultar a configuração de rede**

```powershell
ipconfig
```

Permite consultar os endereços IP, as máscaras de sub-rede e os gateways disponíveis nas interfaces de rede.

**2. Testar a conectividade IP**

```powershell
ping 1.1.1.1
```

No teste realizado, houve resposta aos quatro pacotes enviados, sem perda.

**3. Verificar a resolução DNS**

```powershell
nslookup google.com
```

O comando foi utilizado para verificar a resolução do nome de domínio.

**Limitação:** esses resultados confirmam apenas o comportamento observado no computador de teste. Não identificam a causa do incidente fictício registrado no GLPI.

---

## 📋 Cenário do Chamado Simulado

**Título:** Sem acesso à internet no computador — setor financeiro

**Problema relatado:** o usuário informa que está conectado ao Wi-Fi, mas não consegue acessar sites e o sistema financeiro.

**Impacto:** atividade do setor financeiro comprometida no cenário proposto.

**Investigação inicial:** registro do incidente e identificação dos próximos testes necessários no computador do solicitante, incluindo a verificação da configuração IPv4 e do DHCP.

**Solução hipotética documentada:** falha temporária na obtenção da configuração IPv4 via DHCP, seguida da renovação da configuração de rede e da validação do acesso.

**Estado final:** chamado fechado no GLPI após o registro e a aprovação da solução simulada.

---

## 📸 Evidências do Projeto

Adicione nesta seção capturas de tela que demonstrem:

1. O painel principal do GLPI.
2. O chamado criado e sua classificação.
3. O histórico da investigação inicial.
4. A solução registrada e aprovada.
5. O estado final do chamado.
6. Os containers em execução no Docker Compose.

As imagens devem mostrar o funcionamento real do ambiente e preservar senhas, tokens e outras informações sensíveis.

---

## 🎯 Competências Desenvolvidas

- Fundamentos de Service Desk e ITSM.
- Registro, classificação e documentação de incidentes.
- Investigação inicial e interpretação de evidências.
- Fundamentos de IPv4, DHCP, DNS e conectividade.
- Utilização de comandos básicos de diagnóstico de rede.
- Execução de aplicações com Docker Compose.
- Administração básica de um ambiente Linux via WSL.
- Documentação técnica e segurança de credenciais.

---

## 📌 Status do Projeto

**Ambiente GLPI:** executado localmente com Docker Compose.

**Fluxo de atendimento:** praticado por meio de um chamado fictício, documentado e encerrado.

**Próximas melhorias:** adicionar capturas de tela organizadas, revisar a configuração para facilitar a reprodução do ambiente e ampliar o laboratório com novos cenários de suporte.

---
