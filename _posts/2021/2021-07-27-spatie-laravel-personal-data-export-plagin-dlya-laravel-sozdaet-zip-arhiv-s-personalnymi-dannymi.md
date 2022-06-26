---
title: "spatie/laravel-personal-data-export - плагин для laravel создает zip архив с персональными данными"
date: ""
categories: 
  - "php"
tags: 
  - "laravel"
  - "personal-data"
---

```
// in your User model

public function selectPersonalData(PersonalDataSelection $personalDataSelection) {
    $personalDataSelection
        ->add('user.json', ['name' => $this->name, 'email' => $this->email])
        ->addFile(storage_path("avatars/{$this->id}.jpg");
        ->addFile('other-user-data.xml', 's3');
}
```

  
[https://github.com/spatie/laravel-personal-data-export](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3NwYXRpZS9sYXJhdmVsLXBlcnNvbmFsLWRhdGEtZXhwb3J0)
