# Join

논리 조인은 SQL 문을 작성할 때 직접 쿼리에 사용된다. 
반면 물리 조인은 이것이 실행될 때 내부적으로 어떻게 동작하는지에 대한 이야기다. 
옵티마이저가 통계 등을 기반으로 물리 조인 중 어떤 것을 사용할지 결정하게 된다.

## 논리 조인
- Inner Join: 두 테이블에 모두 있는 값을 기준으로 조인한다.
- Left Outer Join: 왼쪽 테이블을 기준으로 조인하고, 오른쪽 테이블 값은 Null이 될 수 있다.
- Right Outer Join: 오른쪽 테이블을 준으로 조인하고, 왼쪽 테이블 값은 Null이 될 수 있다. 
- Full Outer Join: 양쪽 값 모두 Null이 될 수 있다.
  
## 물리 조인
- Nested Loops join
- Sorted Merge join
- Hash join

  
