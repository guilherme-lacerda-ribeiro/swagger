# Swagger
[Swagger Site Oficial](https://swagger.io/).

Ferramenta utilitária para APIs.
Possui em Tools as OpenSources e as Pro (pagas).

## Tools Open Sources
- [Editor](https://editor.swagger.io/)
- [Editor Novo](https://editor-next.swagger.io/)
- [UI](https://petstore.swagger.io/)
- [Codegen](https://swagger.io/tools/swagger-codegen/)

## Ferramentas extras
- [MockAPI](https://mockapi.io/)
Quickly setup endpoints, generate custom data, and perform operations on it using RESTful interface

## Especificação de API (OAS)
- https://swagger.io/specification/v3/
- Oficial: https://www.openapis.org/ (https://spec.openapis.org/oas/v3.1.0)

## Editor
Permite edição em JSON e YAML (\`iêmal\`).
À medida que vai escrevendo ele vai dando "errors" do que é obrigatório na especificação para corrigirmos (incluirmos na configuração).

Os endpoints da API são chamados de _paths_.
Os arquivos `yml` do projeto podem ser inseridos diretamente no editor do swagger online para teste.

## Trechos destacados da documentação
- [Data types](https://swagger.io/specification/#data-types)
- [Components Examples](https://swagger.io/specification/#components-object-example)

## Autenticação
- [Youtube - Autenticação por Token](https://www.youtube.com/watch?v=MZetkcs2xIo)
- [Youtube - Autenticação com JWT](https://www.youtube.com/watch?v=B-7e-ZpIWAs)

## Offline Swagger Editor
Pode baixar o projeto todo do github e subir como um servidor web. Ou pode subir via docke com a documentação no [próprio site](https://github.com/swagger-api/swagger-editor).
```sh
docker pull docker.swagger.io/swaggerapi/swagger-editor
docker run -d -p 80:8080 docker.swagger.io/swaggerapi/swagger-editor
(...)
```
Observação: por ser um projeto web, toda alteração que for realizada no arquivo precisa baixar novamente (file -> save) o arquivo yml que foi gerado.

## Swagger UI
Disponibilizar a documentação gerada ao cliente. Documentação no [próprio site](https://github.com/swagger-api/swagger-ui). Link direto pra [instalação em docker](https://github.com/swagger-api/swagger-ui/blob/HEAD/docs/usage/installation.md#docker).

```sh
# mapeia meu diretorio atual para o /tmp do servidor, ou seja, /tmp/openapi.json é meu diretório atual ./openapi.json
docker run -p 80:8080 -e SWAGGER_JSON=/tmp/openapi.json -v $(pwd):/tmp docker.swagger.io/swaggerapi/swagger-ui

# ou detached
docker run -d -p 80:8080 -e SWAGGER_JSON=/tmp/openapi.json -v $(pwd):/tmp docker.swagger.io/swaggerapi/swagger-ui
```

## Generate server / client
No editor é possível gerar o código através do menu próprio.
