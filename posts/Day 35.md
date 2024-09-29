## 문제 4. 교집합 구하기

PRODUCT 테이블과 OFFLINE_SALE 테이블 PRODUCT_ID 기준으로 교집합 row를 출력해주세요.

```
SELECT *
FROM PRODUCT AS p
	INNER JOIN OFFLINE_SALE AS o
  ON p.PRODUCT_ID = o.PRODUCT_ID;
```

>문제 5는 Day 34에 해결하였음
