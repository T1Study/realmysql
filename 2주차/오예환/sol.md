- 조건에 부합하는 중고거래 댓글 조회하기

  ```sql
  SELECT b.TITLE, b.BOARD_ID, r.REPLY_ID, r.WRITER_ID, r.CONTENTS, DATE_FORMAT(r.CREATED_DATE, '%Y-%m-%d') as CREATED_DATE
  FROM USED_GOODS_BOARD as b
      JOIN USED_GOODS_REPLY as r
      ON b.BOARD_ID = r.BOARD_ID
  WHERE DATE(b.CREATED_DATE) BETWEEN '2022-10-01' AND '2022-10-31'
  ORDER BY r.CREATED_DATE ASC, b.TITLE ASC;
  ```

  → WHERE절에서 r.CREATED_DATE로 비교를해서 애를 먹었음….

- 모든 레코드 조회하기

  ```sql
  SELECT * FROM ANIMAL_INS
  ORDER BY ANIMAL_ID;
  ```

- 여러 기준으로 정렬하기

  ```sql
  SELECT ANIMAL_ID, NAME, DATETIME FROM ANIMAL_INS
  ORDER BY NAME ASC, DATETIME DESC;
  ```

  → ORDER BY 다중 정렬 이용

- 이름이 있는 동물의 아이디

  ```sql
  SELECT ANIMAL_ID FROM ANIMAL_INS
  WHERE NAME IS NOT NULL
  ORDER BY ANIMAL_ID ASC;
  ```

  → WHERE 칼럼 IS NULL

  → WHERE 칼럼 IS NOT NULL

- 상위 n개 레코드
  ```sql
  SELECT NAME FROM ANIMAL_INS
  ORDER BY DATETIME ASC LIMIT 1;
  ```
  → ORDER BY, ASC, LIMIT 정확한 사용법을 몰라서 검색해서 작성
