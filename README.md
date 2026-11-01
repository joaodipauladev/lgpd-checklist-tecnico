$conteudo = @'
# LGPD: checklist técnico para pequenas empresas

Guia prático, escrito do ponto de vista de quem desenvolve e opera sistemas, para colocar a segurança de dados pessoais em dia sem depender de jargão jurídico. Cada capítulo traz o que a lei pede, o que isso significa na prática técnica, um checklist e os erros mais comuns em empresas pequenas.

> **Aviso:** este é um guia técnico e educativo. Ele **não substitui orientação jurídica** nem constitui consultoria legal. Para decisões sobre enquadramento, bases legais e responsabilidades, consulte um profissional de direito digital. Normas mudam: confirme sempre o texto vigente no site da [ANPD](https://www.gov.br/anpd).

## Para quem é

- Donos e responsáveis por pequenas empresas, clínicas, escolas e e-commerces que tratam dados de clientes, pacientes, alunos ou funcionários
- Desenvolvedores e profissionais de TI que precisam traduzir a LGPD em tarefas concretas
- Freelancers e consultores que fazem diagnóstico de segurança para pequenos negócios

## Como usar

1. Leia o capítulo 1 e faça o mapeamento de dados: **todo o resto depende dele**
2. Siga os capítulos na ordem e marque os itens dos checklists
3. Use os modelos da pasta [`templates/`](templates/) como ponto de partida
4. Revise a cada mudança relevante (novo sistema, novo fornecedor, novo tipo de dado)

## Índice

| Capítulo | Tema |
|---|---|
| [01](docs/01-mapeamento-de-dados.md) | Mapeamento de dados: o que você coleta, onde guarda e por quê |
| [02](docs/02-controle-de-acesso.md) | Controle de acesso: quem pode ver e alterar o quê |
| [03](docs/03-criptografia.md) | Criptografia: proteger o dado em trânsito, em repouso e as senhas |
| [04](docs/04-logs-e-monitoramento.md) | Logs e monitoramento: registrar, proteger e vigiar |
| [05](docs/05-backup-e-retencao.md) | Backup e retenção: não perder o dado e não guardar além do necessário |
| 06 | Resposta a incidentes (em breve) |
| 07 | Direitos do titular (em breve) |

## Referências normativas

- [Lei nº 13.709/2018 (LGPD)](https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm)
- Resolução CD/ANPD nº 2/2022: aplicação da LGPD a agentes de tratamento de pequeno porte
- Resolução CD/ANPD nº 15/2024: Regulamento de Comunicação de Incidente de Segurança

## Sobre a origem

O conteúdo parte da experiência prática com tratamento de dados sensíveis em sistemas de gestão. Nenhum dado, cliente ou sistema real é citado neste repositório.

## Contribuindo

Achou um erro ou quer sugerir melhoria? Abra uma *issue* ou um *pull request*.

## Licença

MIT. Veja o arquivo [LICENSE](LICENSE).

Feito por João ([@joaodipauladev](https://github.com/joaodipauladev)).
'@
[System.IO.File]::WriteAllText("$PWD\README.md", $conteudo, (New-Object System.Text.UTF8Encoding($false)))
(Get-Item README.md).Length