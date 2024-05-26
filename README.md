# Uber Code Challenge

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=for-the-badge)

## Descrição

Este projeto é um desafio de codificação simples com o objetivo de estudos. Ele consiste em um serviço de envio de e-mails construído com Java e Spring Boot. O serviço expõe uma API REST para enviar e-mails, utilizando uma interface de gateway para abstrair a lógica de envio.

## Tecnologias Utilizadas

- **Linguagem:** Java
- **Framework:** Spring Boot
- **Outros:** AWS (para gestão de credenciais)

## Pré-requisitos

- Java 11 ou superior
- Maven
- Conta AWS para obter `accessKeyId` e `secretKey`

## Instruções de Instalação

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/uber-code-challenge.git
   cd uber-code-challenge
   ```

2.Configure suas credenciais AWS no arquivo application.properties
 ```bash
spring.application.name=Uber Code Challenge
aws.region=us-east-1
aws.accessKeyId=SUA_CHAVE
aws.secretKey=SUA-SECRET
```

3.Compile e execute o projeto:
```bash
mvn clean install
mvn spring-boot:run
```

## Como Utilizar
### Enviar E-mail
Para enviar um e-mail, faça uma requisição POST para o endpoint /api/email com um JSON no corpo da requisição, conforme o exemplo abaixo:
Requisição
```bash
POST /api/email HTTP/1.1
Host: localhost:8080
Content-Type: application/json

{
  "to": "exemplo@dominio.com",
  "subject": "Assunto do E-mail",
  "body": "Corpo do e-mail"
}
```

Exemplo de Curl
```bash
curl -X POST http://localhost:8080/api/email \
    -H 'Content-Type: application/json' \
    -d '{
          "to": "exemplo@dominio.com",
          "subject": "Assunto do E-mail",
          "body": "Corpo do e-mail"
        }'
```

Resposta de Sucesso
```bash
{
  "message": "Email send successfully"
}
```

Resposta de Erro
```bash
{
  "message": "Error while sending e-mail"
}
```

## Estrutura do Projeto
EmailSenderGateway: Interface que define o contrato para envio de e-mails.<br>
EmailSenderService: Implementação do caso de uso para envio de e-mails.<br>
EmailSenderController: Controlador REST que expõe a API para envio de e-mails.<br>
EmailRequest: Classe de request para envio de e-mails.<br>
EmailSenderUseCase: Interface de uso para envio de e-mails.<br>
EmailServiceException: Exceção personalizada para erros no envio de e-mails.<br>
UberCodeChallengeApplication: Classe principal para iniciar a aplicação Spring Boot.<br>

## Contribuições
Contribuições são bem-vindas! Sinta-se à vontade para abrir issues e enviar pull requests.
