# RocketLog 📦

Uma API de gerenciamento de entregas construída com Node.js, Express e Prisma.

## Funcionalidades

- 👥 Autenticação e autorização de usuários
- 📝 Criação e gerenciamento de entregas
- 📊 Acompanhamento de status de entrega (em processamento, enviado, entregue)
- 📋 Logs de entrega com informações detalhadas de rastreamento
- 🔐 Controle de acesso baseado em funções (cliente, vendedor)

## Tecnologias

- Node.js
- TypeScript
- Express
- Prisma (PostgreSQL)
- Jest
- Docker
- Autenticação JWT
- Validação com Zod

## Como Começar

### Pré-requisitos

- Node.js
- Docker e Docker Compose
- Git

### Instalação

1. Clone o repositório:
```bash
git clone https://github.com/andersensilva/rocketlog.git
cd rocketlog
```

2. Instale as dependências:
```bash
npm install
```

3. Configure as variáveis de ambiente:
```bash
cp .env-example .env
```
Preencha as variáveis de ambiente necessárias:
- `DATABASE_URL`: String de conexão do PostgreSQL
- `JWT_SECRET`: Chave secreta para geração de tokens JWT

4. Inicie o banco de dados:
```bash
docker compose up -d
```

5. Execute as migrações do banco de dados:
```bash
npx prisma migrate dev
```

6. Inicie o servidor de desenvolvimento:
```bash
npm run dev
```

## Rotas da API

### Usuários
- `POST /users` - Criar novo usuário
- `POST /sessions` - Autenticar usuário

### Entregas
- `POST /deliveries` - Criar nova entrega
- `GET /deliveries` - Listar todas as entregas
- `PATCH /deliveries/:id/status` - Atualizar status da entrega

### Logs de Entrega
- `POST /delivery-logs` - Criar log de entrega
- `GET /delivery-logs/:delivery_id/show` - Buscar logs de entrega

## Testes

Execute a suite de testes:

```bash
npm run test:dev
```

## Autor

Andersen Silva