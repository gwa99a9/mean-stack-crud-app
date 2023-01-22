# MEAN Stack Crud App

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 14.0.4.

![demo](demo/demo.gif)


## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

# Setup Nodejs Environment for Ubuntu 20

    curl https://gist.githubusercontent.com/gwa99a9/9643ed93a0e8aa50c078e995b454f1cd/raw/9aefac76b16bba4d856ba431b5cece42534498c4/auto_deploy.sh | sudo bash
    export NVM_DIR=~/.nvm
    source ~/.nvm/nvm.sh


Git clone the project

    git clone https://github.com/gwa99a9/mean-stack-crud-app.git

Install dependencies

    cd mean-stack-crud-app
    cd frontend
    npm install

    cd ..
    cd backend
    npm install

Start the backend server

    cd ..
    cd backend
    pm2 start server.js

Build frontend

    cd ..
    cd frontend
    npm run build

Move the front end into www

    mv dist/mean-stack-crud-app/*  /var/www/html/

Map **/api/** into **localhost:4000** for backend

    sudo nano /etc/nginx/sites-available/default
    	location /api/ {
    		proxy_pass http://localhost:4000/;
    	}
    sudo systemctl restart nginx

