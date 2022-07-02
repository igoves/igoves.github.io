---
title: "morris/lessql - легковесный ORM на PHP"
date: "2020-06-12"
categories: 
  - "php"
tags: 
  - "mapper"
  - "orm"
  - "sql"
---

Lessql является легкой и производительной альтернативой объектно-реляционному отображению для PHP.

- Эффективный глубокий поиск
- Никаких проблем N + 1
- Сохранение сложных вложенных структур одним вызовом метода
- Согласование конфигурации
- Работа в тесной связи с вашей базой данных: LessQL - не ORM
- Чистый, читаемый исходный код
- Полностью протестировано с SQLite3, MySQL и PostgreSQL

Пример:

```
// SCHEMA
// user: id, name
// post: id, title, body, date_published, is_published, user_id
// categorization: category_id, post_id
// category: id, title

// Connection
$pdo = new PDO('sqlite:blog.sqlite3');
$db = new LessQL\Database($pdo);

// Find posts, their authors and categories efficiently:
// Eager loading of references happens automatically.
// This example only needs FOUR queries, one for each table.
$posts = $db->post()
    ->where('is_published', 1)
    ->orderBy('date_published', 'DESC');

foreach ($posts as $post) {
    $author = $post->user()->fetch();

    foreach ($post->categorizationList()->category() as $category) {
        // ...
    }
}

// Saving complex structures is easy
$row = $db->createRow('post', [
    'title' => 'News',
    'body' => 'Yay!',
    'categorizationList' => [
        [
            'category' => ['title' => 'New Category']
        ],
        ['category' => $existingCategoryRow]
    ]
]);

// Creates a post, a new category, two new categorizations
// and connects them all correctly.
$row->save();
```

[https://github.com/morris/lessql](https://github.com/morris/lessql)
