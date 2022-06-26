---
title: "Сортируем массив по деревьям"
categories: 
  - "php"
tags: 
  - "array"
  - "tree-sort"
---

```
function crazysort(&$comments, $parentComment = 0, $level = 0, $count = null){  if (is_array($comments) && count($comments)){    $return = array();    if (is_null($count)){      $c = count($comments);    }else{      $c = $count;    }    for($i=0;$i<$c;$i++){      if (!isset($comments[$i])) continue;      $comment = $comments[$i];      $parentId = $comment['parent_id'];      if ($parentId == $parentComment){        $comment['level'] = $level;        $commentId = $comment['id'];        $return[] = $comment;        unset($comments[$i]);        while ($nextReturn = crazysort($comments, $commentId, $level+1, $c)){          $return = array_merge($return, $nextReturn);        }      }    }    return $return;  }  return false;}
```
