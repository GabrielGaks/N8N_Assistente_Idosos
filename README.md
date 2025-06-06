📦 Sistema Automatizado de Cadastro e Gerenciamento de Medicamentos via WhatsApp
Este repositório contém um workflow criado no n8n que automatiza o processo de cadastro, verificação e atualização de medicamentos para idosos via mensagens no WhatsApp. O sistema utiliza IA integrada ao Google Sheets para manipulação segura e orientada por regras.

🚀 Por que?
O projeto visa resolver a dificuldade que muitos idosos e seus familiares enfrentam para registrar e acompanhar medicamentos e horários de forma simples, acessível e sem depender de interfaces complexas. Usando apenas o WhatsApp, o usuário consegue manter seu controle de medicamentos atualizado com ajuda de um assistente de IA.

💡 O que é?
Um fluxo automatizado que:

Recebe mensagens do WhatsApp via Webhook

Interpreta a intenção do usuário com IA (OpenAI GPT-4o-mini)

Recupera ou atualiza dados do usuário em um Google Sheet

Interage com empatia e clareza com idosos

Evita ações automáticas sem consentimento explícito

🎯 Para quem?
🧓 Idosos que precisam de suporte no controle de seus medicamentos

👪 Familiares que desejam acompanhar os cuidados de saúde de entes queridos

👨‍⚕️ Profissionais ou instituições de saúde que querem automatizar esse controle

🧑‍💻 Desenvolvedores interessados em fluxos de automação com n8n, IA e Google Sheets

⚙️ Como funciona?
Recebimento de Mensagens: Um webhook capta mensagens do WhatsApp.

Extração de Dados: As mensagens são transformadas em estrutura JSON por um agente de IA.

Validação e Ação:

Se o usuário não existe, é solicitado o cadastro completo.

Se já existe, os dados são exibidos e a IA pergunta o que atualizar.

Execução:

Todas as ações (cadastrar, atualizar, listar) são feitas com ferramentas do Google Sheets.

Nenhuma resposta confirma uma ação sem ter executado a ferramenta correta antes.

Controle de Fluxo: Um Redis armazena e gerencia temporariamente as conversas por sessão.

🛠 Tecnologias Utilizadas
n8n – automação de fluxos

OpenAI GPT-4o-mini – IA para interpretação de mensagens

Google Sheets API – armazenamento dos dados

Redis – armazenamento temporário das conversas

WhatsApp Webhook – entrada de mensagens do usuário

🧠 Inteligência do Sistema
O sistema possui dois agentes:

Agente Operacional: executa comandos e aciona ferramentas (ex: criar/atualizar usuário).

Agente Explicativo: conversa com empatia, explicando o funcionamento e pedindo confirmação para ações.

📁 Estrutura do Google Sheets
Cada linha contém:

Número do usuário (ID do WhatsApp)

Nome do usuário

Medicamentos cadastrados

Horários de uso

Quantidade disponível

Número do responsável

✅ Regras de Funcionamento
Sempre verificar existência do usuário antes de cadastrar

Nunca executar ações sem consentimento do usuário

Mensagens devem ser claras, respeitosas e adaptadas à linguagem de idosos

O fluxo só é acionado por mensagens recebidas, sem agendamento ou execução paralela

📌 Como rodar localmente (opcional)
Caso queira adaptar ou executar este fluxo localmente:

bash
Copiar
Editar
git clone https://github.com/seu-usuario/nome-do-repo.git
cd nome-do-repo
Importe o JSON no n8n (My_workflow (5).json)

Configure suas credenciais de:

Google Sheets

Redis

OpenAI

Configure o Webhook de entrada com integração com WhatsApp (ex: Baileys ou API externa)

🤝 Contribuições
Pull Requests são bem-vindos! Se tiver ideias de melhoria, abra uma issue ou envie sua sugestão!

🧾 Licença
Este projeto está sob licença MIT.

