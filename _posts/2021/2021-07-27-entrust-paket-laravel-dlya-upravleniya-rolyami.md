---
title: "entrust - пакет laravel для управления ролями"
categories: 
  - "php"
---

```
$createPost = new Permission();
$createPost->name         = 'create-post';
$createPost->display_name = 'Create Posts'; // optional
// Allow a user to...
$createPost->description  = 'create new blog posts'; // optional
$createPost->save();

$editUser = new Permission();
$editUser->name         = 'edit-user';
$editUser->display_name = 'Edit Users'; // optional
// Allow a user to...
$editUser->description  = 'edit existing users'; // optional
$editUser->save();

$admin->attachPermission($createPost);
// equivalent to $admin->perms()->sync(array($createPost->id));

$owner->attachPermissions(array($createPost, $editUser));
// equivalent to $owner->perms()->sync(array($createPost->id, $editUser->id));
```

  
[https://github.com/Zizaco/entrust](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL1ppemFjby9lbnRydXN0)
