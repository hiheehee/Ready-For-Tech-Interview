# SQL Join
* 두개 이상의 테이블이나 데이터베이스를 연결해 데이터를 검색하는 방법

# INNER JOIN
* 교집합  

![INNER](https://user-images.githubusercontent.com/49300728/141489130-a967d534-3516-4f3b-8831-94a492809d67.png)
```sql
SELECT *
FROM TableA A INNER JOIN TableB B ON A.KEY = B.KEY;
```

# LEFT JOIN
![L](https://user-images.githubusercontent.com/49300728/141489129-ecc53889-8b39-42ac-8bd7-f1f84e432b92.png)
```sql
SELECT *
FROM TableA A LEFT OUTER JOIN TableB B ON A.KEY = B.KEY;
```
![L2](https://user-images.githubusercontent.com/49300728/141489128-af99f1fe-8620-4025-b242-2bbde2fba239.png)
```sql
SELECT *
FROM TableA A LEFT OUTER JOIN TableB B ON A.KEY = B.KEY
WHERE B.KEY IS NULL;
```
# RIGHT JOIN
![R1](https://user-images.githubusercontent.com/49300728/141489120-55eb280a-5c13-430e-bd21-fb71d47dd35d.png)
```sql
SELECT *
FROM TableA A RIGHT OUTER JOIN TableB B ON A.KEY = B.KEY;
```
![R2](https://user-images.githubusercontent.com/49300728/141489139-bbbe2255-0906-49a6-8cf4-56ab8bfdb65a.png)
```sql
SELECT *
FROM TableA A LEFT OUTER JOIN TableB B ON A.KEY = B.KEY
WHERE A.KEY IS NULL;
```
# OUTER JOIN 
* 합집합  

![O1](https://user-images.githubusercontent.com/49300728/141489134-c7424df7-7ddf-4d71-a571-fe7c0a58dc27.png)
```sql
SELECT *
FROM TableA A FULL OUTER JOIN TableB B ON A.KEY = B.KEY;
```
![O2](https://user-images.githubusercontent.com/49300728/141489132-9b8a7122-d246-45aa-a5b7-31d39cd5c2f8.png)
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
