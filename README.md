# Mensalify: Sistema de Gerenciamento de Assinaturas

Um sistema completo para gerenciar assinaturas, cobranças e clientes com integração com WhatsApp e PIX.

## Recursos

- Gerenciamento de clientes
- Processamento de pagamentos via PIX
- Notificações via WhatsApp
- Verificação OCR de comprovantes de pagamento
- Painel administrativo completo

## Tecnologias

- Frontend: React, TailwindCSS, shadcn/ui
- Backend: Node.js, Express
- Banco de dados: PostgreSQL
- ORM: Drizzle

## Como implantar

### Opção 1: Deploy no Replit

1. Clique no botão "Deploy" no topo da página do Replit
2. Siga as instruções para completar o processo

Esta opção implantará tanto o frontend quanto o backend em um só lugar.

### Opção 2: Deploy Separado (Frontend no Netlify, Backend no Render)

#### Deploy do Frontend no Netlify

1. Conecte sua conta GitHub ao Netlify
2. Importe este repositório
3. Configure as variáveis de ambiente:
   - `VITE_API_URL`: URL do seu backend (ex: https://mensalify-backend.onrender.com)
4. Dispare o deploy

#### Deploy do Backend no Render

1. Conecte sua conta GitHub ao Render
2. Importe este repositório
3. Configure como um "Web Service"
4. Escolha Node.js como ambiente
5. Configure o comando de build: `npm install && npm run build`
6. Configure o comando de start: `npm run start`
7. Configure as variáveis de ambiente:
   - `NODE_ENV`: `production`
   - `DATABASE_URL`: Sua URL do PostgreSQL
   - `GROQ_API_KEY`: Sua chave da API Groq para OCR
   - `Z_API_INSTANCE_ID`: ID da instância Z-API
   - `Z_API_TOKEN`: Token Z-API
   - `Z_API_SECURITY_TOKEN`: Token de segurança Z-API

## Configuração do Banco de Dados

Recomendamos usar o Neon Database (PostgreSQL serverless) para o seu banco de dados:

1. Crie uma conta no [Neon](https://neon.tech)
2. Crie um novo projeto e banco de dados
3. Copie a URL de conexão e adicione-a como `DATABASE_URL` nas variáveis de ambiente do Render

## Variáveis de Ambiente Necessárias

- `DATABASE_URL`: URL de conexão com o PostgreSQL
- `GROQ_API_KEY`: Chave da API Groq para OCR
- `Z_API_INSTANCE_ID`: ID da instância Z-API
- `Z_API_TOKEN`: Token Z-API
- `Z_API_SECURITY_TOKEN`: Token de segurança Z-API

## Após o Deploy

1. Inicialize o banco de dados executando as migrações:
   - No Render: Adicione `&& npm run db:push` ao seu comando de build
2. Opcionalmente, popule o banco com dados iniciais:
   - No Render: Adicione `&& npm run db:seed` ao seu comando de build

## Créditos

Desenvolvido como um sistema de gerenciamento de assinaturas.