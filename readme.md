## Laravel v5.5 Template

- Fixes a lot of Laravel new project issues:
  - Webpack unable to compile due to wrong linked directories
  - Major cleanup in base files
- Includes base controllers and assets:
  - Bootstrap
  - JQuery
  - HTML & Form Laravel packages
- Includes PhpStorm autocompletion for laravel
  - PhpStorm needs the Laravel Plugin installed. Settings -> Plugins -> Search for Laravel Plugin -> Browser Repositories 

### Installation
1) Run `cp .env.example .env`
2) Run `npm run setup` to auto run all the commands usually ran on initial setup :
    * `rm -rf .git; git init`  Removes this repo from the project
    * `cp .env.example .env`  Creates project environment file
  	* `npm install --no-bin-links`  Installs all node dependencies
  	* `composer install`  Installs other project dependencies
  	* `php artisan key:generate`  Creates project encryption key
  	* `npm run dev`  Compiles CSS & JS

### Helpers
Email Template
```
@component('mail::layout')
    @slot('header')
        @component('mail::header')
            Header Title
        @endcomponent
    @endslot

    This is the email body
    
    @component('mail::button', ['url' => '', 'color' => 'green'])
      Button
    @endcomponent

    @slot('footer')
        @component('mail::footer')
            © Copyright
        @endcomponent
    @endslot
@endcomponent
```
