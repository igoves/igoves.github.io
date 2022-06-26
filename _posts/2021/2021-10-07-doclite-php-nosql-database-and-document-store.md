---
title: "doclite - PHP NoSQL database and document store"
date: "2021-10-07"
categories: 
  - "php"
tags: 
  - "database"
  - "nosql"
  - "sqlite"
---

```
// Create a new User in the collection
$user = $users->get();

// Get the automatically generated document ID
$id = $user->getId();

// Set properties by magic set* methods
$user->setUsername("dwgebler");
$user->setRole("admin");
$user->setPassword(password_hash("admin", \PASSWORD_DEFAULT));
$user->setCreated(new \DateTimeImmutable);

// Update the user in the collection
$user->save();

// Retrieve this user later on by ID
$user = $users->get($id);

// Or search for a user by any field
$user = $users->findOneBy(["username" => "dwgebler"]);
```

[https://github.com/dwgebler/doclite](https://github.com/dwgebler/doclite)
