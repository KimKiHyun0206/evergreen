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

<details><summary><b>🌱 2026-01-11 (Sun)</b></summary>

- 예외 클래스 및 예외 Enum 분리: 이전에 다음과 같은 리뷰를 받음.
  - 우선 Error handling은 협업 단계에서 사전에 정의를 하고 들어가, 그래서 프로젝트마다 다른 경우도 존재하고 다만 지금 에러 처리 방식은 모든 도메인이 BussinessException을 통해서 처리되고 있어서 이는 해당 클래스의 책임이 너무 커지고 있어 각 도메인별 커스텀 예외를 만들어보는건 어떨까? 그리고 에러코드, 에러 메세지 형식으로 에러 처리중인데 같은 에러를 처리해도 에러 메세지를 직접 다시 적어야하는 문제가 있어 일반적으로는 ErrorCode에 도메인별 에러 메세지, 에러 코드를 합친 Enum으로 관리하는 방식으로 진행해
- 이 리뷰에 따라 기존에 `BusinessException`에 과도한 책임이 몰려있던 것을 `UserException`, `AuthException` 등의 예외 클래스로 세분화하고 에러 메시지 또한 `UserErrorCode`, `AuthErrorCode` 등으로 세분화하여 관리할 수 있도록 함.
- 이에 따라서 어느 정도로 세분화 할지도 고민함(JWT와 OAUTH는 같은 인증인데 `AuthException`에 둘 것인가?), 이에 대한 결론으로 세분화하기로 함. OAUTH 중 외부 API를 사용하는 부분에서 발생하는 예외와 JWT 예외를 분리하도록 함.
</details>

<details><summary><b>🌱 2026-01-12 (Mon)</b></summary>

- 프로젝트 진행 중 기존에 `List`로 반환하던 것을 `Page`로 반환하도록 리펙토링: `Page`로 읽어오고 반환하는 것이 대규모 데이터 읽기에 더 적합하기 때문.
- `Slice`와 `Page`의 개념에 대해서 공부하고 프로젝트 방향성에 따라서 `Page`에서 `Slice`로 변경할 것.
</details>

<details><summary><b>🌱 2026-01-13 (Tue)</b></summary>

- 커스텀 어노테이션으로 헤더에서 토큰(AT, RT)를 추출하는 방법을 연구함. 이를 통해 컨트롤러에 중복되는 토큰 추출 메소드를 구현하지 않아도 되게 되었음.
- 기존에 리프레시 토큰을 저장하던 방법이 사용자 경험이 떨어지는 것을 우려해 다른 방식을 도입하는 것을 고려하고 연구함.
</details>

<details><summary><b>🌱 2026-01-14 (Wed)</b></summary>

### 리프레시 토큰 블랙리스트 구현
- 리프레시 토큰을 사용하면 리프레시 토큰의 유효기간만큼 Redis에 블랙리스트를 등록해서 재사용 시 토큰이 무효화되도록 함.
- 그리고 Redis의 원자성을 지키는 방법에 대해서 조사하고 연구함. 향후 프로젝트에 적용해볼 계획. 

</details>

<details><summary><b>🌱 2026-01-15 (Thu)</b></summary>

- 리프레시 토큰 블랙리스트 구현 리펙토링
</details>

<details><summary><b>🌱 2026-01-16 (Fri)</b></summary>

- 리프레시 토큰 블랙리스트 구현 PR 리뷰 내용 반영 후 `develop`브랜치로 `merge`
</details>

<details><summary><b>🌱 2026-01-17 (Sat)</b></summary>

- **JWT 암호화 비즈니스 로직 구현**: 기존에는 JWT를 복호화해서 안의 내용물을 모두 확인할 수 있었다. 하지만 이는 보안에 위협이 될 수 있기 때문에 JWT 안의 내용(발급 시간과 유효 시간 제외)을 암호화하여 페이로드에 저장하도록 하였다.
- **AWS 배포 문서화**: 런닝 아트 서비스 AWS 설계 명세 문서 작성
</details>

<details><summary><b>🌱 2026-01-18 (Sun)</b></summary>

- **AWS 인스턴스 공부**: EC2, ECS, ECR, Fargate에 대해서 학습함.
</details>

<details><summary><b>🌱 2026-01-19 (Mon)</b></summary>

- **AWS WAF 학습**: WAF가 어떤 기능을 가지고 있어 서버를 구성하는데 어떻게 사용되는 것이 좋은지 학습.
</details>

<details><summary><b>🌱 2026-01-20 (Tue)</b></summary>

- AWS ElastiCache 학습
- Redis에 저장할 때 JSON으로 저장하는 것과 바이너리로 저장하는 것의 장단점을 공부함.
</details>
