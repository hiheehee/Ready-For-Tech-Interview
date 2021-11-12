# SQL Join
* 두개 이상의 테이블이나 데이터베이스를 연결해 데이터를 검색하는 방법

# INNER JOIN
* 교집합

```sql
SELECT *
FROM TableA A INNER JOIN TableB B ON A.KEY = B.KEY;
```

# LEFT JOIN
```sql
SELECT *
FROM TableA A LEFT OUTER JOIN TableB B ON A.KEY = B.KEY;
```
```sql
SELECT *
FROM TableA A LEFT OUTER JOIN TableB B ON A.KEY = B.KEY
WHERE B.KEY IS NULL;
```
# RIGHT JOIN
```sql
SELECT *
FROM TableA A RIGHT OUTER JOIN TableB B ON A.KEY = B.KEY;
```

```sql
SELECT *
FROM TableA A LEFT OUTER JOIN TableB B ON A.KEY = B.KEY
WHERE A.KEY IS NULL;
```
# OUTER JOIN
* 합집합
```sql
SELECT *
FROM TableA A FULL OUTER JOIN TableB B ON A.KEY = B.KEY;
```

```sql
SELECT *
FROM TableA A FULL OUTER JOIN TableB B ON A.KEY = B.KEY
WHERE A.KEY IS NULL OR B.KEY IS NULL;
```

# CROSS JOIN
* 모든 경우의 수
```sql
SELECT *
FROM TableA A CROSS JOIN TableB B ON A.KEY = B.KEY;
```

```sql
SELECT *
FROM TableA A, TableB B;
```

# SELF JOIN
* 자기 자신과 JOIN
