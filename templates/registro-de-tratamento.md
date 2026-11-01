$conteudo = @'
# Registro de operações de tratamento

Preencha uma linha por tratamento. Revise a cada mudança relevante e ao menos uma vez por ano.

Responsável pelo registro: ______________________  Última revisão: ____/____/______

| # | Processo | Dados tratados | Titulares | Finalidade | Base legal | Onde fica | Quem acessa | Compartilhado com | Retenção | Sensível? |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Ex.: Cadastro de clientes | Nome, e-mail, telefone | Clientes | Emitir orçamento e contato comercial | Execução de contrato | CRM (nuvem) | Equipe de vendas | Fornecedor do CRM | 5 anos após o último contato | Não |
| 2 | | | | | | | | | | |
| 3 | | | | | | | | | | |
'@
[System.IO.File]::WriteAllText("$PWD\templates\registro-de-tratamento.md", $conteudo, (New-Object System.Text.UTF8Encoding($false)))