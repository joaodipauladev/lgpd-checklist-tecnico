# 05. Backup e retenção

Esse capítulo trata de duas perguntas que parecem opostas e se complementam: **como não perder o dado** (backup) e **por quanto tempo guardá-lo** (retenção). A LGPD cobra as duas: disponibilidade e integridade de um lado, e não guardar dado pessoal por mais tempo que o necessário do outro.

## O que a lei pede

- Os dados devem ser protegidos contra **perda, destruição e alteração** (LGPD, art. 46), o que inclui ter cópias que permitam recuperar o dado.
- Pelo princípio da **necessidade** (art. 6º, III), o tratamento deve se limitar ao mínimo necessário, e isso vale também para o **tempo**.
- Quando a finalidade termina, o dado deve ser **eliminado** (arts. 15 e 16). A lei permite conservá-lo em situações específicas, como o **cumprimento de obrigação legal ou regulatória** pelo controlador.
- O titular pode pedir a eliminação de dados tratados com base no seu consentimento (art. 18, VI). O capítulo 7 trata disso, e backup é o ponto que mais gera dúvida nesse pedido (veja abaixo).

Prazos obrigatórios variam por área: documentos fiscais, trabalhistas e prontuários de saúde, por exemplo, têm regras próprias. Confirme os prazos da sua atividade antes de definir a retenção.

## O que isso significa na prática

### Backup

#### 1. A regra 3-2-1

- **3** cópias do dado (a original e duas de backup)
- em **2** tipos diferentes de mídia ou local
- com **1** cópia fora do local principal (nuvem ou outro endereço)

Para se proteger de ransomware, pelo menos uma cópia deve ficar **desconectada ou imutável**: um backup que está sempre ligado à rede é criptografado junto com o resto pelo atacante.

#### 2. Backup é dado pessoal também

Todo cuidado dos capítulos anteriores vale aqui: o backup deve ser **criptografado** (capítulo 3), ter **acesso restrito** (capítulo 2) e entrar no **registro de tratamento** (capítulo 1). Backup esquecido numa gaveta, sem senha, é um vazamento esperando acontecer.

#### 3. Teste a restauração

Backup que nunca foi restaurado é uma suposição. Pelo menos uma vez por semestre, restaure uma cópia de verdade num ambiente de teste e confira se os dados estão completos e legíveis.

#### 4. Defina metas de recuperação

- **RPO**: quanto dado a empresa aceita perder (backup diário significa até 24 horas de perda)
- **RTO**: quanto tempo a empresa aceita ficar fora do ar até restaurar

Essas duas respostas definem a frequência e o tipo de backup, e evitam descobrir o limite no meio de uma crise.

### Retenção

#### 1. Defina um prazo para cada categoria de dado

Use o [registro de tratamento](../templates/registro-de-tratamento.md) do capítulo 1: a coluna **Retenção** deve estar preenchida para todo tratamento. Um modelo:

| Dado | Motivo de guardar | Prazo | O que fazer depois |
|---|---|---|---|
| Cadastro de cliente ativo | Execução do contrato | Enquanto durar a relação | Manter |
| Cadastro de cliente inativo | Possível reclamação | Prazo de prescrição aplicável | Eliminar ou anonimizar |
| Notas fiscais e documentos contábeis | Obrigação legal | Prazo fiscal vigente | Eliminar ao fim do prazo |
| Currículos de candidatos não contratados | Processo seletivo | Curto (por exemplo, 6 a 12 meses) | Eliminar |
| Logs de segurança | Segurança e evidência | 6 a 12 meses (ver capítulo 4) | Eliminar |

#### 2. Elimine de verdade

Ao fim do prazo, o dado precisa ser **apagado ou anonimizado** em todos os lugares: sistema, planilhas, e-mails e backups. Apagar do sistema principal e deixar nos arquivos antigos não cumpre a retenção.

#### 3. Backup e pedido de eliminação

Um pedido de eliminação costuma esbarrar na pergunta: "e o backup?". Uma abordagem comum e defensável é eliminar o dado dos sistemas ativos imediatamente e deixá-lo **sair dos backups pelo ciclo normal de rotação** (por exemplo, em 30 a 90 dias), com um procedimento que garanta que ele **não seja restaurado** para uso. Documente essa regra e informe o prazo ao titular. Para casos específicos, consulte orientação jurídica.

## Checklist

- [ ] Existe backup automático de todos os sistemas e arquivos com dados pessoais
- [ ] A regra 3-2-1 é seguida, com pelo menos uma cópia fora do local e uma isolada ou imutável
- [ ] Os backups são criptografados e o acesso a eles é restrito
- [ ] Uma restauração de teste foi feita nos últimos 6 meses
- [ ] RPO e RTO estão definidos e são compatíveis com a frequência dos backups
- [ ] Cada categoria de dado tem prazo de retenção e motivo registrados
- [ ] Os prazos legais obrigatórios da sua atividade foram verificados
- [ ] Existe rotina para eliminar ou anonimizar dados vencidos, inclusive em planilhas e e-mails
- [ ] Há uma regra documentada para backups em pedidos de eliminação
- [ ] Mídias antigas (HDs, pendrives, computadores) são destruídas ou apagadas com segurança antes do descarte

## Erros comuns em empresas pequenas

- **Backup no mesmo computador ou na mesma rede**, que o ransomware ou um incêndio atinge junto.
- **Nunca testar a restauração.** Muita empresa descobre que o backup não funciona só quando precisa dele.
- **Guardar tudo para sempre "por precaução".** Dado sem finalidade é risco sem benefício e contraria o princípio da necessidade.
- **Backup sem criptografia** levado para casa ou esquecido em escritório.
- **Descartar computador ou HD velho sem apagar de verdade.** Formatar não basta para dados sensíveis.
- **Eliminar do sistema e esquecer o resto**: planilhas exportadas, e-mails antigos e pastas na nuvem continuam com o dado.

## Próximo capítulo

O capítulo 06 trata de **resposta a incidentes**: o que fazer nas primeiras horas quando algo dá errado, inclusive o prazo de comunicação à ANPD.