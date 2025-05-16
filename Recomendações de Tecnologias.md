**Recomendações de tecnologias para a disciplina de Desenvolvimento de Software**

## **Frontend**

### **HTML, CSS e JavaScript**

Descrição: Tecnologias fundamentais para construção de interfaces web.

* Prós:

* Altamente difundidas e documentadas.  
* Base para qualquer framework moderno.

* Contras:

* Trabalhos repetitivos e complexos sem abstrações/frameworks.

Presença no mercado: Onipresentes. Todo desenvolvedor web precisa conhecê-las.

### **React**

Descrição: Biblioteca JavaScript para criação de interfaces reativas com componentes reutilizáveis.

* Prós:

* Comunidade enorme e vasto ecossistema.  
* Suporte a bibliotecas e ferramentas modernas.

* Contras:

* Curva de aprendizado intermediária (JSX, hooks, estado global).

Presença no mercado: Uma das tecnologias frontend mais populares e requisitadas atualmente.

### **Svelte**

Descrição: Framework moderno que compila os componentes para JavaScript puro no build.

* Prós:

* Sintaxe simples e próxima do HTML/JS puro.  
* Reatividade embutida sem boilerplate.

* Contras:

* Adoção no mercado ainda é pequena.  
* Ecossistema e suporte da comunidade menores que React.

Presença no mercado: Em crescimento, mas ainda nichado.

### **Next.js**

Descrição: Framework baseado em React, com suporte a renderização server-side e geração estática.

* Prós:

* SEO amigável.  
* Sistema de rotas simples.  
* Suporte nativo a SSR e SSG.

* Contras:

* Pode ser mais complexo que usar apenas React puro.

Presença no mercado: Amplamente utilizado em produção, especialmente em grandes sites e apps.

### **Vite**

Descrição: Ferramenta moderna de build para projetos JavaScript/TypeScript.

* Prós:

* Build e hot reload ultrarrápidos.  
* Configuração simples.

* Contras:

* Menor compatibilidade com ferramentas antigas.

Presença no mercado: Crescente, sendo cada vez mais adotado no lugar do Webpack.

### **Axios**

Descrição: Cliente HTTP para consumo de APIs.

* Prós:

* Interface simples e poderosa.  
* Suporte a interceptadores e cancelamento de requisições.

* Contras:

* Código levemente mais verboso que fetch nativo.

Presença no mercado: Amplamente usado em aplicações frontend e backend.

### **React Router DOM**

Descrição: Biblioteca para gerenciamento de rotas em aplicações React.

* Prós:

* Poderosa e altamente customizável.

* Contras:

* Pode ser complexa para iniciantes.

Presença no mercado: Muito utilizada em projetos React SPA.

## **Backend**

### **Node.js com Express**

Descrição: Ambiente de execução JavaScript com framework minimalista para criação de APIs REST.

* Prós:

* Leve, rápido e altamente customizável.  
* Ecossistema vasto de pacotes via NPM.

* Contras:

* Pouca estrutura nativa, exige organização manual.

Presença no mercado: Muito usado, especialmente em startups e aplicações web.

### **Flask**

Descrição: Framework Python minimalista para APIs e aplicações web.

* Prós:

* Simples e rápido de configurar.  
* Ideal para projetos pequenos e médios.

* Contras:

* Menos indicado para projetos grandes sem estrutura adicional.

Presença no mercado: Bastante usado no meio acadêmico e em protótipos.

### **FastAPI**

Descrição: Framework moderno em Python para construção de APIs performáticas com validação automática.

* Prós:

* Tipagem estática com Pydantic.  
* Geração automática de documentação Swagger.  
* Alto desempenho.

* Contras:

* Menor comunidade que Flask/Express.

Presença no mercado: Em rápida ascensão, principalmente em projetos Python modernos.

## **Banco de Dados**

### **PostgreSQL**

Descrição: Banco relacional open-source com suporte a extensões poderosas.

* Prós:

* Confiável, performático e muito flexível.  
* Suporte a ORMs (como Prisma, SQLAlchemy).

* Contras:

* Requer conhecimento em SQL e modelagem relacional.

Presença no mercado: Um dos bancos de dados relacionais mais usados no mundo.

### **MongoDB**

Descrição: Banco NoSQL orientado a documentos (JSON-like).

* Prós:

* Esquema flexível, ideal para dados semi-estruturados.  
* Escalável e fácil de começar.  
* Suporte a ODMs como Mongoose (Node.js), MongoEngine (Python).

* Contras:

* Mais difícil de aplicar regras de integridade sem um esquema definido.

Presença no mercado: Muito popular em startups, aplicações modernas e projetos com dados não relacionais.

## **Testes**

### **Pytest**

Descrição: Framework poderoso para testes em Python.

* Prós:

* Suporte a fixtures, parametrização e plugins.  
* Sintaxe simples.

Presença no mercado: Principal ferramenta de testes Python, amplamente usada em produção.

### **Jest**

Descrição: Framework completo para testes em JavaScript e TypeScript.

* Prós:

* Fácil de configurar com React.  
* Suporte a mocks, cobertura de código e testes assíncronos.

Presença no mercado: Padrão de testes em aplicações frontend modernas com React.

# **Glossário de Siglas**

**SPA (Single Page Application)**: Aplicação web que carrega uma única página HTML e atualiza o conteúdo dinamicamente sem recarregar a página inteira.

**SSR (Server-Side Rendering)**: Técnica em que o conteúdo da página é renderizado no servidor antes de ser enviado ao navegador, melhorando o desempenho e o SEO.

**SSG (Static Site Generation)**: Geração de páginas HTML estáticas no momento da build, resultando em sites rápidos e seguros.

**SEO (Search Engine Optimization)**: Conjunto de práticas para melhorar a visibilidade de um site em motores de busca como o Google.

**ORM (Object-Relational Mapping)**: Ferramenta que mapeia objetos da linguagem de programação para tabelas de bancos de dados relacionais.

**ODM (Object Document Mapper)**: Ferramenta que mapeia objetos da linguagem de programação para documentos de bancos NoSQL, como MongoDB.

