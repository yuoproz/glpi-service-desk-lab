## 📋 Cenário do chamado simulado

**Título:** Computador demora muito para iniciar o Windows.

**Problema relatado:** o usuário informa que o computador demora aproximadamente 8 minutos para iniciar o Windows e disponibilizar a área de trabalho.

**Impacto:** atraso no início das atividades profissionais do usuário.

**Investigação inicial:** análise da aba Inicializar do Gerenciador de Tarefas do Windows. Foram identificados quatro aplicativos classificados como de alto impacto: Free Download Manager, Microsoft Edge, Microsoft OneDrive e Roblox Game Client.

**Hipótese de solução documentada:** excesso de aplicativos configurados para iniciar automaticamente com o Windows, contribuindo para a lentidão durante a inicialização.

**Procedimento realizado:** desativação da inicialização automática do Free Download Manager e Roblox Game Client, mantendo os programas disponíveis para abertura manual.

**Estado final:** chamado encerrado no GLPI após reinicialização do computador de laboratório e observação de uma pequena melhora no tempo de inicialização.

> Os testes foram realizados no computador do técnico, não em equipamento de um usuário real. A melhoria foi percebida, mas não cronometrada. Portanto, não foi possível confirmar que os aplicativos eram a única causa da lentidão.

## 📸 Evidências do projeto

**Painel GLPI: chamados registrados e encerrados.**

![Painel GLPI](evidencias/01-painel-glpi.png)

**Chamado: investigação realizada e solução registrada.**

![Investigação e solução](evidencias/02-investigacao-solucao.png)

## 🎯 Competências praticadas

- Gerenciador de Tarefas do Windows.
- Gerenciamento de programas de inicialização.
- Identificação de aplicativos com alto impacto.
- Troubleshooting de desempenho.
- Aplicação de medidas corretivas.
- Documentação técnica de incidentes.