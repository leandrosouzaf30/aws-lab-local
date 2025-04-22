# AWS Local Development Environment

Este projeto fornece um ambiente de desenvolvimento local para serviços AWS utilizando LocalStack. Ele permite que você desenvolva e teste aplicações que utilizam serviços AWS como SQS e SNS em um ambiente local, sem necessidade de credenciais AWS reais.

## 🚀 Funcionalidades

- Ambiente local AWS usando LocalStack
- Configuração automática de serviços AWS:
  - Amazon SQS (Simple Queue Service)
  - Amazon SNS (Simple Notification Service)
- Scripts de automação para setup do ambiente
- Exemplos de infraestrutura como código usando:
  - Terraform
  - CloudFormation

## 📋 Pré-requisitos

- Docker
- AWS CLI
- LocalStack
- Terraform (opcional, para exemplos de IaC)

## 🛠️ Instalação

1. Clone este repositório:
```bash
git clone [URL_DO_REPOSITÓRIO]
cd [NOME_DO_DIRETÓRIO]
```

2. Configure o LocalStack Cloud - https://app.localstack.cloud/getting-started:
```bash
# Configure seu token de autenticação pessoal
export LOCALSTACK_AUTH_TOKEN="SEU TOCKER"

# Configure as variáveis de ambiente para teste
export AWS_ACCESS_KEY_ID="test"
export AWS_SECRET_ACCESS_KEY="test"
export AWS_DEFAULT_REGION="us-east-1"
```

3. Execute o script de setup:
```bash
chmod +x setup.sh
./setup.sh
```

## 🔧 Configuração

O script `setup.sh` realiza as seguintes configurações:
- Cria uma fila SQS chamada `minha-fila`
- Cria um tópico SNS chamado `meu-topico`
- Configura a integração entre SQS e SNS
- Verifica as configurações realizadas

## 📁 Estrutura do Projeto

```
.
├── aws-lab-local/           # Diretório principal do projeto
│   ├── cloudformation/      # Templates CloudFormation
│   ├── terraform/          # Configurações Terraform
│   └── localstack/         # Configurações LocalStack
├── localstack/             # Configurações adicionais LocalStack
└── setup.sh               # Script de configuração inicial
```

## 🔍 Como Usar

1. Certifique-se que o LocalStack está rodando:
```bash
docker ps
```

2. Execute o script de setup para criar os recursos:
```bash
./setup.sh
```

3. Verifique os recursos criados:
```bash
# Listar filas SQS
aws --endpoint-url=http://localhost:4566 sqs list-queues

# Listar tópicos SNS
aws --endpoint-url=http://localhost:4566 sns list-topics
```

## 🤝 Contribuindo

Contribuições são bem-vindas! Por favor, sinta-se à vontade para submeter um Pull Request.

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes. 