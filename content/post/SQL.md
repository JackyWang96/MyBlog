---
title: "SQL"
date: 2023-01-10T01:51:14+11:00
draft: flase
---

SQL experience

1. When combining tables, the efficiency of simply using the where statement is lower than join, which is equivalent to full join

left join (left join): Returns all records including all records in the left table and records with equal join fields in the right table.

right join (right join): Returns all records including all records in the right table and records with equal join fields in the left table.

Inner join (equivalent connection or inner connection): only returns the rows with the same connection fields in the two tables.

full join (full outer connection): Return all records in the left and right tables and records with the same connection fields in the left and right tables.

2. The way to use Null is Where xxxx is null

3. Use limit 1, 1 to filter the second and third data that meet the conditions. eg. the second largest, the second highest