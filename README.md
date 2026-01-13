## 🥬 Horta na Porta - Sistema de Gestão Completo

## 📖 Sobre o Projeto
O Horta na Porta é um sistema desenvolvido para Jhones (38) e Silmara (35), empreendedores que conectam agricultura familiar com consumidores de produtos orgânicos. Plataforma integrada Web + Mobile para administração de finanças, gestão de recursos e vendas de produtos orgânicos da agricultura familiar

## 🎯 Contexto do Negócio
- Missão: Entregar produtos orgânicos (doces, verduras, vegetais) para pronto consumo

- Origem: Ideia de Silmara, que percebeu a dificuldade de consumir produtos naturais por falta de tempo

- Cliente-alvo: Pessoas que buscam alimentos saudáveis sem agrotóxicos

## ⚠️ Problemas Resolvidos
- Gestão Digital de Pedidos - Substitui cadernos físicos por sistema online

- Organização de Clientes - Cadastro estruturado com histórico de compras

- Emissão de Relatórios - Geração automática de PDF com jsPDF

## 🚀 Funcionalidades Implementadas
- Autenticação segura com JWT e Spring Security

- Cadastro e gerenciamento de produtos orgânicos

- Sistema completo de pedidos online

- Gestão de clientes (fixos, ocasionais, escolas, governo)

- Dashboard financeiro com gráficos

- Geração de relatórios em PDF com jsPDF + AutoTable

- Controle de estoque em tempo real

- Integração ViaCEP para busca de endereços

- Sistema de notificações com SweetAlert2 e ngx-toastr

## 🔄 Integrações
- API de e-mail Brevo para comunicação com clientes

- Sistema de autenticação JWT com Spring Security

- Upload de imagens de produtos

- Máscaras de formulário com ngx-mask

- UI Components com PrimeNG e Angular Material

## 🛠️ Tecnologias Utilizadas
## Backend (Spring Boot)
- Java 21 + Spring Boot 3.5.3

- MySQL 8.0+ (Banco de dados)

- Spring Security + JWT (Autenticação)

- Spring Data JPA (ORM)

- Maven (Gerenciamento de dependências)

## Frontend (Angular)
- Angular 17.1.0 (Framework)

- TypeScript 5.3.2 (Linguagem)

- PrimeNG 17 + Angular Material (UI Components)

- RxJS 7.8 (Programação reativa)

- jsPDF + AutoTable (Relatórios PDF)

## Banco de Dados
- MySQL 8.0+

- Spring JPA com ddl-auto: update

- JDBC com SSL desabilitado

- Timezone UTC configurado

## Ferramentas de Desenvolvimento
- Visual Studio Code / IntelliJ IDEA

- Git + GitHub (Versionamento)

- Postman (Testes de API)

- Node.js 22.14.0 + npm 10.9.2

- Angular CLI 17.1.2

## 📋 Estrutura do Projeto
horta-na-porta/
├── backend/                 # API Spring Boot (Java)
│   ├── src/main/java/com/hortanaporta/
│   │   ├── controller/     # Controladores REST
│   │   ├── model/         # Entidades JPA
│   │   ├── repository/    # Repositórios Spring Data
│   │   ├── service/       # Lógica de negócio
│   │   └── security/      # Configuração de segurança
│   ├── pom.xml            # Dependências Maven
│   └── application.properties
│
├── frontend/              # Aplicação Angular
│   ├── src/app/
│   │   ├── components/   # Componentes reutilizáveis
│   │   ├── pages/        # Páginas principais
│   │   ├── services/     # Serviços HTTP
│   │   └── models/       # Interfaces TypeScript
│   ├── package.json      # Dependências npm
│   └── angular.json      # Configuração Angular
│
└── README.md             # Esta documentação

## Acesso aos Serviços
## Frontend (Angular): http://localhost:4200

- Backend API: http://localhost:8080

- Banco de Dados: localhost:3306

## 🔗 Endpoints da API
- Autenticação
POST /api/auth/login - Login com JWT
POST /api/auth/register - Registro de usuário
GET /api/auth/me - Informações do usuário

- Produtos
GET /api/produtos - Listar todos produtos
GET /api/produtos/{id} - Buscar produto por ID
POST /api/produtos - Criar novo produto
PUT /api/produtos/{id} - Atualizar produto
DELETE /api/produtos/{id} - Excluir produto

