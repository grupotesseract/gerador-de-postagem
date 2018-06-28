# Gerador de Postagens & Portfólio do Grupo Tesseract

## https://postagem.grupotesseract.com.br/

Template para criação de novas postagens para as mídias sociais.

Utilizando o developer tools do browser, deixe a resolução em 1080x1080 pixels e tire uma print da tela atual, isso gera um arquivo .png pronto para a postagem na mídia social.

Gradientes e sombreamento feitos com CSS3/SASS.

Um dia fazeremos a integração com a conta das mídias sociais, automatizando as postagens.

## Instalação

1. **Clone do projeto**

```
git clone --recurse-submodules https://github.com/Acquati/alabamaot-npccreator
```

2. **Criando o .env do Laravel**

- Áreas que precisam ser configuradas:
```
APP_URL=http://localhost:8082
```
```
DB_CONNECTION=pgsql
DB_HOST=172.17.0.1
DB_PORT=5432
DB_DATABASE=postagem
DB_USERNAME=default
DB_PASSWORD=secret
```

3. **Criando o .env do Laradock**

- Áreas que precisam ser configuradas:
```
# Data Path
Choose storage path on your machine. For all storage systems.
DATA_SAVE_PATH=~/.laradock/postagem
```
```
# PHP_FPM
PHP_FPM_INSTALL_PGSQL=true
```
```
# NGINX
NGINX_HOST_HTTP_PORT=8085
NGINX_HOST_HTTPS_PORT=443
NGINX_HOST_LOG_PATH=./logs/nginx/
NGINX_SITES_PATH=./nginx/sites/
NGINX_PHP_UPSTREAM_CONTAINER=php-fpm
NGINX_PHP_UPSTREAM_PORT=9000
```
```
# POSTGRES
POSTGRES_DB=postagem
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
docker-compose exec postgres createdb -U default postagem
docker-compose exec --user=laradock workspace php artisan migrate
```

5. **NPM**

```
npm install
```
- Caso de erro no pngquant
```
sudo apt-get install libpng-dev
npm install -g pngquant-bin
```

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
git clone https://github.com/grupotesseract/gerador-de-postagem.git
cd gerador-de-postagem
```

2. **Adicionando o Laravel**

```
cd ..
git clone https://github.com/laravel/laravel.git
cd laravel
rm -rf .git
cp -r ./ ~/Documents/gerador-de-postagem
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
