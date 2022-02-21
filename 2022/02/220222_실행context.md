# 실행문맥
함수가 실행되는 환경

GO - 빌트인객체, BOM, DOM, 전역변수
AO - 함수선언, 매개변수, 변수
GO, AO, this가 형성될 때 Scopechain (단방향 연결해줌) 진행됨 → 이 때문에 호이스팅이 가능

변수 쉐도잉 : 가장 가까운 변수를 참조
scope chain - inner scope에서 outer scope로 나아가면서 연결