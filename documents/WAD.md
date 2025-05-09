# Web Application Document - Projeto Individual - Módulo 2 - Inteli

## Recipedia

#### Autora: [Nicolli Venino Santana](https://www.linkedin.com/in/nicolli-venino-santana-b84341254/)

## Sumário

1. [Introdução](#c1)  
2. [Visão Geral da Aplicação Web](#c2)  
3. [Projeto Técnico da Aplicação Web](#c3)  
4. [Desenvolvimento da Aplicação Web](#c4)  
5. [Referências](#c5)  

<br>

## <a name="c1"></a>1. Introdução (Semana 01)

O Recipedia é uma plataforma WEB de publicação, coleção e armazenamento de receitas gastronômicas que aspira facilitar e potencializar o acesso à gastronomia, tanto para chefs renomados quanto para qualquer usuário interessado em cozinhar. Nesse sentido, o objetivo do projeto é concentrar receitas publicadas para e pela comunidade de usuários amantes de culinária, sem necessidade de diploma, ou por chefs do mercado que desejam compartilhar experiências, assim como servir de portfólio para estudantes e formados em áreas relacionadas à cozinha, de modo que possam publicar suas ideias de pratos e trocar informações entre si.

Diante disso, para alcançar o escopo supracitado, o Recipedia contempla a funcionalidade de visualizar várias receitas na tela, sob as quais os usuários têm a liberdade de salvar em pastas personalizadas aquelas que melhor lhe agradar. Paralelamente, ao selecionar uma receita, o usuário tem acesso não só às informações de tempo de preparo e quantidade, mas também à opção de fazer anotações pessoais e inserir uma nota (variando de 1 a 5 estrelas). Dessa forma, a plataforma garante agradar usuários que não necessariamente possuem experiência profissional gastronômica, porém que, ainda assim, desejam exercer ou apreciar a culinária em suas vidas. 

Além disso, vale mencionar que o site abrange a função dos usuários criarem receitas autorais e publicá-las na plataforma. Essas receitas ficam salvas e visíveis no perfil do usuário, sujeitas a comentários e notas de toda a comunidade. Assim também, os usuários podem “seguir” os perfis uns dos outros e trocar informações por intermédio de um chat - no entanto, é imprescindível ressaltar que tal aplicação é opcional e o usuário tem liberdade de deixar seu perfil público (no qual suas pastas e receitas autorais são transparentes à toda comunidade) ou privado. Com isso, o Recipedia atua como um portfólio no qual universitários e profissionais do campo podem tornar seu trabalho público.

---

## <a name="c2"></a>2. Visão Geral da Aplicação Web

### 2.1. Personas (Semana 01 - opcional)

*Posicione aqui sua(s) Persona(s) em forma de texto markdown com imagens, ou como imagem de template preenchido. Atualize esta seção ao longo do módulo se necessário.*

### 2.2. User Stories (Semana 01 - opcional)

*Posicione aqui a lista de User Stories levantadas para o projeto. Siga o template de User Stories e utilize a referência USXX para numeração (US01, US02, US03, ...). Indique todas as User Stories mapeadas, mesmo aquelas que não forem implementadas ao longo do projeto. Não se esqueça de explicar o INVEST de 1 User Storie prioritária.*

---

## <a name="c3"></a>3. Projeto da Aplicação Web

### 3.1. Modelagem do banco de dados  (Semana 3)

#### 3.1.1. Modelagem Conceitual do banco de dados

<p align = "center">Figura 1: Modelagem Conceitual</p>

<p align="center"> <img src="https://github.com/user-attachments/assets/090020b8-ccd4-48dd-a737-b7b36fe89038" alt="Modelagem Conceitual"> </p>

<p align = "center">Fonte: material produzido pela autora por intermédio do software DRAW.io (2025).</p> <br>

#### 3.1.2. Modelagem Relacional do banco de dados

<p align = "center">Figura 2: Modelagem Relacional</p>

<p align="center"> <img src="https://github.com/user-attachments/assets/7ef4c3e3-b009-40dd-9518-188d12870680" alt="Modelagem Relacional"> </p>

<p align = "center">Fonte: material produzido pela autora por intermédio do software drawSQL (2025).</p> <br>


#### 3.1.3. Modelagem física com o Schema do banco de dados

```sql
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  first_name TEXT NOT NULL,
  last_name TEXT NOT NULL,
  avatar TEXT NOT NULL,
  username TEXT NOT NULL,
  email TEXT NOT NULL,
  password TEXT NOT NULL,
  description TEXT NOT NULL
);

CREATE TABLE user_formations  (
  id SERIAL PRIMARY KEY,
  id_user INT REFERENCES users(id) ON DELETE CASCADE,
  formation TEXT NOT NULL
);

CREATE TABLE folders (
  id SERIAL PRIMARY KEY,
  name TEXT NOT NULL,
  description TEXT NOT NULL,
  id_user INT REFERENCES users(id) ON DELETE CASCADE
);

CREATE TABLE recipes (
  id SERIAL PRIMARY KEY,
  name TEXT NOT NULL,
  image TEXT NOT NULL,
  tipe TEXT NOT NULL,
  category TEXT NOT NULL,
  email TEXT NOT NULL,
  directions TEXT NOT NULL,
  prep_time INT,
  cook_time INT,
  servings INT,
  yield INT,
  score INT,
  author TEXT NOT NULL
);

CREATE TABLE folders_recipes  (
  id SERIAL PRIMARY KEY,
  id_folder INT REFERENCES folders(id) ON DELETE CASCADE,
  id_recipe INT REFERENCES recipes(id) ON DELETE CASCADE
);

CREATE TABLE ingredients (
  id SERIAL PRIMARY KEY,
  name TEXT NOT NULL,
  specification TEXT NOT NULL
);

CREATE TABLE recipes_ingredients  (
  id SERIAL PRIMARY KEY,
  id_recipe INT REFERENCES recipes(id) ON DELETE CASCADE,
  id_ingredient INT REFERENCES ingredients(id) ON DELETE CASCADE
);

```
### 3.1.4 BD e Models (Semana 5)
*Descreva aqui os Models implementados no sistema web*

### 3.2. Arquitetura (Semana 5)

*Posicione aqui o diagrama de arquitetura da sua solução de aplicação web. Atualize sempre que necessário.*

**Instruções para criação do diagrama de arquitetura**  
- **Model**: A camada que lida com a lógica de negócios e interage com o banco de dados.
- **View**: A camada responsável pela interface de usuário.
- **Controller**: A camada que recebe as requisições, processa as ações e atualiza o modelo e a visualização.
  
*Adicione as setas e explicações sobre como os dados fluem entre o Model, Controller e View.*

### 3.3. Wireframes (Semana 03 - opcional)

*Posicione aqui as imagens do wireframe construído para sua solução e, opcionalmente, o link para acesso (mantenha o link sempre público para visualização).*

### 3.4. Guia de estilos (Semana 05 - opcional)

*Descreva aqui orientações gerais para o leitor sobre como utilizar os componentes do guia de estilos de sua solução.*


### 3.5. Protótipo de alta fidelidade (Semana 05 - opcional)

*Posicione aqui algumas imagens demonstrativas de seu protótipo de alta fidelidade e o link para acesso ao protótipo completo (mantenha o link sempre público para visualização).*

### 3.6. WebAPI e endpoints (Semana 05)

*Utilize um link para outra página de documentação contendo a descrição completa de cada endpoint. Ou descreva aqui cada endpoint criado para seu sistema.*  

### 3.7 Interface e Navegação (Semana 07)

*Descreva e ilustre aqui o desenvolvimento do frontend do sistema web, explicando brevemente o que foi entregue em termos de código e sistema. Utilize prints de tela para ilustrar.*

---

## <a name="c4"></a>4. Desenvolvimento da Aplicação Web (Semana 8)

### 4.1 Demonstração do Sistema Web (Semana 8)

*VIDEO: Insira o link do vídeo demonstrativo nesta seção*
*Descreva e ilustre aqui o desenvolvimento do sistema web completo, explicando brevemente o que foi entregue em termos de código e sistema. Utilize prints de tela para ilustrar.*

### 4.2 Conclusões e Trabalhos Futuros (Semana 8)

*Indique pontos fortes e pontos a melhorar de maneira geral.*
*Relacione também quaisquer outras ideias que você tenha para melhorias futuras.*



## <a name="c5"></a>5. Referências

_Incluir as principais referências de seu projeto, para que o leitor possa consultar caso ele se interessar em aprofundar._<br>

---
---
