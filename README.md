# devLife
A blog for web developers to enhance and improve their lifestyles!


THE FOLLOWING IS A LIST OF THE COMMANDS I USED TO CREATE THIS ENVIRONMENT. I PRAY THAT IT WORKS.

$ curl -s https://laravel.build/projectName | bash
$ cd projectName
$ sail up -d

$ composer require laravel/ui
$ composer require laravel/sail --dev
$ composer require tinker
$ php artisan ui vue --auth 
$ npm install && npm run dev
$ npm run dev (yes, again)

$ php artisan ui bootstrap
$ npm install && npm run dev

$ npm install --save @fortawesome/fontawesome-free

$ npm install && npm run dev
$ npm install laravel-mix@latest 
$ npm install sass-loader@
$ npm install sass

in sass file: 
// Bootstrap
@import "~bootstrap/scss/bootstrap";

//fontawesome
@import "~@fortawesome/fontawesome-free/scss/brands";
@import "~@fortawesome/fontawesome-free/scss/regular";
@import "~@fortawesome/fontawesome-free/scss/solid";
@import "~@fortawesome/fontawesome-free/scss/fontawesome";



in webpack.mix.js file: 
const mix = require("laravel-mix");

mix.js("resources/js/app.js", "public/js")
.vue()
.sass("resources/sass/app.scss", "public/css")
.sourceMaps();



package.json:
{
"private": true,
"scripts": {
"dev": "npm run development",
"development": "mix",
"watch": "mix watch",
"watch-poll": "mix watch -- --watch-options-poll=1000",
"hot": "mix watch --hot",
"prod": "npm run production",
"production": "mix --production"
},
"devDependencies": {
"axios": "^0.21",
"bootstrap": "^4.6.0",
"jquery": "^3.6",
"laravel-mix": "^6.0.31",
"lodash": "^4.17.19",
"popper.js": "^1.16.1",
"postcss": "^8.1.14",
"resolve-url-loader": "^4.0.0",
"sass": "^1.42.1",
"sass-loader": "^11.1.1"
"vue": "^2.6.12",
"vue-loader": "^15.9.8",
"vue-template-compiler": "^2.6.12"
},

"dependencies": {
"@fortawesome/fontawesome-free": "^5.15.4"
}
}

and add to docker-compose.yml file:
phpmyadmin:
        image: phpmyadmin/phpmyadmin:5
        ports:
            - 8080:80
        links:
            - mysql
        environment:
            PMA_HOST: mysql
            PMA_PORT: 3306
        depends_on:
            mysql:
                condition: service_healthy
        networks:
            - sail


$ npm run dev


IF PHPMYADMIN is not working on localhost:8080
	try the following:

$ php artisan cache:clear
$ php artisan config:clear 
$ php artisan route:clear
$ php artisan serve



$ composer require spatie/laravel-permission

add to config/app.php file:

under ‘providers’ => [

	in the section called Package Service Providers, I think…
	Spatie\Permission\PermissionServiceProvider::class,

$ php artisan vendor:publish –provider=”Spatie\Permission\PermissionServiceProvider”

$ php artisan make:migration add_username_to_users_table

$ php artisan config:clear

$ php artisan migrate
