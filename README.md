# gc-github-actions

[![Primeiro Workflow](https://github.com/cVitorAndrade/gc-github-actions/actions/workflows/primeiro-workflow.yml/badge.svg)](https://github.com/cVitorAndrade/gc-github-actions/actions/workflows/primeiro-workflow.yml)

Meu primeiro workflow com **GitHub Actions**: uma pipeline mínima que roda automaticamente a cada `push`, sem nenhuma aplicação por trás. O objetivo é praticar o básico: gatilho, runner, actions e comandos.

## Estrutura

```
.
├── .github
│   └── workflows
│       └── primeiro-workflow.yml
└── README.md
```

## O que o workflow faz

O arquivo [`.github/workflows/primeiro-workflow.yml`](.github/workflows/primeiro-workflow.yml) é acionado a cada `push` e executa, em um runner `ubuntu-latest`, as etapas abaixo:

| Etapa                          | Action / comando        | O que faz                                     |
| ------------------------------ | ----------------------- | --------------------------------------------- |
| Baixar o código do repositório | `actions/checkout@v4`   | Baixa o conteúdo do repositório para o runner |
| Configurar o Node.js           | `actions/setup-node@v7` | Instala o Node.js 24                          |
| Mostrar a versão do Node.js    | `node --version`        | Confirma que o Node foi configurado           |
| Listar os arquivos do projeto  | `ls -la`                | Mostra os arquivos baixados pelo checkout     |
| Mensagem final                 | `echo`                  | Imprime `Pipeline executada com sucesso!`     |

## Como validar

1. Faça um commit e um `git push`.
2. Abra a aba **Actions** do repositório: uma execução de **Primeiro Workflow** aparece automaticamente.
3. Entre na execução e confira se todas as etapas ficaram verdes e se os logs mostram o uso das duas actions e a mensagem final.
