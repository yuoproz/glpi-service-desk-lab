# Chamado 01 — Computador sem acesso à internet

**Status:** Concluído (simulado) | **Prioridade:** Média | **Categoria:** Rede / Conectividade

## Cenário

Um funcionário do setor financeiro relata que não consegue acessar sites nem o sistema financeiro, apesar de o computador estar conectado ao Wi-Fi. No cenário, outros funcionários conseguem acessar a internet normalmente, enquanto o solicitante está impedido de utilizar o sistema financeiro. O problema teria começado cerca de 15 minutos antes da abertura do chamado.

## Investigação

1. O incidente foi registrado no GLPI com as informações relatadas pelo usuário fictício.
2. No computador utilizado pelo técnico no laboratório, foi executado `ping 1.1.1.1`. Os quatro pacotes enviados receberam resposta, sem perda.
3. No mesmo computador, `nslookup google.com` foi utilizado para verificar a resolução do nome de domínio, que ocorreu com sucesso.
4. A verificação da configuração IPv4, do gateway e do DHCP no equipamento fictício do solicitante foi planejada, mas não foi executada em um equipamento real do usuário.

Os testes realizados demonstram apenas que havia conectividade IP com o endereço testado e resolução DNS no computador de laboratório naquele momento. Eles não identificam a causa do cenário fictício.

## Causa

**Causa definida no roteiro simulado:** falha temporária na entrega da configuração IPv4 via DHCP. Essa é a causa registrada no chamado fictício, mas não foi reproduzida nem confirmada experimentalmente em um equipamento real.

## Solução

Na simulação, foi verificada a conexão Wi-Fi e atualizada a configuração de rede do computador. O registro do GLPI descreve que o equipamento fictício recebeu um endereço IPv4 válido, gateway padrão e configuração DNS, restabelecendo o acesso aos sites e ao sistema financeiro. Essa sequência representa o desfecho do cenário, não um reparo realizado em uma estação real.

## Validação

- **No computador de laboratório:** o `ping 1.1.1.1` recebeu quatro respostas e o `nslookup google.com` resolveu o domínio.
- **No cenário simulado:** o registro da solução informa que o acesso a sites e ao sistema financeiro foi testado com sucesso após a atualização da configuração de rede.
- **No GLPI:** a solução foi registrada, aceita e o chamado foi encerrado.
- **Limite da validação:** a restauração descrita ocorreu apenas na simulação. Os testes reais no computador do técnico não comprovam a resolução de um incidente em equipamento de solicitante.

## Prevenção

Em um atendimento real, recomenda-se verificar a concessão DHCP, o endereço IPv4, o gateway padrão e a resolução DNS no equipamento afetado. Também é útil documentar o resultado de cada teste e verificar a disponibilidade do escopo DHCP quando houver indícios de falha na distribuição de endereços.

Essas ações são recomendações para um atendimento real, não alterações realizadas neste laboratório.

## Evidências

**Histórico do chamado registrado no GLPI.**

![Histórico do chamado](evidencias/01-chamado-historico.png)

**Solução simulada aprovada e registrada.**

![Solução aprovada](evidencias/02-solucao-aprovada.png)

**Lista de chamados registrados no GLPI.**

![Lista de chamados](evidencias/03-lista-chamados.png)

## Limitações

- O cenário do usuário e o incidente são fictícios.
- Os testes `ping` e `nslookup` foram executados no computador do técnico, não no equipamento do solicitante.
- A falha DHCP não foi confirmada experimentalmente.
- A renovação de DHCP foi documentada como proposta simulada, não como reparo realizado.

## Competências praticadas

- Registro e encerramento de chamados no GLPI;
- Triagem inicial de incidente de conectividade;
- Fundamentos de IPv4, DHCP e DNS;
- Uso de `ping` e `nslookup`;
- Interpretação de resultados e identificação de limitações do diagnóstico;
- Documentação técnica de hipótese, solução proposta e validação.
