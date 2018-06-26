## Gerador de Postagens

Deixar fácil a criação de novas postagens, utilizando um template onde possamos tirar print pelo developer tools do browser, já na resolução da determinada mídia social.

Talvez um dia fazer a integração com as contas das mídias sociais, automatizando as postagens.

## Passos da criação do projeto

### Clonando a o repositório após criar no github
```
cd Documents
git clone https://github.com/grupotesseract/gerador-de-postagem.git
cd gerador-de-postagem
```

### Adicionando o Laravel
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

### Criando o read.me resumindo a criação do projeto
```
git add .
git commit -m "adicinando o read.me"
ggpush
```

### Criando o .gitignore pelo gitignor.io
```
git add .
git commit -m "adicinando o gitignore"
ggpush
```