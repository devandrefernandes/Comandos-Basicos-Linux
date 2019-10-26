# Comandos-Basicos-Linux
Lista de comandos básicos do Linux | Laravel | GIT

## Git:
> Baixar branch:
```bash
    git checkout dev
    git pull
```
> Alterar repositório local para o mesmo do branch:
 ```bash
    git checkout -b nome­novo­branch
```
> Após as alterações no branch, alterar repositório para dev:
```bash
    git add .
    git commit -m "Descrição"
    git push

    git checkout dev
```
> Baixar possíveis alterações:
```bash
    git pull
```
> Fazer o merge:
```bash
    git merge nome­novo­branch
```
> Fazer o push:
```bash
    git push
```
> Status modificações:
```bash
    git status
```
> Não permitir enviar arquivos com apenas a permissão alterada:
```bash
    git config core.filemode false
```
> Visualizar origem:
```bash
    git remote -v
```
> Alterar origem do projeto para ssh:
```bash
    git remote set-url origin ssh://git@gitlab...:2200/pasta/.git
```
> Revert merge:
```bash
    git reset --soft|mixed|hard branch
    git stash
    git revert hash-do-ultimo-commit
    git stash pop/apply
```
> Stash
```bash
    git stash
    git stash pop
```
### Chave SSH gitlab
> Verificar se existe chave ssh:
```bash
cat ~/.ssh/id_rsa.pub
```
> Adicionar par de chave ssh:
```bash
ssh-keygen -t rsa -C "email@example.com" -b 4096
```
> Copiar par de chave ssh para a área de transferência:
```bash
xclip -sel clip < ~/.ssh/id_rsa.pub
```
> Adicionar chave ssh no gitlab:
```bash
Menu 'Settings' -> 'SSH Keys'
```
> Testar configuração ssh:
```bash
ssh -T git@gitlab.com -p 2200
```
### Configurações globais - first-time
```bash
git config --global user.name "Nome Usuário"
git config --global user.email "email.usuario@gdax.com.br"
git config --global color.ui true
```

## Linux:
```bash
 - Root:
    sudo su
 
 - Refresh:
    sudo apt update
 
 - PHP padrão:
    sudo update-alternatives --set php /usr/bin/php5.6
 
 - PHP disable:
    sudo a2dismod php5.6

 - PHP enable:
    sudo a2enmod php7.1

 - Apache restart:
    sudo systemctl restart apache2
    sudo service apache2 restart

 - Install php7.1:
    sudo apt-get install php7.1 php7.1-common
    if needed you can remove old packages: sudo apt-get purge php7.0 php7.0-common
```

## Laravel:
```bash 
 - Hosts(pasta etc):
    host: 127.0.0.1   projLaravel

 - Permission:
    sudo chgrp -R www-data storage bootstrap/cache
    sudo chmod -R ug+rwx storage bootstrap/cache

 - Migrations:
    create migrations:
        php artisan make:migration create_users_table
    
    alter tables by migrations:
        php artisan make:migration alter_table_books --table=books
    
    execute migrations:
        php artisan migrate
    
    status migrations:
        php artisan migrate:status
    
    rollback migrations:
        php artisan migrate:rollback
    
    help migrations:
        php artisan | grep migrat
 
 - Seed
	php artisan db:seed
 
 - Cria seed:
	php artisan make:seeder UsersTableSeeder
 
 - Passport:
	php artisan passport:install
	php artisan passport:client --password

 - Rewrite
	sudo a2enmod rewrite

 - nginx:
    sudo service nginx restart
    sudo service nginx status
```
## PHP Artisan
```bash
 - Help:
    php artisan list
 
 - Controllers:
    create controllers:
    php artisan make:controller API/AccessGroupController --resource
 
 - Models:
    create models:
    php artisan make:model Models/AccessGroup

 - Repository:
    create repositorys:
    php artisan make:repository AccessGroupRepository

 - BO:
    create BO:
    php artisan make:BO AccessGroupBO

 - GCRUD blade:
    php artisan make:gcrud nomeModulo

 - Cache:
    php artisan cache:clear
    php artisan config:clear
    php artisan route:clear
```

## VueJs
```bash
 - Deploy
     git pull - api e front
     npm run build -- --mode development --dest pasta_destino
     rm -R dist_old/ && mv dist/ dist_old/ && mv pasta_destino/ dist/
```
## Nginx
Configurar virtualhost.
> Duplicar arquivo available/default com um novo nome:
```bash
cp /etc/nginx/sites-available/default /etc/nginx/sites-available/compreclaro.local
```
> Alterar arquivo criado acima:
```bash
server_name nomeaplicacao.local;
root /caminho/www/nomeaplicacao/public;
index index.php index.html inde.htm;
```
> Criar link simbólico:
```bash
cd /etc/nginx/sites-enabled
ln -s /etc/nginx/sites-available/compreclaro.local
```
> Configurar hosts
```bash
vim /etc/hosts
127.0.0.1 nomeaplicacao.local
```
> Restart serviço:
```bash
service nginx restart
```
> Acessar aplicacao
```bash
nomeaplicacao.local:81
```
