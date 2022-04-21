---
layout: post
title: [SQL] SELECT
category: database
---

### Table of contents
- [데이터 읽기](#데이터-읽기)
	- [기본 형식](#기본-형식)

---

# [데이터 읽기](#데이터-읽기)

## [기본 형식](#기본-형식)
```
SELECT column1, column2, ...
FROM table_name
(WHERE conditions)
(ORDER BY column1, column2, ... ASC | DESC)
```

`SELECT * FROM table_name;`

테이블 전체를 출력함