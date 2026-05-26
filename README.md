# Auth App

## Sobre o Projeto

Este é um **aplicativo Laravel** de exemplo que permite a gestão de **Posts** associados a **Categorias**. Cada post possui:
- **Título**
- **Descrição** (texto)
- **Imagem** (upload e exibição)
- **Categoria**

O objetivo do projeto é demonstrar um fluxo completo de CRUD, relacionamento entre modelos, upload de arquivos e uma interface responsiva com Blade + TailwindCSS.

## Tecnologias e Versões Utilizadas

- **PHP**: 8.2 (ou superior)
- **Laravel**: 10.x
- **Composer**: 2.x
- **Node.js & npm**: 18.x (para compilar assets Tailwind)
- **MySQL / MariaDB**: 10.5+ (ou outro driver compatível)
- **XAMPP** (Apache, PHP, MySQL) – usado como ambiente local.

## Pré‑requisitos

1. **PHP 8.2+** instalado e configurado no PATH.
2. **Composer** para gerenciamento de dependências PHP.
3. **Node.js** e **npm** para compilar assets (TailwindCSS).
4. **MySQL** (ou outro banco suportado) e um banco de dados criado para a aplicação.
5. **XAMPP** ou outro servidor web que sirva a pasta `public` do Laravel.
6. Extensões PHP necessárias: `ctype`, `json`, `mbstring`, `openssl`, `pdo_mysql`, `tokenizer`, `xml`.

## Instalação

```bash
# 1. Clonar o repositório
git clone https://github.com/SEU_USUARIO/auth-app.git
cd auth-app

# 2. Instalar dependências PHP
composer install

# 3. Copiar o .env de exemplo e gerar a chave da aplicação
cp .env.example .env
php artisan key:generate

# 4. Configurar o banco no .env (DB_DATABASE, DB_USERNAME, DB_PASSWORD)
#    e criar o banco de dados correspondente.

# 5. Executar as migrations (cria tabelas de posts, categorias etc.)
php artisan migrate

# 6. Criar link simbólico para acesso a arquivos armazenados publicamente
php artisan storage:link

# 7. Instalar dependências front‑end (TailwindCSS) e compilar assets
npm install
npm run dev

# 8. Iniciar o servidor de desenvolvimento
php artisan serve
```

A aplicação estará disponível em `http://localhost:8000`.

## Uso da Aplicação

- **Listar Posts**: ao acessar a rota `/posts` são exibidos cards com a imagem (se houver), título, descrição, categoria e botões de *Editar* e *Deletar*.
- **Criar Post**: clique em **Adicionar novo Post**, preencha título, texto, escolha a categoria e, opcionalmente, faça upload de uma imagem (máx. 2 MB, formatos JPEG/PNG/GIF).
- **Editar Post**: o formulário de edição mostra a imagem atual (se existir) e permite substituí‑la ou deixá‑la como está.
- **Deletar Post**: o botão de exclusão remove o registro e, se houver imagem associada, o arquivo é removido do storage.

## Licença

Distribuído sob a licença **MIT**. Veja o arquivo `LICENSE` para mais detalhes.
