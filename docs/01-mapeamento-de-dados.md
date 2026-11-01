$conteudo = @'
# 01. Mapeamento de dados

Você não protege o que não sabe que tem. O mapeamento é o inventário de **quais dados pessoais a empresa trata, para quê, onde ficam, com quem são compartilhados e por quanto tempo**. Todos os outros capítulos dependem dele.

## O que a lei pede

- **Dado pessoal** é qualquer informação relacionada a pessoa natural identificada ou identificável (LGPD, art. 5º, I). **Dado pessoal sensível** inclui saúde, origem racial ou étnica, convicção religiosa, opinião política, biometria e dado genético (art. 5º, II).
- O **controlador** deve manter registro das operações de tratamento (art. 37).
- Todo tratamento precisa de uma **finalidade** e de uma **base legal** (arts. 7º e 11).
- Princípios como **necessidade** e **adequação** (art. 6º) mandam coletar só o que for preciso.

> Agentes de tratamento de pequeno porte podem ter regras simplificadas, como a dispensa de indicar encarregado em certos casos (Resolução CD/ANPD nº 2/2022). Verifique se sua empresa se enquadra e se há tratamento de alto risco, que afasta a flexibilização.

## O que isso significa na prática

Para cada tipo de dado, responda sete perguntas:

1. **Quais dados?** (nome, CPF, e-mail, endereço, dados de saúde, fotos...)
2. **De quem?** (clientes, alunos, pacientes, funcionários, visitantes do site)
3. **Para quê?** (finalidade: emitir nota fiscal, agendar consulta, enviar newsletter)
4. **Com que base legal?** (consentimento, contrato, obrigação legal, legítimo interesse...)
5. **Onde fica?** (planilha, sistema, e-mail, WhatsApp, papel, nuvem, notebook de funcionário)
6. **Quem acessa e com quem é compartilhado?** (equipe, contador, fornecedor de software, plataforma de e-mail marketing)
7. **Por quanto tempo é guardado e como é descartado?**

### Passo a passo

1. **Liste os processos do negócio** (vendas, atendimento, RH, financeiro, marketing, site) e, em cada um, onde entram dados pessoais.
2. **Liste os sistemas e locais de armazenamento**, inclusive os "informais": planilhas soltas, grupos de WhatsApp, pastas compartilhadas, backups em HD externo.
3. **Preencha o registro** usando o modelo em [`templates/registro-de-tratamento.md`](../templates/registro-de-tratamento.md), uma linha por tratamento.
4. **Destaque os dados sensíveis** e os de crianças e adolescentes: eles exigem cuidado reforçado.
5. **Liste os fornecedores** que recebem dados (hospedagem, e-mail, CRM, contabilidade) e confirme se há contrato ou termo cobrindo proteção de dados.
6. **Marque o que não precisa ser coletado ou guardado.** Eliminar dado desnecessário é a medida de segurança mais barata que existe.

## Checklist

- [ ] Todos os processos que usam dados pessoais foram listados
- [ ] Todos os locais de armazenamento foram identificados, inclusive os informais
- [ ] Cada tratamento tem finalidade e base legal registradas
- [ ] Dados sensíveis e de menores estão destacados
- [ ] Fornecedores com acesso a dados estão listados, com contato e contrato
- [ ] Há prazo de retenção definido para cada categoria
- [ ] Dados desnecessários foram identificados para eliminação
- [ ] O registro tem um responsável e uma data de revisão

## Erros comuns em empresas pequenas

- **Esquecer os canais informais.** Dados de clientes em WhatsApp pessoal e planilhas no e-mail são a maior fonte de vazamento.
- **Coletar "por precaução".** Pedir CPF, endereço e data de nascimento num cadastro que só precisa de e-mail aumenta o risco sem benefício.
- **Não registrar a base legal.** Dizer "consentimento" para tudo, inclusive onde cabe contrato ou obrigação legal, enfraquece a defesa da empresa.
- **Registro feito uma vez e esquecido.** Sistema novo ou fornecedor novo muda o mapa: revise a cada mudança.
- **Ignorar fornecedores.** Se o dado está na ferramenta de e-mail marketing, ele faz parte do seu mapa.

## Próximo capítulo

Com o mapa pronto, o capítulo 02 trata de **quem pode acessar o quê**.
'@
[System.IO.File]::WriteAllText("$PWD\docs\01-mapeamento-de-dados.md", $conteudo, (New-Object System.Text.UTF8Encoding($false)))