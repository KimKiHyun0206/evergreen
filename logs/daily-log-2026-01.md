# 📅 2026-01 Learning Log
이번 달의 성장을 기록합니다. 🌱


<details>
<summary>🌱 <b>2026-01-01 (Thu)</b></summary>
<div markdown="1">
  
- 로깅 AOP 구현
- 어느 수준까지 로깅을 해도 될지 연구(모든 것을 로깅하면 비밀번호 처럼 민감한 데이터가 로그에 남을 수 있는데 이를 어떻게 로깅하지 않을지도 연구)
</div>
</details>



<details>
<summary>🌱 <b>2026-01-02 (Fri)</b></summary>
<div markdown="1">
  
- 로깅 메시지 연구
- 로그에 색상을 넣을 수 있는 Logback에 대해서 연구하고 적용해봄.
</div>
</details>



<details>
<summary>🌱 <b>2026-01-03 (Sat)</b></summary>
<div markdown="1">

- Aetheria 프로젝트 Swagger 문서화
</div>
</details>



<details>
<summary>🌱 <b>2026-01-04 (Sun)</b></summary>
<div markdown="1">
  
- Polyline이 GPX 파일을 얼마나 압축하는지 확인함. (약 90% 압축하는 것을 확인)
- 암호화 키 버전 관리 및 로테이션 전략 구현
</div>
</details>


<details>
<summary>🌱 <b>2026-01-05 (Mon)</b></summary>
<div markdown="1">

- 암호화 키 버전 관리 및 로테이션 전략 PR의 코드 리뷰를 코드에 반영.

</div>
</details>

<details>
<summary>🌱 <b>2026-01-06 (Tue)</b></summary>
<div markdown="1">

- Limit Rate 조사 및 연구
- AWS의 기능을 사용하는 것이 좋을지 아니면 Redis로 직접 구현하는 것이 좋을지 조사 및 연구함.

</div>
</details>

<details>
<summary>🌱 <b>2026-01-07 (Wed)</b></summary>
<div markdown="1">

- Aetheria 프로젝트 PR 리뷰 확인 및 답변
- 코드 문서화

</div>
</details>


<details><summary><b>🌱 2026-01-08 (Thu)</b></summary>

- Aethaeia 프로젝트 코드 문서화
</details>

<details><summary><b>🌱 2026-01-09 (Fri)</b></summary>

- 문서화 완료

<img width="907" height="683" alt="image" src="https://github.com/user-attachments/assets/b1a31e70-8c8d-44c0-a0b8-4d92d602b9f0" />

- 코드 리펙토링: 서비스 레이어에서 외부 API 요청, 트랜잭션 제어를 모두 하던 것의 책임을 분리하여 헬퍼 클래스에 책임을 나눔.

</details>

<details><summary><b>🌱 2026-01-10 (Sat)</b></summary>

- **리펙토링 중 클래스를 어디까지 분리해야할지 고민함**: 리펙토링 중 책임을 너무 세세하게 나눌 경우 클래스가 너무 많아서 코드를 처음 보는 사람이 이해하기 힘들 수 있다고 생각하는데, 리펙토링의 목적이 남들이 읽기 쉬운 코드를 작성해야 하는 게 맞는지, 아니면 객체지향 설계 원칙(SCP)에 따라 책임을 세세하게 나눠 클래스를 만드는 것이 좋을지 고민함. 이것이 이해하기 쉬운 코드와 객체지향 설계 사이의 트레이드 오프인지 아니면 객체지향 설계 원칙을 세세하게 지침으로 남들이 읽기 쉬운 코드가 될지 고민함.
</details>
