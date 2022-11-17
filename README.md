# About This Auth and JWT
- i use jwt token from this repository https://github.com/tymondesigns/jwt-auth
- i use table user default that laravel created in migration

#case 1 
-  when i install tymondesigns/jwt-auth, i got error not supported for laravel 8. then i use this for installing tymondesigns/jwt-auth

$ composer require tymon/jwt-auth --ignore-platform-reqs

- after installation i use this documentation for setting the tymond design in my laravel project: https://jwt-auth.readthedocs.io/en/docs/laravel-installation/

- mulai gunakan jwt: https://jwt-auth.readthedocs.io/en/docs/quick-start/

- membuat authcontroller: 
php artisan make:controller AuthController

- menambahkan Route ini di routes/api.php

Route::group(['middleware' => 'api', 'namespace' => 'App\Http\Controllers', 'prefix' => 'auth'], function ($router) {
    Route::post('login', [AuthController::class, 'login']);
    Route::post('logout', [AuthController::class, 'logout']);
    Route::post('register', [AuthController::class, 'register']);
    Route::post('refresh', [AuthController::class, 'refresh']);
    Route::post('me', [AuthController::class, 'me']);
});

