Explorando Workflows Automatizados com AWS Step Functions
📌 Descrição do Projeto

Este projeto foi realizado como parte do desafio da DIO para consolidar conhecimentos em AWS Step Functions.
O objetivo foi criar um workflow automatizado simples, documentar o processo e registrar aprendizados adquiridos durante a prática.

O workflow desenvolvido consiste em:

Validar a entrada do usuário via Lambda (ValidateInput)

Tomar decisão com base na validação (Choice)

Processar dados se a entrada for válida (ProcessData)

Finalizar o workflow ou registrar falha em caso de entrada inválida (FailState)

🛠️ Tecnologias Utilizadas

AWS Step Functions – Criação e execução do workflow

AWS Lambda – Funções utilizadas nas tasks

AWS IAM – Permissões e políticas para execução das funções

AWS Console – Monitoramento e testes do workflow

🏗️ Arquitetura do Workflow
Start
 │
 ▼
[ValidateInput] (Lambda)
 │
 ▼
[Choice: IsValid?]
 ├─ True ─> [ProcessData] (Lambda) → Success
 └─ False → [FailState] → Fail

Explicação:

ValidateInput: Função Lambda que valida os dados de entrada

Choice (IsValid?): Estado de decisão que verifica se a entrada é válida

ProcessData: Função Lambda que processa os dados válidos

FailState: Estado de falha caso os dados não sejam válidos

📄 Arquivo JSON do Workflow

O workflow está definido no arquivo state-machine-definition.json, que pode ser importado diretamente no AWS Step Functions.
O JSON contém:

StartAt: Define o estado inicial

States: Lista de estados do workflow (Task, Choice, Fail)

Resource: ARN da função Lambda associada a cada Task

End ou Fail: Indicam a conclusão ou falha do workflow

Exemplo de ARN usado no JSON:

arn:aws:lambda:us-east-1:123456789012:function:validateInput


🧠 Insights e Aprendizados

Aprendi a criar State Machines no AWS Step Functions

Entendi a diferença entre os tipos de estados: Task, Choice e Fail

Compreendi como chamar funções Lambda dentro de um workflow

Percebi a importância de documentar o fluxo para facilitar manutenção e estudo

É possível testar workflows sem criar Lambdas reais, usando dados mock

📂 Estrutura do Repositório
│── README.md
└── state-machine-definition.json


👩‍💻 Autora

Projeto desenvolvido por Amanda Justen — Engenharia de Computação & IA
LinkedIn: linkedin.com/in/amanda-justen-80b17182
