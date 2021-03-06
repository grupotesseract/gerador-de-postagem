# Portfólio do Grupo Tesseract & Gerador de Postagens

## https://portfolio.grupotesseract.com.br/

**Portfólio do Grupo Tesseract**
**+**
**Template para criação de novas postagens para as mídias sociais.**

Portfólio dos projetos realizados pelo Grupo Tesseract. Esse portfólio foi criado utilizando Reveal.js, JQuery, Laravel 5.6, Laradock, SASS e NPM. 

**Gerador de Postagens**

1. Clique no ícone do olho para esconder o menu.
2. Utilizando o developer tools do browser,  deixe a resolução em 1080x1080 pixels.
3. No menu de opções, clique em Take Screenshot, isso gera um arquivo .png pronto para a postagem da imagem na mídia social.

Gradientes e sombreamento feitos com CSS3/SASS.

## Instalando o Projeto

1. **Clone do projeto**

```
git clone --recurse-submodules https://github.com/grupotesseract/portfolio
```

2. **Criando o .env do Laravel**

- **Áreas que precisam ser configuradas:**
```
APP_URL=http://localhost:8080
```
```
DB_CONNECTION=pgsql
DB_HOST=172.17.0.1
DB_PORT=5432
DB_DATABASE=portfolio
DB_USERNAME=default
DB_PASSWORD=secret
```

3. **Criando o .env do Laradock**

- **Áreas que precisam ser configuradas:**
```
# Data Path
Choose storage path on your machine. For all storage systems.
DATA_SAVE_PATH=~/.laradock/portfolio
```
```
# PHP_FPM
PHP_FPM_INSTALL_PGSQL=true
```
```
# NGINX
NGINX_HOST_HTTP_PORT=8080
```
```
# POSTGRES
POSTGRES_DB=portfolio
POSTGRES_USER=default
POSTGRES_PASSWORD=secret
POSTGRES_PORT=5432
```

4. **Comandos pasta Laradock**

```
cd laradock
docker-compose up -d nginx php-fpm postgres
docker-compose exec --user=laradock workspace composer install
docker-compose exec --user=laradock workspace php artisan key:generate
```

5. **Migrate do DB**

```
docker-compose exec --user=laradock workspace php artisan migrate
```
- Caso o Laradock não crie o DB automaticamente, crie manualmente:
```
docker-compose exec postgres createdb -U default portfolio
docker-compose exec --user=laradock workspace php artisan migrate
```

6. **NPM**

```
npm install
```
- Caso de erro no pngquant
```
sudo apt-get install libpng-dev
npm install -g pngquant-bin
```

## Próximos passos do projeto

- Adicionar o favicon.
- Otimizar o loading time, minificando os arquivos.
- Fazer um tutorial de como tirar os prints pelo developer tools.
- Fazer o tutorial de como alterar as imagens, cores e gradientes.
- Adicionar no header um link para o site do projeto que esta sendo visualizado.
- Adicionar autenticação de usuário.
- Criar um espaço para criação do portfólio do usuário.
- Criar mais templates UI/UX.
- Criar um índice no read.me.
- Login com a conta do Facebook e Google.
- Usar os arquivos em SASS do reveal.js.

## Referências e Ferramentas

- **Color Picker**
https://www.w3schools.com/colors/colors_picker.asp

- **CSS3 Gradients**
https://www.w3schools.com/css/css3_gradients.asp

- **Material Design Box Shadows - Codepen**
https://codepen.io/sdthornton/pen/wBZdXq

- **Reveal.js**
https://revealjs.com/ 

- **Laravel**
https://laravel.com/

- **Laradock**
https://laradock.io/

## Passos da criação de um projeto Laravel com Laradock

1. **Clonando a o repositório após cria-lo no GitHub**

```
cd Documents
git clone https://github.com/grupotesseract/portfolio.git
cd portfolio
```

2. **Adicionando o Laravel**

```
cd ..
git clone https://github.com/laravel/laravel.git
cd laravel
rm -rf .git
cp -r ./ ~/Documents/portfolio
git add .
git commit -m "adicionando laravel"
ggpush
```

3. **Criando o read.me resumindo a criação do projeto**

```
git add .
git commit -m "adicinando o read.me"
ggpush
```

4. **Criando o .gitignore pelo gitignor.io**

- https://www.gitignore.io/api/node,laravel

```
git add .
git commit -m "adicinando o gitignore"
ggpush
```

5. **Adicionando o Laradock como sub-módulo**

```
git submodule add https://github.com/laradock/laradock.git
git add .
git commit -m "adicionando o laradock como sub-módulo"
ggpush
```
