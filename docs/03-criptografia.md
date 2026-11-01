# 03. Criptografia

O controle de acesso (capítulo 2) tenta impedir que a pessoa errada chegue ao dado. A criptografia é a segunda barreira: se o acesso falhar, porque um notebook foi roubado, um backup vazou ou alguém interceptou a conexão, o que o invasor leva é um dado **ilegível**.

## O que a lei pede

- A LGPD exige medidas de segurança **técnicas e administrativas aptas a proteger os dados pessoais** (art. 46) e trata a segurança como princípio (art. 6º, VII).
- A lei **não obriga uma tecnologia específica**, nem cita criptografia como exigência universal. Mas, na prática, ela é a medida técnica mais citada para demonstrar que o risco foi tratado, principalmente com dados sensíveis.
- Dados **anonimizados**, aqueles que não permitem mais identificar a pessoa por meios razoáveis, deixam de ser dado pessoal (arts. 5º, III e XI, e 12). Dado apenas criptografado **continua sendo dado pessoal**, porque quem tem a chave consegue reverter.

## O que isso significa na prática

Criptografia tem três frentes. Cada uma protege um momento diferente da vida do dado.

### 1. Em trânsito: o dado viajando

- Todo site e sistema que recebe dados pessoais deve usar **HTTPS** (TLS 1.2 ou superior), com certificado válido e renovação automática.
- Nada de **HTTP** puro, **FTP** ou **Telnet**. Para enviar arquivos, use SFTP ou um serviço de compartilhamento com acesso controlado.
- Acesso remoto a sistemas internos deve passar por **VPN** ou conexão segura, nunca expor serviços de administração direto na internet.
- Conferir isso é rápido: o [webcheck](https://github.com/joaodipauladev/webcheck) verifica versão de TLS, validade do certificado e o cabeçalho HSTS de um site.

### 2. Em repouso: o dado guardado

- **Disco inteiro** em notebooks e celulares que acessam dados pessoais: BitLocker (Windows), FileVault (macOS), LUKS (Linux), criptografia nativa no Android e iOS.
- **Servidores e bancos de dados**: use a criptografia de disco e de volume do provedor de nuvem e, para campos muito sensíveis (documentos, dados de saúde), considere criptografar a coluna na aplicação.
- **Backups**: devem ser criptografados. Backup em HD externo sem senha é um dos vazamentos mais comuns.
- **Pendrives e HDs externos** com dados pessoais: criptografados ou, melhor, evitados.

### 3. Senhas: hash, não criptografia

Senhas de usuários **nunca** são guardadas em texto puro nem criptografadas de forma reversível. Elas passam por uma função de **hash** com sal, projetada para ser lenta:

- Use **Argon2**, **bcrypt** ou **scrypt**.
- Evite MD5, SHA-1 e SHA-256 simples: são rápidos demais e quebram em segundos com força bruta.

### 4. Chaves e segredos

A criptografia só vale tanto quanto o sigilo da chave.

- **Nunca** deixe senhas, tokens e chaves de API no código-fonte ou em repositório (nem em repositório privado).
- Guarde segredos em variáveis de ambiente, num cofre de segredos ou no gerenciador do provedor.
- **Não guarde a chave junto do dado criptografado**: um disco criptografado com a chave escrita num papel colado no notebook não protege nada.
- Tenha um plano de **troca de chaves** quando alguém sai da equipe ou um segredo vaza.

## Checklist

- [ ] Todos os sites e sistemas com dados pessoais usam HTTPS com certificado válido
- [ ] O certificado renova automaticamente e há alerta antes do vencimento
- [ ] Não há serviços com HTTP puro, FTP ou Telnet em uso
- [ ] Computadores e celulares que acessam dados pessoais têm disco criptografado
- [ ] Backups são criptografados e a chave fica separada deles
- [ ] Senhas de usuários são guardadas com Argon2, bcrypt ou scrypt
- [ ] Nenhum segredo (senha, token, chave de API) está no código ou em repositório
- [ ] Existe procedimento de troca de chaves e senhas de serviço quando alguém sai da equipe
- [ ] Dados muito sensíveis têm proteção adicional (criptografia de campo ou de arquivo)

## Erros comuns em empresas pequenas

- **Certificado vencido que ninguém percebeu.** O site passa a exibir aviso de erro e os clientes perdem a confiança. Automatize a renovação.
- **Criptografar e deixar a chave junto.** Dá uma sensação de segurança que não existe.
- **Senha em texto puro no banco**, por ser "mais simples" de recuperar. Se o banco vazar, todas as contas caem.
- **Arquivo `.env` ou chave de API publicados no GitHub.** Robôs varrem repositórios públicos atrás desses arquivos em minutos.
- **Backup em HD externo sem proteção**, esquecido numa gaveta ou levado para casa.
- **Achar que criptografar equivale a anonimizar.** Dado criptografado continua sendo dado pessoal e continua sob a LGPD.

## Próximo capítulo

O capítulo 04 trata de **logs e monitoramento**: como saber quem acessou o quê e perceber quando algo dá errado.