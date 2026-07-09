# Jeferson Dev Full Stack - Portal Institucional & Portfólio

Este projeto é um portal institucional e portfólio desenvolvido como parte de um **teste técnico para vaga de Desenvolvedor de Aplicações Web**. 

O projeto consiste na migração, componentização e rebranding completo de um site institucional de alto padrão (originalmente focado no setor industrial madeireiro) para uma marca moderna de engenharia de software: **Jeferson Dev Full Stack**.

---

## 🚀 Tecnologias Utilizadas

O projeto foi reestruturado utilizando uma stack moderna focada em performance máxima de carregamento (Core Web Vitals), SEO e fidelidade visual:

* **Framework Principal**: [Astro (v4)](https://astro.build/) - Adotado por sua arquitetura de ilhas (Island Architecture) e entrega de HTML 100% estático por padrão (SSG).
* **Estilização**: Vanilla CSS (extraído, modularizado e otimizado a partir das folhas de estilo premium originais).
* **Interatividade & Animações**:
  * **AOS (Animate On Scroll)**: Para transições e surgimento suave de elementos na tela.
  * **Typed.js**: Efeito dinâmico de digitação de termos no slider principal.
  * **Splide.js**: Carrosséis e sliders responsivos com aceleração de hardware.
* **Segurança e SEO**:
  * **JSON-LD (Schema.org)**: Estrutura de dados enriquecida para mecanismos de busca (SEO técnico).
  * **Metatags Open Graph & Twitter Card**: Otimização completa para compartilhamento em redes sociais.

---

## 📁 Estrutura de Pastas e Componentes

A arquitetura do projeto foi desenhada visando modularidade, componentização limpa e facilidade de manutenção:

```bash
spa/
├── public/                  # Arquivos estáticos (fontes, scripts e assets locais)
│   ├── assets/              # Imagens de marca, bandeiras e scripts auxiliares
│   └── img/                 # Assets de background css e imagens de renderização
├── src/
│   ├── components/          # Componentes reutilizáveis do portal
│   │   ├── About.astro            # Apresentação do desenvolvedor com contadores
│   │   ├── BlogCarousel.astro     # Carrossel com artigos recentes de tecnologia
│   │   ├── Categories.astro       # Seções de serviços (Sistemas, Sites, E-commerce)
│   │   ├── ContactCTA.astro       # Banner final com contatos e e-mail principal
│   │   ├── Footer.astro           # Rodapé institucional global
│   │   ├── Header.astro           # Menu de navegação responsivo (Desktop/Mobile)
│   │   ├── HeroSlider.astro       # Slider principal com Typed.js integrado
│   │   ├── Modals.astro           # Modais de aviso e botões flutuantes de contato
│   │   ├── ProductsCarousel.astro # Carrossel de portfólio de projetos web
│   │   └── ValueBlocks.astro      # Diferenciais técnicos (Performance, Código Limpo, etc.)
│   ├── layouts/
│   │   └── Layout.astro     # Shell global da página (metas, scripts de Analytics e fontes)
│   ├── pages/               # Roteamento estático baseado em arquivos
│   │   ├── minha-conta/
│   │   │   └── entrar.astro # Área do Cliente (Formulários de Login e Modais de Acesso)
│   │   ├── [...slug].astro  # Catch-all de rotas secundárias e template de "Em Construção"
│   │   ├── contato.astro    # Página de contato com formulário e Google Maps integrado
│   │   ├── index.astro      # Página inicial agregando os componentes principais
│   │   ├── noticias.astro   # Listagem de artigos de blog e sidebar de navegação
│   │   ├── produtos.astro   # Grade principal com serviços oferecidos
│   │   ├── politica-de-privacidade.astro
│   │   └── quem-somos.astro # Trajetória do dev, Missão/Visão/Valores e Infra Cloud
│   └── styles/              # Folhas de estilo globais importadas pelo Layout
```

---

## 🛠️ Como Executar o Projeto Localmente

### Pré-requisitos
* [Node.js](https://nodejs.org/) (versão 18.14.1 ou superior recomendada)
* Gerenciador de pacotes `npm` (incluso com o Node.js)

### Passos para Instalação

1. Clone ou navegue até a pasta do projeto:
   ```bash
   cd spa
   ```

2. Instale todas as dependências do projeto:
   ```bash
   npm install
   ```

3. Execute o servidor de desenvolvimento local:
   ```bash
   npm run dev
   ```
   *O portal estará disponível no navegador através do endereço:* **`http://localhost:3000`**

---

## 📦 Builds e Deploy em Produção

Para gerar o bundle estático otimizado pronto para publicação em qualquer servidor de hospedagem estática (Vercel, Netlify, Cloudflare Pages ou AWS S3):

1. Compile o projeto:
   ```bash
   npm run build
   ```
   *Este comando gerará os arquivos estáticos na pasta* **`dist/`**.

2. Para testar o build de produção localmente antes do deploy:
   ```bash
   npm run preview
   ```

---

## 🌟 Principais Desafios & Soluções Aplicadas

1. **Pixel-Perfect e Fidelidade Visual**:
   * *Desafio*: Preservar exatamente a disposição visual, cores, tipografias e o comportamento interativo premium do site original.
   * *Solução*: Fizemos a extração refinada do CSS e JS originais. As dependências antigas de fontes que causavam requisições locais quebradas foram corrigidas para CDN oficiais no Layout central.
2. **Rebranding Completo e Coeso**:
   * *Desafio*: Transformar todo o texto e contexto focado na indústria de madeira para o setor de desenvolvimento web de forma profissional e crível.
   * *Solução*: Reescrevemos a história institucional criando uma linha do tempo profissional de tecnologia (2018-2026), ajustando blocos de valores para qualidade de software, migrando os posts de blog para temas de desenvolvimento frontend/backend/infraestrutura e reconfigurando os formulários.
3. **Resolução de Erros 404 (Assets)**:
   * *Desafio*: Folhas de estilo dependiam de imagens locais que não estavam na estrutura inicial.
   * *Solução*: Baixamos os vetores e imagens de background diretamente do servidor original (`bg777.png` e `border-radius.svg`) e os disponibilizamos na pasta pública do projeto, eliminando 100% de erros no console do navegador.

---

## 🔮 Planejamento de Futuras Implementações (Backend & Banco de Dados)

Com o objetivo de transformar esta aplicação em uma plataforma totalmente dinâmica e integrada, estão planejadas as seguintes etapas para a arquitetura de backend e dados:

### 1. Backend em PHP / Laravel
* **API RESTful**: Criação de endpoints estruturados com Laravel para servir as áreas dinâmicas da aplicação (como listagem de projetos/serviços, posts de notícias e recebimento de contatos).
* **Autenticação Segura (Sanctum/JWT)**: Migração e robustez da **Área do Cliente** (`/minha-conta/entrar`) utilizando autenticação baseada em token para controle de acesso às rotas restritas e painel de projetos.
* **Camada de Serviços & Filas**: Integração de disparo de e-mails assíncronos (orçamentos e contatos) utilizando filas (Queues/Redis) integradas com Amazon SES ou Mailgun, garantindo excelente tempo de resposta na interface.

### 2. Banco de Dados MySQL
* **Modelagem Relacional (Schema)**:
  * Tabela `users` (dados cadastrais dos clientes, permissões e hash de senha seguro via bcrypt).
  * Tabela `projects` (títulos, descrições, categorias, tecnologias utilizadas e links de imagens do portfólio).
  * Tabela `posts` (gerenciamento dos posts de tecnologia: slug, título, conteúdo HTML, categorias e datas de publicação).
  * Tabela `contact_requests` (registro histórico de leads, orçamentos solicitados e mensagens enviadas).
* **Otimização**: Definição de índices adequados em campos com alto fluxo de busca (como e-mails de usuários e slugs de artigos) e relacionamentos com chaves estrangeiras para assegurar integridade referencial.

