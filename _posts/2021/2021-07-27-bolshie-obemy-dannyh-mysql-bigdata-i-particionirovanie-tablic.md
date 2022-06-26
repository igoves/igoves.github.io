---
title: "Большие обьемы данных MySQL (bigdata) и партиционирование таблиц"
date: ""
categories: 
  - "note"
tags: 
  - "mysql"
---

Столкнулся с проблемой больших обьемов данных в MySQL. На помощь пришла относительно новая возможность mysql партицирование данных. Если коротко, то это разбиение таблиц на логические части по определенным критериям. И дает это прирост скорости работы с таблицами.  
  
Смотрим поддерживается ли у нас:

```
HOW VARIABLES LIKE '%partition%';have_partitioning | YES
```

  
  
Какие способы «разделения» данных предоставляет mySQL?  
**1\. RANGE**  
По диапазону значений

```
PARTITION BY RANGE (store_id) ( PARTITION p0 VALUES LESS THAN (10), PARTITION p1 VALUES LESS THAN (20), PARTITION p3 VALUES LESS THAN (30) );
```

  
**2\. LIST**  
По точному списку значений

```
 PARTITION BY LIST(store_id) ( PARTITION pNorth VALUES IN (3,5,6,9,17), PARTITION pEast VALUES IN (1,2,10,11,19,20) )
```

  
**3\. HASH**  
Вы никак не управляете партицированием, просто указываете, по какому полю строить хеш и сколько «подтаблиц» создавать.

```
 PARTITION BY HASH(store_id) PARTITIONS 4;
```

  
**4\. KEY**  
Почти то же самое что и HASH, но более логично — по ключу.

```
 PARTITION BY KEY(s1) PARTITIONS 10;
```

  
Первый раз я попробовал разбить по RANGE DATETIME.

```
ALTER TABLE flowsPARTITION BY RANGE( TO_DAYS(date) ) ( PARTITION y2013m10 VALUES LESS THAN( TO_DAYS('2013-10-01') ), PARTITION y2013m11 VALUES LESS THAN( TO_DAYS('2013-11-01') ), PARTITION y2013m12 VALUES LESS THAN( TO_DAYS('2013-12-01') ));
```

  
  
Но получил:

```
[Error] 1503 - A PRIMARY KEY must include all columns in the table partitioning function
```

  
  
Вылез неприятный момент из за того что, поле по которому делаются партиции должно быть PRIMARY KEY, то есть уникальным.  
А данные в таблицу пишутся не прерывно и вполне возможно что в 1 секунду писаться несколько значений. поэтому такое разделение мне не подойдет =(  
  
Решено было найти id где заканчиваются года и сделать альтер по ним, как-то так. То есть разделение будет до 2013 года и после. При необходимости можно разбить мельче.

```
ALTER TABLE flowsPARTITION BY RANGE (id) (	PARTITION y2013 VALUES LESS THAN( 231607217 ),	PARTITION y2014 VALUES LESS THAN(MAXVALUE));
```

  
Что мы получаем? Первая «таблица» будет хранить данные за «архивный» период, до 2013 года, вторая — все остальное.  
  
Столкнулся в процессе использования что бекап генериться неправильный, в таблицах где есть разбиение вставляется автоинкримент не в то место. Поэтому надо переставлять руками, но это не есть большая проблема.  
  
И ликбез: http://www.rldp.ru/mysql/mysqlpro/parts.htm
