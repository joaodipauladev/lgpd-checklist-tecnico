# 02. Controle de acesso

Dado pessoal vaza, na maioria das vezes, por acesso que não deveria existir: a conta de um ex-funcionário que continua ativa, a senha compartilhada na equipe, a planilha aberta para "qualquer pessoa com o link". Controle de acesso é decidir **quem pode ver ou alterar o quê**, e garantir que isso continue verdadeiro com o tempo.

## O que a lei pede

- Os agentes de tratamento devem adotar **medidas de segurança, técnicas e administrativas, aptas a proteger os dados pessoais de acessos não autorizados** e de situações acidentais ou ilícitas de destruição, perda, alteração, comunicação ou tratamento inadequado (LGPD, art. 46).
- O princípio da **segurança** (art. 6º, VII) e o da **responsabilização e prestação de contas** (art. 6º, X) exigem não só ter as medidas, mas **conseguir demonstrar** que elas existem.
- A lei incentiva regras de boas práticas e governança, que incluem o controle de quem acessa os dados (art. 50).

A LGPD não diz qual tecnologia usar. Ela exige que as medidas sejam **adequadas ao risco**: quanto mais sensível o dado, mais rigoroso o controle.

## O que isso significa na prática

### 1. Menor privilégio

Cada pessoa recebe **apenas** o acesso de que precisa para fazer seu trabalho, e nada além. A recepcionista precisa ver o agendamento, não o prontuário. O financeiro precisa de CPF para emitir nota, não do histórico de atendimento.

### 2. Uma conta por pessoa

Contas compartilhadas ("login do setor", "senha da loja") impedem saber **quem fez o quê** e tornam impossível revogar o acesso de uma pessoa só. Cada pessoa tem login próprio.

### 3. Autenticação forte

- **Verificação em duas etapas (2FA/MFA)** em e-mail, sistemas com dados pessoais, painel de hospedagem e qualquer conta de administrador
- **Senha única por serviço**, guardada num gerenciador de senhas, nunca numa planilha ou no bloco de notas
- Senhas longas (frases) valem mais que senhas complicadas e curtas

### 4. Ciclo de vida do acesso

| Momento | O que fazer |
|---|---|
| Admissão | Criar contas individuais com o perfil mínimo da função |
| Mudança de função | Remover os acessos antigos **e** conceder os novos |
| Desligamento | Desativar todas as contas **no mesmo dia** e trocar senhas compartilhadas, se existirem |
| Revisão periódica | A cada 6 ou 12 meses, listar quem tem acesso a quê e remover o que sobrou |

### 5. Contas privilegiadas e terceiros

- Contas de **administrador** são poucas, nominais, com 2FA obrigatório e usadas só quando necessário (o trabalho diário é feito com conta comum).
- **Fornecedores e prestadores** recebem acesso temporário e restrito, e a conta é removida quando o serviço termina.

### 6. Dispositivos e compartilhamento

- Bloqueio de tela automático e senha em computadores e celulares que acessam dados pessoais
- Evitar enviar dados pessoais por WhatsApp pessoal e e-mail sem proteção
- Links de pastas e planilhas compartilhadas restritos a pessoas específicas, nunca "qualquer pessoa com o link"

## Matriz de acesso (modelo)

Monte uma tabela simples com os papéis da empresa e o que cada um acessa:

| Papel | Cadastro de clientes | Dados financeiros | Dados sensíveis | Administração do sistema |
|---|---|---|---|---|
| Atendimento | Leitura e edição | Sem acesso | Sem acesso | Sem acesso |
| Financeiro | Leitura | Leitura e edição | Sem acesso | Sem acesso |
| Gestão | Leitura | Leitura | Leitura | Sem acesso |
| TI / responsável técnico | Sem acesso | Sem acesso | Sem acesso | Total (conta nominal, com 2FA) |

O ponto de partida é o [registro de tratamento](../templates/registro-de-tratamento.md) do capítulo 1: a coluna "Quem acessa" dele deve bater com esta matriz.

## Checklist

- [ ] Cada pessoa tem login individual, sem contas compartilhadas
- [ ] Existe uma matriz de acesso por papel e ela segue o menor privilégio
- [ ] 2FA ativo em e-mail, sistemas com dados pessoais e painéis de administração
- [ ] Senhas guardadas em gerenciador de senhas, sem reuso entre serviços
- [ ] Há procedimento de desligamento que desativa todas as contas no mesmo dia
- [ ] Os acessos são revisados ao menos uma vez por ano
- [ ] Contas de administrador são poucas, nominais e com 2FA
- [ ] Acessos de fornecedores são temporários e removidos ao fim do serviço
- [ ] Computadores e celulares que acessam dados têm bloqueio de tela e senha
- [ ] Links de compartilhamento são restritos a pessoas específicas

## Erros comuns em empresas pequenas

- **Conta do ex-funcionário que continua ativa.** É o vazamento mais evitável: ninguém lembra de revogar.
- **Todo mundo é administrador** porque "é mais fácil". Um erro ou um golpe de phishing numa conta assim compromete tudo.
- **Senha compartilhada no grupo da equipe.** Fica salva no histórico de mensagens, inclusive em celulares pessoais.
- **2FA só "quando der".** Sem ele, uma senha vazada em outro site vira acesso aos seus sistemas.
- **Acesso dado "só por um dia" e nunca removido.** Sem prazo e sem dono, o acesso temporário vira permanente.

## Próximo capítulo

O capítulo 03 trata de **criptografia**: como proteger o dado mesmo quando o acesso falha.