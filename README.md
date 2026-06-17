# MovieLib

MovieLib é um pequeno app React de catálogo de filmes criado com Vite. A aplicação consome uma API de filmes para exibir:

- filmes mais bem avaliados
- busca por títulos
- página de detalhes com orçamento, receita, duração e resumo
- navegação com React Router
- cards de filme com imagem, título e nota

## Tecnologias

- React 18
- Vite
- React Router DOM
- React Icons
- JavaScript moderno

## Estrutura principal

- `src/main.jsx` - configura o React e as rotas
- `src/App.jsx` - layout principal e `<Outlet />`
- `src/components/NavBar.jsx` - barra de navegação e busca
- `src/components/MovieCard.jsx` - card de filme reutilizável
- `src/pages/Home.jsx` - página inicial de filmes top rated
- `src/pages/Search.jsx` - pagina de resultados de busca
- `src/pages/Movie.jsx` - página de detalhes do filme

## Funcionalidades

- `Home` exibe filmes mais bem avaliados carregados da API
- `Search` consulta filmes por título usando query string `?q=`
- `Movie` mostra detalhes completos de um filme selecionado
- o campo de busca navega para `/search?q=...`
- o link de detalhe vai para `/movie/:id`

## Variáveis de ambiente

O projeto usa variáveis de ambiente Vite para configurar a API e imagens. Crie um arquivo `.env` na raiz com as chaves abaixo:

```env
VITE_API=https://api.themoviedb.org/3/movie/
VITE_SEARCH=https://api.themoviedb.org/3/search/movie
VITE_API_KEY=api_key=SEU_TOKEN_AQUI
VITE_IMG=https://image.tmdb.org/t/p/w500
```

> Ajuste o valor de `VITE_API_KEY` para a sua chave da API.

## Como executar

1. Instale as dependências:

```bash
npm install
```

2. Rode o servidor de desenvolvimento:

```bash
npm run dev
```

3. Abra o endereço exibido no terminal (normalmente `http://localhost:5173`).

## Build para produção

```bash
npm run build
```

Para pré-visualizar o build:

```bash
npm run preview
```

## Scripts disponíveis

- `npm run dev` - inicia o servidor de desenvolvimento
- `npm run build` - gera o build de produção
- `npm run preview` - pré-visualiza o build
- `npm run lint` - verifica o código com ESLint

## Observações

- O app espera que a API de filmes retorne o campo `poster_path` para as imagens.
- Caso não exista uma chave de API válida, a página não exibirá resultados corretamente.
- A navegação principal usa `BrowserRouter` com rotas para `/`, `/search` e `/movie/:id`.

## Melhorias sugeridas

- adicionar tratamento de erro ao `fetch`
- incluir loading state nas páginas de detalhes
- habilitar paginação nos resultados de busca
- melhorar a acessibilidade e responsividade dos cards
