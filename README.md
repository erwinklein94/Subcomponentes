# Controle Visual Rumo Cavan

Site estático para controle visual de estoque e inspeções realizadas dos subcomponentes ferroviários armazenados na Cavan.

## Estrutura

```text
.
├── index.html
├── assets/
│   ├── css/
│   │   └── styles.css
│   └── js/
│       └── app.js
├── data/
│   └── base-data.json
└── .nojekyll
```

## Como publicar no GitHub Pages

1. Crie um repositório no GitHub.
2. Envie todos os arquivos e pastas desta pasta para a raiz do repositório.
3. No GitHub, abra **Settings > Pages**.
4. Em **Build and deployment**, selecione **Deploy from a branch**.
5. Escolha a branch `main` e a pasta `/root`.
6. Salve e aguarde o link do GitHub Pages ficar disponível.

## Como atualizar os dados

O site já carrega a base inicial em `data/base-data.json`.

Para usar uma planilha mais nova, abra a aba **Importar planilha** no próprio site e carregue um arquivo `.xlsx` com abas no mesmo padrão da planilha base:

- Aba de estoque: preferencialmente `Estoque`
- Aba de inspeções realizadas: preferencialmente `Executados`

A importação acontece no navegador. Os dados da planilha não são enviados para servidor.

## Teste local

Como o site carrega `data/base-data.json` via `fetch`, abrir o `index.html` diretamente por `file://` pode bloquear a base inicial em alguns navegadores.

Para testar localmente, use um servidor estático simples, por exemplo:

```bash
python -m http.server 8000
```

Depois abra:

```text
http://localhost:8000
```

Outra opção é usar a extensão **Live Server** no VS Code.
