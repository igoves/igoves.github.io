---
title: "laravel-user-verification - пакет laravel для верификации и валидации email"
date: ""
categories: 
  - "php"
---

```
public function register(Request $request)
{
	$this->validator($request->all())->validate();
	$user = $this->create($request->all());
	event(new Registered($user));
	$this->guard()->login($user);
	UserVerification::generate($user);
	UserVerification::send($user, 'My Custom E-mail Subject');
	return $this->registered($request, $user)
					?: redirect($this->redirectPath());
}
```

  
[https://github.com/jrean/laravel-user-verification](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2pyZWFuL2xhcmF2ZWwtdXNlci12ZXJpZmljYXRpb24%3D)
