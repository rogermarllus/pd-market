# PD Market (Projeto de Promoções)

[![Deploy with Vercel](https://vercel.com/button)](https://pd-market.vercel.app/)

Projeto desenvolvido como atividade prática, focado na criação de uma página de promoções estática utilizando **HTML5 semântico e CSS3**, com a restrição de **não utilizar JavaScript** para nenhuma funcionalidade interativa.

**Acesse a página publicada:** [https://pd-market.vercel.app/](https://pd-market.vercel.app/)

---

## 1. Introdução

O objetivo deste projeto foi criar uma página de promoções para o PD Market. Os principais desafios foram:

1.  Implementar um **carrossel de banners 100% funcional (com autoplay e navegação) apenas com HTML e CSS**.
2.  Implementar um **modal de "Ver detalhes" 100% funcional apenas com HTML e CSS**.
3.  Utilizar de forma rigorosa um conjunto de **83 tags HTML obrigatórias**, comentando o propósito de cada uma na sua primeira aparição no código (`index.html`).
4.  Seguir um fluxo de trabalho profissional com Git, utilizando _feature branches_ e _Conventional Commits_.

## 2. Tecnologias Utilizadas

- **HTML5 (Semântico):** O projeto utiliza um conjunto rigoroso de 83 tags HTML obrigatórias (de `<!DOCTYPE html>` a `<a>`), incluindo tags estruturais (`<main>`, `<article>`, `<aside>`), de mídia (`<video>`, `<picture>`), de tabela (`<table>`, `<tbody>`), de formulário (`<fieldset>`, `<datalist>`) e semânticas (`<time>`, `<meter>`), para garantir a máxima acessibilidade e estrutura correta.
- **CSS3:** Utilizado para toda a estilização, layout (CSS Grid, Flexbox), animações (`@keyframes`) e interatividade (seletores de pseudo-classe como `:checked`, `~` e `+`).
- **Proibição de JavaScript:** Conforme o requisito principal, **nenhum arquivo `.js` ou tag `<script>` com lógica funcional foi utilizado** para os componentes interativos.

---

## 3. Funcionalidades Implementadas

### 🔹 Carrossel de Banners (100% CSS)

- **Autoplay:** O carrossel avança automaticamente os 4 slides usando animações `@keyframes`.
- **Navegação Manual:** O usuário pode navegar clicando nos "dots" (pontos de navegação).
- **Pausa no Hover:** A animação de autoplay é pausada quando o mouse está sobre o carrossel, melhorando a usabilidade.
- **Acessibilidade:** Totalmente navegável pelo teclado (usando `Tab` para focar nos `labels` dos inputs de rádio).

### 🔹 Grade de Produtos e Filtro

- Exibição de **30 produtos** em um layout de grade responsivo.
- Cada "card" de produto inclui imagem, nome, preço antigo (`<small>`), preço promocional (`<strong>`) e uma etiqueta de oferta (`<mark>`).
- Inclusão de um filtro visual de categorias (HTML/CSS).

### 🔹 Modal de Detalhes (100% CSS)

- Ao clicar em "Ver detalhes" em um produto, um modal é exibido.
- Esta funcionalidade foi implementada usando a técnica de _checkbox hack_ (um `<input type="checkbox">` oculto que, ao ser marcado pelo `<label>`, exibe o modal através de seletores CSS).

### 🔹 HTML Semântico e Acessibilidade

- **83 Tags Obrigatórias:** O código-fonte (`index.html`) atende ao requisito de usar todas as 83 tags especificadas. Cada tag possui um comentário em sua primeira aparição explicando sua finalidade.
- **Acessibilidade:** Foram aplicados textos alternativos (`alt`) em todas as imagens, `aria-label` nos controles do carrossel e foi mantido um bom contraste de cores.

### 🔹 Fluxo de Trabalho Git

- O projeto seguiu um fluxo com _feature branches_ (ex: `feature-header`, `feature-banner`, `feature-products`).
- Foram realizados mais de 8 commits seguindo o padrão **Conventional Commits** (ex: `feat:`, `style:`, `docs:`, `fix:`).

---

## 4. Decisões de Design e Estrutura

### Paleta de Cores e Estética

Optei por um **tema escuro (dark mode)** para um visual mais moderno e que destaca melhor as imagens dos produtos.

- **Fundo Principal:** `darkslateblue`
- **Texto Principal:** `#eee` (branco suave)
- **Destaques (Links/Botões):** `darkcyan` e `lightblue`
- **Cards de Produto:** Fundo branco (`#fff`) para criar contraste com a página e destacar as ofertas.

### Interatividade sem JS

Todo o dinamismo da página foi construído sobrepondo "estados" do CSS, sem manipulação de DOM.

- **Carrossel:** A lógica é controlada por 4 inputs de rádio (`<input type="radio">`) ocultos. Clicar nos `labels` (os "dots") marca o input correspondente, que por sua vez aciona uma regra CSS (`#slide1:checked ~ .slides-container`) para mover o contêiner dos slides usando `transform: translateX()`. O autoplay é uma animação CSS (`@keyframes`) que é pausada no `:hover` e interrompida se o usuário interagir manualmente.

- **Modal:** Utiliza um único `<input type="checkbox">` oculto. O botão "Ver detalhes" é um `<label>` que marca esse checkbox. Quando o checkbox está `:checked`, o modal (que é um irmão do checkbox) muda de `display: none` para `display: flex`.

---

## 5. Como Visualizar o Projeto

### Deploy (Vercel)

O projeto está publicado e pode ser acessado diretamente através do link:

**[https://pd-market.vercel.app/](https://pd-market.vercel.app/)**


### Localmente

Para rodar este projeto localmente, basta clonar o repositório e abrir o arquivo `index.html` no seu navegador de preferência.

```bash
# 1. Clone o repositório
git clone https://github.com/rogermarllus/pd-market.git

# 2. Navegue até a pasta do projeto
cd pd-market

# 3. Abra o arquivo index.html
# (Você pode fazer isso clicando duas vezes no arquivo
# ou usando uma extensão como o "Live Server" no VS Code)
```
