# 04. Logs e monitoramento

Sem registro, você não sabe se houve um incidente, quando começou, o que foi atingido nem quem foi afetado. Log é a "caixa-preta" do sistema. Monitoramento é alguém (ou algo) olhando essa caixa-preta **antes** do desastre, e não só depois.

## O que a lei pede

- A empresa deve **demonstrar** que adotou medidas de segurança (LGPD, art. 6º, VII e X). Logs são a principal evidência dessas medidas funcionando.
- Em caso de incidente que possa causar risco ou dano relevante aos titulares, a empresa precisa comunicar a ANPD e os titulares (art. 48). Sem logs, não há como saber o que e quem foi atingido, e a comunicação fica incompleta.
- Dependendo da atividade, o **Marco Civil da Internet** (Lei 12.965/2014) pode obrigar a guardar registros de acesso a aplicações por prazo mínimo (art. 15, seis meses para provedores de aplicações que atuam de forma organizada e com fins econômicos). Verifique se isso se aplica ao seu negócio.
- Atenção ao outro lado: **o log também contém dado pessoal** (IP, usuário, horário, ações). Ele precisa ser protegido, ter prazo de retenção e finalidade, como qualquer outro dado.

## O que isso significa na prática

### 1. O que registrar

Para sistemas que tratam dados pessoais, registre os **eventos de segurança**:

- Logins, com sucesso e **falha**, e logouts
- Mudanças de permissão e criação ou remoção de contas
- Acesso, exportação e alteração de dados sensíveis (quem, quando, qual registro)
- Ações de administrador
- Erros graves e mudanças de configuração

Cada linha deve responder: **quem** fez, **o quê**, **quando**, de **onde** (IP ou dispositivo) e com que **resultado**.

### 2. O que NÃO registrar

- **Senhas**, nem as tentativas erradas
- Tokens, chaves de API e números de cartão completos
- Conteúdo de dados sensíveis (o prontuário inteiro, o documento enviado). Registre o **evento** ("usuário X abriu o registro 123"), e não o dado em si.

Log que guarda segredo vira uma segunda fonte de vazamento.

### 3. Proteger os logs

- Acesso restrito: poucas pessoas leem e **ninguém altera**
- Hora sincronizada nos servidores (NTP), senão a linha do tempo de um incidente não fecha
- Cópia em local separado do sistema de origem (se o servidor for invadido, o invasor não deve conseguir apagar o rastro)
- Prazo de retenção definido (por exemplo, 6 a 12 meses para logs de segurança) e descarte depois disso

### 4. Monitorar: alguém precisa olhar

Log que ninguém lê só serve para autópsia. Defina alertas simples para os sinais mais comuns de problema:

| Sinal | Pode indicar |
|---|---|
| Muitas falhas de login do mesmo IP em poucos minutos | Ataque de força bruta |
| Várias falhas seguidas de um login bem-sucedido | Conta comprometida |
| Login fora do horário ou de local incomum | Uso indevido de credencial |
| Criação de novo administrador ou mudança de permissão | Escalada de privilégio |
| Exportação ou download em massa de dados | Vazamento em andamento |
| Sistema de log parou de enviar eventos | Alguém desligou ou quebrou o registro |

Para pequena empresa, o começo pode ser simples: alertas por e-mail do próprio provedor ou sistema, ou um script que lê o log e avisa. Ferramentas como o Wazuh (código aberto) permitem centralizar e alertar com mais maturidade quando o ambiente cresce.

## Checklist

- [ ] Os sistemas com dados pessoais registram login, falhas, mudanças de permissão e acesso a dados sensíveis
- [ ] Cada registro tem quem, o quê, quando, origem e resultado
- [ ] Senhas, tokens e dados sensíveis completos não aparecem nos logs
- [ ] Os logs têm acesso restrito e não podem ser alterados por quem opera o sistema
- [ ] Há cópia dos logs fora do servidor de origem
- [ ] A hora dos servidores é sincronizada (NTP)
- [ ] Existe prazo de retenção definido e descarte depois dele
- [ ] Há alertas para falhas repetidas de login, novo administrador e exportação em massa
- [ ] Alguém tem a responsabilidade definida de ler os alertas
- [ ] Foi verificado se o Marco Civil da Internet exige guarda de registros no seu caso

## Erros comuns em empresas pequenas

- **Não ter log nenhum.** Quando acontece um incidente, ninguém consegue dizer o que foi exposto, e a empresa precisa assumir o pior cenário.
- **Log ligado, mas ninguém lê.** O ataque fica semanas registrado e nunca é notado.
- **Gravar senha ou dado sensível no log**, geralmente por um `print` ou depuração esquecida.
- **Logs só no próprio servidor.** O invasor apaga o rastro junto com o ataque.
- **Guardar log para sempre "por segurança".** Sem prazo, o log vira um acúmulo de dado pessoal sem finalidade.
- **Hora errada nos servidores**, o que impede correlacionar eventos entre sistemas.

## Próximo capítulo

O capítulo 05 trata de **backup e retenção**: como não perder os dados e por quanto tempo guardá-los.