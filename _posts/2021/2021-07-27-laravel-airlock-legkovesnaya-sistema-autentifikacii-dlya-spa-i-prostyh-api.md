---
title: "laravel / airlock - легковесная система аутентификации для SPA и простых API"
date: ""
categories: 
  - "php"
tags: 
  - "api"
  - "auth"
  - "laravel"
  - "token"
---

```
use App\\User;
use Illuminate\\Http\\Request;
use Illuminate\\Support\\Facades\\Hash;
use Illuminate\\Validation\\ValidationException;

Route::post('/airlock/token', function (Request $request) {
    $request->validate([
        'email' => 'required|email',
        'password' => 'required',
        'device_name' => 'required'
    ]);

    $user = User::where('email', $request->email)->first();

    if (! $user || ! Hash::check($request->password, $user->password)) {
        throw ValidationException::withMessages([
            'email' => ['The provided credentials are incorrect.'],
        ]);
    }

    return $user->createToken($request->device_name)->plainTextToken;
});
```

  
[https://github.com/laravel/airlock](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2xhcmF2ZWwvYWlybG9jaw%3D%3D)
