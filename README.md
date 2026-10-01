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

## Hospedar no GitHub Pages

1. Crie um repositório, por exemplo `orbita-api-docs`.
2. Envie os quatro arquivos deste diretório para a branch `main`.
3. No GitHub, abra **Settings > Pages**.
4. Em **Build and deployment**, escolha **Deploy from a branch**.
5. Selecione `main` e `/ (root)`.
6. Salve.
7. O GitHub publicará a documentação em uma URL no domínio `github.io`.

O arquivo `.nojekyll` evita processamento desnecessário pelo Jekyll.

## Hospedar no Netlify

A forma mais simples é utilizar o deploy manual:

1. Entre no Netlify.
2. Crie um novo projeto por deploy manual/drag-and-drop.
3. Arraste a pasta `orbita-swagger`.
4. O site será publicado em uma URL `*.netlify.app`.

## Backend futuro

Quando o backend existir, altere a seção `servers` de `openapi_orbita.yaml`:

```yaml
servers:
  - url: https://api.seudominio.com
    description: Produção
```

O botão **Try it out** passará a chamar esse endereço.

## Observação

O Swagger UI apresentado aqui é somente documentação do contrato. Como nenhum backend está incluído,
as chamadas em **Try it out** não funcionarão até que um servidor real implemente os endpoints.