- Pedidos
GET /api/pedidos - Listar pedidos
POST /api/pedidos - Criar novo pedido
GET /api/pedidos/{id} - Detalhes do pedido
PUT /api/pedidos/{id} - Atualizar pedido
PUT /api/pedidos/{id}/status - Atualizar status
DELETE /api/pedidos/{id} - Excluir pedido

- Clientes (Pessoas)
GET /api/pessoas - Listar clientes
POST /api/pessoas - Cadastrar cliente
GET /api/pessoas/{id} - Detalhes do cliente
PUT /api/pessoas/{id} - Atualizar cliente
DELETE /api/pessoas/{id} - Excluir cliente

- Endereços
GET /api/enderecos/cep/{cep} - Buscar endereço por CEP (ViaCEP)
GET /api/enderecos/pessoa/{id} - Endereços por pessoa
POST /api/enderecos - Cadastrar endereço
PUT /api/enderecos/{id} - Atualizar endereço
DELETE /api/enderecos/{id} - Excluir endereço

## 📊 Modelo de Dados
- Pessoa (Cliente/Usuário)
id: Long (Identificador único)
nmPessoa: String (Nome completo)
emailPessoa: String (E-mail)
senhaPessoa: String (Senha criptografada)
cpfPessoa: String (CPF)
rolePessoa: String (ADMIN, CLIENTE)
telefone: String
dataCadastro: Date

- Produto
cdProduto: Long (Código do produto)
nmProduto: String (Nome do produto)
descricao: String (Descrição)
preco: BigDecimal (Preço unitário)
estoque: Integer (Quantidade em estoque)
categoria: String (verdura, legume, fruta, doce)
organico: boolean (Produto orgânico)
imagemUrl: String (URL da imagem)

- Pedido
cdPedido: Long (Código do pedido)
pessoa: Pessoa (Cliente)
enderecoEntrega: Endereco (Endereço de entrega)
status: String (PENDENTE, CONFIRMADO, ENTREGUE, CANCELADO)
total: BigDecimal (Valor total)
observacoes: String (Observações do pedido)
itensPedido: List<ItemPedido> (Itens do pedido)
dataPedido: LocalDateTime (Data do pedido)

- Endereço
cdEndereco: Long (Código do endereço)
cep: String (CEP)
logradouro: String (Rua/Avenida)
numero: String (Número)
complemento: String (Complemento)
bairro: String (Bairro)
cidade: String (Cidade)
estado: String (Estado - UF)
pessoa: Pessoa (Proprietário do endereço)
enderecoPrincipal: boolean (Endereço principal)

## 🔒 Sistema de Segurança
- Autenticação JWT
- Tokens JWT com expiração de 24 horas
- Claims: email, userId, role
- Spring Security para proteção de endpoints
- PasswordEncoder para criptografia de senhas

## 🎨 Interface
## Telas Principais
- Login/Registro - Autenticação com JWT
- Produtos - Catálogo de produtos
- Pedidos - Criação e acompanhamento
- Perfil - Dados pessoais e endereços
- Finalizar pedido - Resumo do pedido com dados pessoais inclusos
- Gerenciar pedidos - Todos os pedidos com possibilidade de filtrar por status

## Componentes Reutilizáveis
- ProductCardComponent - Card de produto com imagem
- OrderFormComponent - Formulário de pedido
- CustomerTableComponent - Tabela com filtros
- AddressSearchComponent - Busca por CEP
- PDFReportComponent - Geração de relatórios
- NotificationService - Toastr + SweetAlert2

## 📱 Funcionalidades Avançadas
## Carrinho de Compras
- Carrinho persistente por usuário
- Migração automática ao fazer login
- Cálculo automático de totais
- Gestão de quantidades

## Sistema de Notificações
- SweetAlert2 para confirmações
- ngx-toastr para notificações rápidas
- Alertas personalizados por tipo (sucesso, erro, info)

## Integração ViaCEP
- Busca automática de endereços por CEP
- Preenchimento automático de campos
- Validação de CEP

## E-mail com Brevo API
- Envio de e-mails transacionais
- Templates para confirmação de pedidos
- Recuperação de senha

## 📄 Licença
Este projeto está licenciado sob a Licença MIT - veja o arquivo LICENSE para detalhes.

## 👥 Equipe desenvolvedora
Maria Luiza - Desenvolvedor Full Stack
GitHub: @mariCareca
Email: Mariaalmei92@gmail.com

Miguel Augusto - Desenvolvedor Full Stack
GitHub: @augustovv
Email: augustot.carvalho@gmail.com