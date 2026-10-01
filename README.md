# ÓRBITA API - Swagger/OpenAPI

Documentação estática da API do projeto ÓRBITA.

## Estrutura

```text
orbita-swagger/
├── index.html
├── openapi_orbita.yaml
├── .nojekyll
└── README.md
```

Não há backend, banco de dados ou dependências de build. O `index.html` usa Swagger UI via CDN e carrega o contrato `openapi_orbita.yaml`.

## Executar localmente

Abrir `index.html` diretamente pode ser bloqueado pelo navegador ao tentar carregar o YAML por `file://`.
Por isso, use um servidor HTTP simples.

### Python

```bash
cd orbita-swagger
python3 -m http.server 8080
```

Acesse:

```text
http://localhost:8080
```

### Node.js

```bash
npx serve .
```


## Observação

O Swagger UI apresentado aqui é somente documentação do contrato. Como nenhum backend está incluído,
as chamadas em **Try it out** não funcionarão até que um servidor real implemente os endpoints.
