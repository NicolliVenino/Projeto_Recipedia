# 🍳 Recipedia

# Descrição do projeto
&nbsp; &nbsp; &nbsp; &nbsp;Desenvolvido durante o segundo módulo do curso de engenharia da computação do Instituto de Tecnologia e Liderança (Inteli), o projeto consiste em uma plataforma WEB que tem como objetivo facilitar e democratizar o acesso às receitas gastronômicas, de modo a concentrá-las em um único espaço digital que permite a criação de pastas e a troca de informações entre os usuários.

# Estrutura de pastas
&nbsp; &nbsp; &nbsp; &nbsp;Segue abaixo a estrutura de pastas do projeto.
```
Projeto_Recipedial/
│
├── assets/                # Arquivos públicos como imagens e fontes
|   └── modelo-conceitual-banco.png 
|   └── modelo-logico-banco.png  
|   └── modelo-fisico-banco.png            
├── config/                # Arquivos de configuração (ex: conexão com banco)
│   └── database.js
├── controllers/           # Lógica de controle das requisições
│   └── HomeController.js
├── documents/             # Documentação do projeto - Web Application Document
|   └── WAD.md
├── models/                # Definição de modelos de dados (estrutura do banco)
│   └── User.js
├── node_modules/          # Pacotes do node 
├── routes/                # Definição das rotas do sistema
│   └── index.js
├── scripts                # Arquivos de JavaScript públicos
├── services/              # Serviços auxiliares do sistema
│   └── userService.js                            
├── styles/                # Arquivos CSS públicos
├── tests/                 # Arquivos de testes unitários
│   └── example.test.js
├── views/                 # Templates e componentes visuais da aplicação
├── .gitignore             # Arquivo para ignorar arquivos no Git
├── .env.example           # Arquivo de exemplo para variáveis de ambiente
├── jest.config.js         # Arquivo de configuração do Jest
├── package-lock.json      # Gerenciador de dependências do Node.js
├── package.json           # Gerenciador de dependências do Node.js
├── README.md              # Documentação do projeto (Markdown)
├── server.js              # Arquivo principal que inicializa o servidor
└── rest.http              # Teste de endpoints 
```

# Como executar o projeto localmente?
## Requisitos:
- Instalação do Node.js (v18+);
- Instalação do PostgreSQL (v15+);
- Instalação do Git.

## Instalação

1) Clone o projeto
```
git clone https://github.com/NicolliVenino/Projeto_Recipedia.git
```

2) Instale as dependências
```
npm install
```

3) Rode o seguinte código para iniciar o servidor
```
node server.js
```
