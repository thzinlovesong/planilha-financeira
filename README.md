💰 Planilha Financeira
Sistema completo de gestão financeira pessoal com tema escuro, projeções de gastos e controle de transações reais.

Status: em desenvolvimento
Licença: MIT
Node: 18.x
React: 18.x

--------------------------------------------------------------------------------
FUNCIONALIDADES
--------------------------------------------------------------------------------
✅ Autenticação - Registro e login com JWT
✅ Tema Escuro - Interface moderna e agradável
✅ Dashboard - Resumo financeiro com gráficos
✅ Transações - Controle de entradas e saídas
✅ Projeções - Planejamento de gastos separado do real
✅ Comparativo - Veja a diferença entre planejado e realizado
✅ Gráficos - Evolução diária e gastos por categoria
✅ Responsivo - Funciona em desktop e mobile

--------------------------------------------------------------------------------
TECNOLOGIAS
--------------------------------------------------------------------------------
FRONTEND:
- React 18
- Vite
- TailwindCSS
- React Router DOM
- Recharts (gráficos)
- Axios

BACKEND:
- Node.js
- Express
- SQLite3
- JWT (autenticação)
- Bcrypt (hash de senhas)

--------------------------------------------------------------------------------
ESTRUTURA DO PROJETO
--------------------------------------------------------------------------------
planilha-financeira/
├── backend/
│   ├── src/
│   │   ├── database/      # Configuração do banco
│   │   ├── models/         # Models do banco
│   │   ├── routes/         # Rotas da API
│   │   ├── controllers/    # Controladores
│   │   ├── middlewares/    # Middlewares (auth)
│   │   └── server.js       # Entry point
│   ├── package.json
│   └── .env
├── frontend/
│   ├── src/
│   │   ├── pages/          # Páginas (Login, Dashboard, etc)
│   │   ├── components/     # Componentes reutilizáveis
│   │   ├── styles/         # Estilos globais
│   │   ├── services/       # Configuração da API
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── package.json
│   └── vite.config.js
├── package.json            # Dependências da raiz
├── vercel.json             # Configuração do deploy
└── README.md

--------------------------------------------------------------------------------
INSTALAÇÃO E EXECUÇÃO
--------------------------------------------------------------------------------
PRÉ-REQUISITOS:
- Node.js 18+
- npm ou yarn

1. Clone o repositório:
git clone https://github.com/seu-usuario/planilha-financeira.git
cd planilha-financeira

2. Instale as dependências:
# Instala tudo de uma vez (backend + frontend)
npm run install:all

# Ou manualmente:
cd backend && npm install
cd frontend && npm install
npm install

3. Configure as variáveis de ambiente:
Crie um arquivo .env na pasta backend/:
PORT=3333
JWT_SECRET=sua_chave_secreta_aqui
FRONTEND_URL=http://localhost:3000

4. Execute o projeto:
# Executa backend e frontend juntos
npm run dev

# Ou separadamente:
npm run dev:backend  # Backend na porta 3333
npm run dev:frontend # Frontend na porta 3000

5. Acesse:
- Frontend: http://localhost:3000
- Backend API: http://localhost:3333/api

--------------------------------------------------------------------------------
DEPLOY NA VERCEL
--------------------------------------------------------------------------------
1. Push para o GitHub:
git init
git add .
git commit -m "Primeiro deploy"
git remote add origin https://github.com/seu-usuario/planilha-financeira.git
git push -u origin main

2. Deploy na Vercel:
- Acesse vercel.com
- Clique em "Add New Project"
- Importe o repositório
- Configure:
  - Framework Preset: Vite
  - Root Directory: ./
  - Build Command: npm run build
  - Output Directory: frontend/dist

3. Adicione as variáveis de ambiente no painel da Vercel:
JWT_SECRET = sua_chave_secreta
FRONTEND_URL = https://seu-projeto.vercel.app

4. Clique em "Deploy"

--------------------------------------------------------------------------------
END-POINTS DA API
--------------------------------------------------------------------------------
AUTENTICAÇÃO:
POST /api/auth/registrar - Registrar novo usuário
POST /api/auth/login - Login e geração de token

TRANSAÇÕES:
GET /api/transacoes - Listar todas as transações
POST /api/transacoes - Adicionar nova transação
GET /api/transacoes/resumo - Resumo do mês (entradas/saídas)

PROJEÇÕES:
GET /api/projecoes - Listar projeções do mês
POST /api/projecoes - Criar/atualizar projeção
GET /api/projecoes/comparativo - Comparativo previsto vs real

--------------------------------------------------------------------------------
BANCO DE DADOS
--------------------------------------------------------------------------------
TABELA: usuarios
- id (INTEGER, PK)
- nome (TEXT)
- email (TEXT, UNIQUE)
- senha_hash (TEXT)
- saldo_inicial (REAL)
- created_at (DATETIME)

TABELA: transacoes_reais
- id (INTEGER, PK)
- usuario_id (INTEGER, FK)
- tipo (TEXT: 'entrada' | 'saida')
- valor (REAL)
- descricao (TEXT)
- categoria (TEXT)
- data (DATETIME)

TABELA: projecoes
- id (INTEGER, PK)
- usuario_id (INTEGER, FK)
- categoria (TEXT)
- valor_previsto (REAL)
- valor_real (REAL)
- mes (INTEGER)
- ano (INTEGER)

--------------------------------------------------------------------------------
DEPENDÊNCIAS PRINCIPAIS
--------------------------------------------------------------------------------
BACKEND:
express: ^4.18.2
sqlite3: ^5.1.6
jsonwebtoken: ^9.0.2
bcryptjs: ^2.4.3
cors: ^2.8.5

FRONTEND:
react: ^18.2.0
react-router-dom: ^6.15.0
recharts: ^2.8.0
tailwindcss: ^3.3.3
axios: ^1.5.0

--------------------------------------------------------------------------------
PRÓXIMAS FUNCIONALIDADES
--------------------------------------------------------------------------------
[ ] Recorrência de transações (mensal, semanal)
[ ] Exportar dados em CSV/Excel
[ ] Notificações de metas
[ ] Categorias personalizadas com ícones
[ ] Métricas e indicadores financeiros
[ ] Backup automático
[ ] Modo offline com PWA

--------------------------------------------------------------------------------
COMO CONTRIBUIR
--------------------------------------------------------------------------------
1. Fork o projeto
2. Crie sua branch: git checkout -b feature/nova-funcionalidade
3. Commit suas mudanças: git commit -m 'Adiciona nova funcionalidade'
4. Push: git push origin feature/nova-funcionalidade
5. Abra um Pull Request

--------------------------------------------------------------------------------
LICENÇA
--------------------------------------------------------------------------------
MIT © 2024 - Seu Nome

--------------------------------------------------------------------------------
CONTATO
--------------------------------------------------------------------------------
Email: seu-email@example.com
GitHub: @seu-usuario
LinkedIn: seu-linkedin

--------------------------------------------------------------------------------
Desenvolvido com 💜 e muito café ☕
