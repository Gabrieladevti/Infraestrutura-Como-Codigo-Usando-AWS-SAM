# Infraestrutura-Como-Codígo-Usando-AWS-SAM

## Introdução
Este laboratório explora o AWS Serverless Application Model (SAM), um framework para desenvolvimento de aplicações serverless na nuvem da AWS. O AWS SAM simplifica a definição e implantação de recursos serverless, como AWS Lambda, API Gateway, DynamoDB, entre outros.

## Pré-requisitos
Antes de iniciar, certifique-se de ter os seguintes requisitos instalados:
- AWS CLI configurada
- AWS SAM CLI
- Docker (para testes locais)

## Instalação do AWS SAM CLI
Caso ainda não tenha instalado, siga as instruções oficiais:
```sh
curl -Lo aws-sam-cli.zip https://github.com/aws/aws-sam-cli/releases/latest/download/aws-sam-cli-linux-x86_64.zip
unzip aws-sam-cli.zip -d sam-installation
sudo ./sam-installation/install
sam --version
```

## Criando um Novo Projeto SAM
Para criar uma nova aplicação serverless com o AWS SAM:
```sh
sam init
```
Siga os prompts para escolher o template e linguagem desejados.

## Estrutura do Projeto
Após a inicialização, o projeto terá a seguinte estrutura:
```
my-sam-app/
│   README.md
│   template.yaml  # Definição da infraestrutura
└───hello-world/
    │   app.py  # Código da função Lambda
    │   requirements.txt  # Dependências
```

## Construção e Deploy
### Teste Local
Para testar a função Lambda localmente:
```sh
sam build
sam local invoke "HelloWorldFunction"
```

### Deploy para AWS
Para implantar a aplicação na AWS:
```sh
sam deploy --guided
```
Isso configurará automaticamente os recursos necessários na AWS.

## Removendo a Aplicação
Caso deseje remover a aplicação da AWS:
```sh
aws cloudformation delete-stack --stack-name my-sam-app
```

## Conclusão
Este laboratório abordou a configuração e o uso do AWS SAM para desenvolver e implantar aplicações serverless. Explore mais funcionalidades no [AWS SAM Documentation](https://docs.aws.amazon.com/serverless-application-model/).




