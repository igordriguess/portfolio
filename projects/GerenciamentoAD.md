---
layout: project
type: project
image: img/project-image.svg
title: "Ferramenta para Gerenciar usuários no Active Directory (AD)"
date: 2025
published: true
labels:
  - PowerShell
summary: "Script Gerenciador de Usuários em PowerShell"
---

<img class="img-fluid" src="../img/ManipulaAD.png">

<b>🚀 Automatizando a Gestão de Usuários no Active Directory com PowerShell 💻</b> <br/>
Gerenciar usuários no Active Directory (AD) pode ser uma tarefa repetitiva e propensa a erros quando feita manualmente. Pensando nisso, desenvolvi um script em <b>PowerShell</b> para simplificar e automatizar as operações mais comuns no AD, garantindo eficiência e padronização no gerenciamento.

🎯 <b>Funcionalidades do Script:</b> <br/>
✅ <b>Verificação de Permissões:</b> <br/>
- O script verifica se está sendo executado com privilégios de administrador. <br/>
- Se não estiver, reinicia automaticamente com as permissões necessárias. <br/>

📂 <b>Integração com o Active Directory:</b> <br/>
- Verifica se o módulo Active Directory está instalado antes de continuar. <br/>
- Conecta ao domínio especificado. <br/>

🛠️ <b>Operações Disponíveis:</b> <br/>
<b>Consultar Usuário pelo Primeiro Nome:</b> <br/>
- Pesquisa usuários pelo primeiro nome e exibe informações como nome completo, login, e-mail, status (ativo/inativo) e grupos pertencentes. <br/>

<b>Listar Todos os Usuários:</b> <br/>
- Exibe todos os usuários do AD, filtrando contas padrão como administrator e guest. <br/>

<b>Criar Novo Usuário:</b> <br/>
- Cria um novo usuário no AD com informações personalizadas. <br/>
- Define senha, cargo, e adiciona aos grupos especificados. <br/>

<b>Remover Usuário:</b> <br/>
- Exclui um usuário do AD de forma segura. <br/>

<b>Resetar Senha do Usuário:</b> <br/>
- Permite redefinir a senha de um usuário. <br/>
- Oferece opções para exigir a troca de senha no próximo login e para definir se a senha nunca expira. <br/>

<b>Modificar Grupos do Usuário:</b> <br/>
- Adiciona ou remove usuários de grupos no AD. <br/>

<b>Ativar/Inativar Usuário:</b> <br/>
- Ativa ou desativa contas de usuário de forma rápida. <br/>

📋 <b>Interface Simples e Intuitiva:</b> <br/>
- Menu interativo que guia o administrador pelas opções. <br/>
- Feedback visual para cada ação realizada. <br/>

⚡ <b>Destaques Técnicos:</b> <br/>
Segurança: Uso de SecureString para manipulação de senhas. <br/>
Eficiência: Automação de tarefas críticas reduzindo erros humanos. <br/>
Flexibilidade: Possibilidade de personalizar o script para diferentes domínios e estruturas de AD. <br/>

💡 <b>Por que usar este script?</b> <br/>
Economia de Tempo: Automatiza tarefas manuais recorrentes. <br/>
Consistência: Garante que todas as operações sigam o mesmo padrão. <br/>
Segurança: Minimiza riscos relacionados à manipulação manual de contas. <br/>
Se você lida com ambientes que utilizam o Active Directory, esse script pode ser um grande aliado na sua rotina! ⚙️🔐 <br/>
💬 Gostou? Tem sugestões ou dúvidas? Entre em contato comigo! 👇 <br/>
📲💬 +55 16 99158-4347

Clique [aqui](https://github.com/igordriguess/PowerShell/blob/main/ManipulaAD.ps1) para ter acesso o código completo, aproveite e bom uso!!!
