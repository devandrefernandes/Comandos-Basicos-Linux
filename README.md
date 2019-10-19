# Comandos-Basicos-Linux
Lista de comandos básicos do Linux | Laravel | GIT

# Comandos Básicos

## Git:
```bash
 - Baixar branch:
    git checkout dev
    git pull

 - Alterar repositório local para o mesmo do branch:
    git checkout -b nome­novo­branch
    EX nome(Demanda-Descrição): 28233-AlterarRegraByside

 - Após as alterações no branch, alterar repositório para dev:
    git add .
    git commit -m "Descrição demanda"
    git push

    git checkout dev

 - Baixar possíveis alterações:
    git pull
 
 - Fazer o merge:
    git merge nome­novo­branch
 
 - Fazer o push:
    git push

 - Status modificações:
    git status
 
 - Não permitir enviar arquivos com apenas a permissão alterada:
    git config core.filemode false
 
 - Visualizar origem:
    git remote -v
 
 - Alterar origem do projeto para ssh:
    git remote set-url origin ssh://git@gitlab...:2200/pasta/.git
 
 - Revert merge:
    git reset --hard HEAD~1
 
 - Stash
    git stash
    git pull
    git stash pop
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
