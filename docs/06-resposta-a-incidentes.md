# 06. Resposta a incidentes

Mais cedo ou mais tarde, algo vai dar errado: um notebook roubado, um e-mail enviado para a pessoa errada, uma conta invadida, um ransomware. O que separa um susto de uma crise é **ter decidido antes** quem faz o quê. Durante o incidente ninguém tem tempo nem calma para inventar o processo.

## O que a lei pede

- O controlador deve comunicar à **ANPD** e ao **titular** a ocorrência de incidente de segurança que possa acarretar **risco ou dano relevante** aos titulares (LGPD, art. 48).
- O **Regulamento de Comunicação de Incidente de Segurança** (Resolução CD/ANPD nº 15/2024) define como e quando fazer essa comunicação. Segundo as fontes consultadas:
  - o prazo para comunicar a ANPD é de **3 dias úteis**, contados a partir do momento em que o controlador **toma conhecimento de que o incidente afetou dados pessoais**;
  - se a informação ainda estiver incompleta, é possível enviar uma **comunicação preliminar** e complementá-la em até **20 dias úteis**;
  - a comunicação aos titulares deve ocorrer **sem demora injustificada**;
  - incidentes que **não** precisam ser comunicados devem, ainda assim, ser **registrados internamente**, com a análise de risco e a conclusão.
- Agentes de tratamento de pequeno porte contam com **prazos em dobro** em certas obrigações (Resolução CD/ANPD nº 2/2022). Confirme se a sua empresa se enquadra.

> **Atenção:** prazos e critérios podem ser atualizados e têm exceções. Leia o texto vigente das resoluções no site da ANPD e consulte orientação jurídica ao tratar de um incidente real. O prazo de guarda do registro interno de incidentes também deve ser conferido na resolução.

## O que é um incidente

Qualquer evento que comprometa a **confidencialidade, a integridade ou a disponibilidade** de dados pessoais:

- Acesso não autorizado (conta invadida, invasão do sistema)
- Vazamento ou exposição (planilha pública, banco sem senha, e-mail enviado ao destinatário errado)
- Perda ou roubo de equipamento ou mídia com dados
- Ransomware ou destruição de dados
- Alteração indevida de dados

## O que isso significa na prática

### 1. Prepare antes (agora, antes de qualquer incidente)

- Defina **quem coordena** a resposta e quem o substitui
- Tenha uma lista de **contatos de emergência**: TI, jurídico ou consultor, encarregado (se houver), fornecedor de hospedagem, seguradora
- Saiba **onde estão os logs** e os backups (capítulos 4 e 5)
- Tenha este plano **impresso ou fora do sistema principal**: se o ambiente cair, ele precisa continuar acessível

### 2. As quatro fases da resposta

**Fase 1: contenção (primeiras horas)**
- Isole o que foi afetado: desconecte o equipamento da rede, bloqueie a conta, revogue a chave ou o token exposto
- **Não desligue nem apague nada** que possa servir de evidência: preserve logs, e-mails e imagens do equipamento
- Troque as senhas das contas envolvidas e de contas privilegiadas
- Registre hora e fato de cada ação tomada

**Fase 2: avaliação (primeiro dia)**
- O que aconteceu e quando foi descoberto? (a data de ciência é a que conta para o prazo)
- Quais **sistemas** e quais **categorias de dados** foram atingidos? Há dados sensíveis, de crianças ou financeiros?
- Quantos **titulares** foram afetados, e quão fácil é identificá-los?
- Qual o **risco** para essas pessoas: fraude, discriminação, exposição, dano financeiro?
- Os dados estavam criptografados? A chave também foi exposta? (capítulo 3)

**Fase 3: comunicação (até o prazo)**
- Decida, com apoio jurídico, se o incidente **pode acarretar risco ou dano relevante**
- Se sim, comunique a **ANPD** pelo formulário eletrônico dentro do prazo, mesmo que com informações preliminares
- Comunique os **titulares** de forma clara: o que aconteceu, quais dados, quais riscos, o que a empresa fez e o que a pessoa pode fazer para se proteger
- Se **não** comunicar, **registre a justificativa** por escrito

**Fase 4: recuperação e aprendizado**
- Restaure a partir de backup limpo e confirme que a falha foi corrigida, para não ser explorada de novo
- Faça uma revisão pós-incidente: causa raiz, o que funcionou, o que faltou
- Transforme cada falha em uma ação concreta (um acesso a revogar, um alerta a criar, um treinamento)

### 3. Conteúdo da comunicação à ANPD

Tenha estas informações em mãos (pode enviar uma versão preliminar e completar depois):

- Identificação da empresa e do responsável pelo contato (e do encarregado, se houver)
- Data e hora em que o incidente ocorreu (se souber) e em que foi descoberto
- Descrição do que aconteceu e, se conhecida, a causa provável
- Sistemas afetados e categorias de dados envolvidas
- Número estimado de titulares e o perfil deles
- Medidas de contenção e prevenção adotadas
- Se os titulares já foram avisados e, se não, por quê

### 4. Ficha de registro do incidente (modelo)

| Campo | Preenchimento |
|---|---|
| Número / data de registro | |
| Quem descobriu e quando | |
| Descrição do incidente | |
| Sistemas e dados afetados | |
| Quantidade e perfil dos titulares | |
| Risco avaliado | Baixo / Médio / Alto, com justificativa |
| Medidas de contenção | |
| Comunicado à ANPD? | Sim (data) / Não (justificativa) |
| Comunicado aos titulares? | Sim (data e forma) / Não (justificativa) |
| Causa raiz e ações corretivas | |
| Responsável e prazo | |

## Checklist

- [ ] Há uma pessoa responsável por coordenar incidentes, com substituto definido
- [ ] A lista de contatos de emergência está pronta e acessível fora do sistema principal
- [ ] Todos sabem a quem avisar imediatamente se suspeitarem de um incidente
- [ ] Existe um procedimento de contenção (isolar, bloquear, trocar credenciais, preservar evidências)
- [ ] A empresa sabe quais dados trata e onde, para avaliar rápido o que foi atingido (capítulo 1)
- [ ] O modelo de comunicação à ANPD e aos titulares está pronto
- [ ] Os prazos de comunicação aplicáveis foram conferidos na resolução vigente
- [ ] Existe um registro de incidentes, inclusive os que não foram comunicados
- [ ] O plano é testado ao menos uma vez por ano com um simulado simples
- [ ] Cada incidente termina com uma revisão e ações corretivas

## Erros comuns em empresas pequenas

- **Esconder ou demorar.** O prazo corre desde que a empresa sabe do incidente. Demorar para decidir quem avisa pesa contra, além de ampliar o dano.
- **Apagar tudo e reinstalar na pressa**, destruindo as evidências e a chance de saber o que foi exposto.
- **Descobrir pelo cliente ou pela imprensa.** Sem monitoramento (capítulo 4), a empresa é a última a saber.
- **Não registrar os incidentes menores.** A lei pede registro até daquilo que não foi comunicado, e a justificativa precisa existir por escrito.
- **Não ter plano e improvisar na crise**, sem saber quem decide, quem fala com o cliente e quem fala com a ANPD.
- **Culpar a pessoa** que errou e criar medo de reportar. Se avisar é punido, os próximos incidentes só serão descobertos tarde.

## Próximo capítulo

O capítulo 07 trata dos **direitos do titular**: o que fazer quando um cliente pede acesso, correção ou eliminação dos próprios dados.