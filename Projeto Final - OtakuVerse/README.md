# 🎌 OtakuVerse Collector Hub — E-commerce de Figures & Colecionáveis Oficiais

Projeto completo de **Front-end (Web & Mobile)** que simula uma loja virtual especializada na importação de colecionáveis japoneses originais (*Scale Figures 1/7*, *Nendoroids*, *Wall Scrolls Cyberpunk*, *Streetwear Otaku* e *Mangás/Artbooks*), desenvolvido com foco em **HTML5 Semântico**, **Design System Responsivo (Dark/Light Mode)**, **Componentização** e **Persistência de Dados com `localStorage`**.

---

## 📌 1. Objetivo do Projeto

O **OtakuVerse Collector Hub** foi projetado para demonstrar, na prática, os principais conceitos de um curso de desenvolvimento **Front-end moderno**:

1. **Estruturação Semântica HTML5**: Uso adequado de tags estruturais (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<figure>`, `<figcaption>`, `<address>`, `<footer>`) e atributos de acessibilidade (`aria-label`, `alt`, hierarquia de títulos `h1`–`h4`).
2. **Estilização Avançada e Adaptativa (Web, Tablet e Mobile)**: Layout fluido utilizando **CSS Grid**, **Flexbox**, **Variáveis CSS (Design Tokens)**, **Tailwind CSS v4** e **Media Queries** com menu hambúrguer mobile.
3. **Interatividade Completa de E-commerce**: Busca em tempo real, catálogo com **filtro de preço**, sistema de **Favoritos (♥)**, **Carrinho de Compras** com cálculo de frete/cupom, **Página de Forma de Pagamento** separada e **Sistema de Cadastro, Login e Área de Perfil** funcionando com `localStorage`.
4. **Suporte a Imagens por Links Diretos (URL)**: Todas as imagens utilizam links diretos externos com tratamento automático de fallback (`SafeImage`) caso algum link fique indisponível.

---

## 🛠️ 2. Tecnologias e Ferramentas Utilizadas

| Camada                  | Tecnologia                                      | Onde e Como Foi Utilizada                                                                                                                                             |
| :---------------------- | :---------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Marcação**            | **HTML5 Semântico**                             | Estrutura principal no `index.html` e nos componentes de tela, garantindo semântica, SEO (OpenGraph) e acessibilidade.                                                |
| **Estilização**         | **CSS3 & Tailwind CSS v4**                      | Sistema de cores *Neo-Akiba Vault*, suporte nativo a **Modo Escuro (Dark)** e **Modo Claro (Light)**, animações suaves e responsividade mobile-first.                 |
| **Lógica & UI**         | **JavaScript (ES2022) / TypeScript + React 19** | Controle de estados das telas, filtros combinados do catálogo, gaveta de favoritos, cálculo de carrinho e validação de formulários.                                   |
| **Persistência**        | **Web Storage API (`localStorage`)**            | Armazenamento local no navegador para contas cadastradas, sessão do usuário logado, histórico de pedidos, lista de favoritos e tema.                                  |
| **Tipografia & Ícones** | **Google Fonts & Material Symbols**             | Fontes `Plus Jakarta Sans` (títulos), `Inter` (leitura) e ícones vetoriais `Material Symbols Outlined`.                                                               |
| **Empacotamento**       | **Vite & ESBuild**                              | Compilação do projeto para rodar tanto via **VS Code Live Server** (`index.html` + `style.css` + `script.js`) quanto via servidor de desenvolvimento (`npm run dev`). |

---

## 📂 3. Estrutura de Arquivos do Projeto

O projeto foi organizado para funcionar imediatamente ao abrir o `index.html` no **VS Code (Live Server)**, além de manter todo o código-fonte modularizado na pasta `src/`:

```text
📦 otakuverse-projeto
 ┣ 📄 index.html                  # Entrada principal (HTML5 semântico pré-renderizado + links de estilo e script)
 ┣ 📄 style.css                   # Folha de estilos compilada (Tailwind CSS v4 + variáveis de tema Dark/Light)
 ┣ 📄 script.js                   # Bundle JavaScript completo para execução direta no VS Code Live Server
 ┣ 📄 package.json                # Dependências e scripts do projeto (Vite, React, Tailwind, TypeScript)
 ┣ 📄 vite.config.ts              # Configuração do bundler Vite
 ┣ 📄 tsconfig.json               # Configuração do TypeScript
 ┣ 📄 README.md                   # Documentação detalhada do projeto
 ┗ 📂 src/                        # Código-fonte modularizado
    ┣ 📄 main.tsx                 # Ponto de montagem da aplicação
    ┣ 📄 App.tsx                  # Gerenciador global de rotas/telas, carrinho, favoritos, busca e modais
    ┣ 📄 index.css                # Definições de variáveis CSS (Design System Neo-Akiba) e importação Tailwind
    ┣ 📂 data/
    ┃  ┣ 📄 storeData.ts          # Base de dados dos produtos, categorias, ofertas e links diretos de imagens
    ┃  ┗ 📄 authStorage.ts        # Funções de persistência no localStorage (Cadastro, Login, Perfil e Pedidos)
    ┣ 📂 components/
    ┃  ┣ 📄 Layout.tsx            # Cabeçalho responsivo (TopNavBar), Menu Mobile e Rodapé (Footer)
    ┃  ┣ 📄 SafeImage.tsx         # Componente de imagem resiliente com fallback automático e suporte a URL direta
    ┃  ┣ 📄 ProductQuickViewModal.tsx # Modal de ficha técnica detalhada do colecionável
    ┃  ┗ 📄 ImageLinksModal.tsx   # Gerenciador visual para editar/copiar links diretos de imagens
    ┗ 📂 screens/
       ┣ 📄 HomeScreen.tsx        # Tela 1: Início, Hero Banner, Ofertas Relâmpago e Vitrine
       ┣ 📄 CatalogProfileScreen.tsx # Tela 2: Catálogo de Produtos com Filtro de Preço e Categorias
       ┣ 📄 CheckoutScreen.tsx    # Tela 3: Aba Carrinho (Itens Selecionados, Destino e botão Ir para Pagamento)
       ┣ 📄 PaymentScreen.tsx     # Tela 4: Página exclusiva de Forma de Pagamento (Pix, Cartão 12x e Boleto)
       ┣ 📄 RegisterScreen.tsx    # Tela 5: Cadastro de Colecionador integrado ao localStorage
       ┣ 📄 LoginScreen.tsx       # Tela 6: Login com autenticação local e acesso rápido de demonstração
       ┗ 📄 ProfileScreen.tsx     # Tela 7: Área de Perfil pós-login (Meus Dados, Meus Pedidos e Favoritos)
```

---

## 🖥️ 4. Como Cada Funcionalidade Foi Construída

### 4.1. Cabeçalho e Navegação Responsiva (`Layout.tsx`)
- **Barra de Navegação Limpa**: Contém os links principais (**Início**, **Catálogo de Produtos**, **Ofertas** com rolagem suave até a seção `#ofertas`, e **Pagamento**).
- **Busca Instantânea**: Digitar na barra de pesquisa filtra os produtos em tempo real e direciona automaticamente para a visualização dos resultados.
- **Botão de Favoritos (♥)**: Exibe o contador atualizado em tempo real. Ao clicar, abre a gaveta interativa **"Meus Favoritos"**, permitindo adicionar itens ao carrinho ou removê-los.
- **Alternância de Tema (Claro / Escuro)**: Alterna a classe `.dark` no elemento `<html>`, trocando dinamicamente toda a paleta de cores via variáveis CSS (`--color-surface`, `--color-primary`, etc.).
- **Menu Mobile (Hambúrguer)**: Em telas menores (`< 1024px`), exibe um botão de menu expansível com barra de busca mobile e links adaptados para toque.

### 4.2. Tela Inicial e Ofertas (`HomeScreen.tsx`)
- **Hero Section**: Destaque principal da *Figure 1/7 Shadow Sovereign* com selo de autenticidade e chamada para ação.
- **Oferta Relâmpago (`#ofertas`)**: Seção com cronômetro regressivo em tempo real, preço promocional no Pix e botão de compra rápida.
- **Cards de Produtos com Coração (Favoritos)**: Cada card possui botão de coração (`♥`) no canto superior direito e ao lado do botão de compra, mudando de cor e preenchimento quando favoritado.

### 4.3. Catálogo de Produtos com Filtro de Preço (`CatalogProfileScreen.tsx`)
- **Filtro de Preço Duplo**:
  - **Controle Deslizante (`<input type="range">`)**: Permite ajustar o teto máximo de preço (de `R$ 80` a `R$ 1.000`).
  - **Atalhos de Faixa de Preço**: Botões rápidos para *Todos os preços*, *Até R$ 150*, *R$ 150 a R$ 350* e *Acima de R$ 350*.
- **Filtros Combinados**: Filtra simultaneamente por **Categoria** (*Scale Figures*, *Nendoroids*, *Posters*, *Vestuário*, *Mangás*), **Apenas Favoritos (♥)**, **Disponibilidade em Estoque** e **Ordenação** (*Menor Preço*, *Maior Preço*, *Maior Desconto*).
- **Alternância de Visualização**: Permite alternar entre **Grade (Grid)** e **Lista Detalhada**.

### 4.4. Aba Carrinho / Resumo do Pedido (`CheckoutScreen.tsx`)
- **Foco em Itens e Destino**: Exibe exclusivamente os blocos de **Itens Selecionados** (com controle de quantidade `-`/`+`, remoção e itens complementares de proteção) e **Destino** (endereço de entrega sincronizado com o usuário logado e simulador de CEP).
- **Resumo Financeiro & Cupom**: Calcula subtotal, desconto automático no Pix (5%) e aceita os cupons `SENAI10` ou `OTAKU10` (10% OFF + Frete Blindado Grátis).
- **Fluxo Direto**: O botão principal **"Ir para Pagamento"** leva diretamente para a página exclusiva de pagamento.

### 4.5. Página de Forma de Pagamento Separada (`PaymentScreen.tsx`)
- **3 Métodos de Pagamento**:
  1. **Pix Instantâneo (-5% OFF)**: Exibe QR Code dinâmico e código *Pix Copia e Cola* com botão de cópia rápida.
  2. **Cartão de Crédito (até 12x sem juros)**: Formulário com máscara de cartão, validade, CVV, seletor de parcelas e cartão virtual estilizado que reflete os dados digitados.
  3. **Boleto Bancário Registrado**: Geração de linha digitável copiável.
- **Finalização Real**: Ao clicar em **"Confirmar Pagamento e Finalizar Pedido"**, gera um protocolo único (`#OV-...`), salva o pedido no `localStorage`, limpa o carrinho e redireciona o usuário para o histórico na **Área de Perfil**.

### 4.6. Cadastro, Login e Área de Perfil com `localStorage` (`authStorage.ts`)
- **Chaves de Armazenamento no Navegador**:
  - `otakuverse_users_v1`: Lista de usuários cadastrados.
  - `otakuverse_current_user_v1`: Sessão ativa do colecionador logado.
  - `otakuverse_orders_v1`: Histórico de pedidos finalizados na página de pagamento.
- **Área de Perfil (`ProfileScreen.tsx`)**: Dividida em 3 abas (**Meus Dados & Endereço**, **Meus Pedidos** e **Lista de Desejos**), permitindo atualizar cadastro, trocar avatar via URL direta ou upload e acompanhar pedidos.

---

## 📱 5. Semântica e Responsividade (Web / Mobile)

- **Tags Semânticas Utilizadas**:
  - `<header>`: Cabeçalho fixo com logotipo, navegação e ações.
  - `<nav>`: Menus de navegação principal e filtros de categoria.
  - `<main>`: Conteúdo central de cada tela.
  - `<section>`: Agrupamentos temáticos (Hero, Ofertas, Catálogo, Checkout).
  - `<article>`: Cards individuais de produtos e pedidos.
  - `<aside>`: Barras laterais de filtros de preço e resumo financeiro.
  - `<footer>`: Rodapé institucional com links rápidos e dados de atendimento.
- **Pontos de Quebra (Breakpoints)**:
  - **Mobile (`< 640px`)**: 1 coluna nos grids de produtos, menu hambúrguer recolhido, botões com área de toque ampliada.
  - **Tablet (`640px – 1024px`)**: 2 colunas no catálogo, filtros empilhados de forma ergonômica.
  - **Desktop (`> 1024px`)**: Layout completo em até 12 colunas (`max-w-[1440px]`), barra lateral fixa de filtros e resumo de compra lateral.

---

## 🚀 6. Como Executar o Projeto no Seu Computador

### Opção 1: Abrir Direto no VS Code (Mais Rápido — Sem Instalar Nada)
1. Extraia a pasta do projeto no seu computador e abra-a no **Visual Studio Code**.
2. Como o arquivo **`index.html`** na raiz já está integrado ao **`style.css`** e ao **`script.js`** compilados:
   - Clique com o botão direito no arquivo **`index.html`** e selecione **"Open with Live Server"** (extensão *Live Server* do VS Code), **OU**
   - Dê dois cliques diretamente no arquivo **`index.html`** para abri-lo no seu navegador (Chrome, Edge, Firefox).

### Opção 2: Executar em Modo de Desenvolvimento (Node.js + Vite)
Caso queira editar os arquivos TypeScript/React dentro da pasta `src/`:
```bash
# 1. Instale as dependências
npm install

# 2. Inicie o servidor de desenvolvimento na porta 3000
npm run dev
```

---

## 🧪 7. Dados para Teste Rápido na Apresentação

- **Conta de Demonstração (Login com 1 clique na tela de Login)**:
  - **E-mail**: `kenji@otakuverse.jp`
  - **Senha**: `akiba2025`
- **Cupons de Desconto (no Carrinho)**:
  - Digite **`SENAI10`** ou **`OTAKU10`** para aplicar **10% de desconto + Frete Grátis**.
