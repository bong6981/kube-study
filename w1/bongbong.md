# 쿠버네티스가 하는 일 : 컨테이너를 잘 관리할 수 있게 해준다

- 여러 시스템 및 서비스를 자동화하고 하나의 통합된 시스템으로 동작하도록 관리 해주는 일을 오케스트레이션이라고 한다
- 쿠버네티스는 컨테이너를 관리해주도록 하고
- 간단히 말해, 도커있을 때는 각 도커를 하나하나 관리해 줘야 했다면 그것을 클러스터 단위로 묶어서 관리 ( 어떤 서버가 여유있나, 어떤 서버가 죽었나, 어떤 서비스가 어떤 주소를 갖고 있나 문제 생기면 롤백 등)

# M1 에서 Virtualbox 실행 안되는 이유

- [https://velog.io/@480/이제는-개발자도-CPU-아키텍처를-구분해야-합니다](https://velog.io/@480/%EC%9D%B4%EC%A0%9C%EB%8A%94-%EA%B0%9C%EB%B0%9C%EC%9E%90%EB%8F%84-CPU-%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98%EB%A5%BC-%EA%B5%AC%EB%B6%84%ED%95%B4%EC%95%BC-%ED%95%A9%EB%8B%88%EB%8B%A4)
- 인텔이 x-86 계열의 cpu, AMD : 인텔의 x-86 고과 호환되는 cpu 아키텍쳐, arm : 과거 소형 기기에서 사용 (저가격, 저전력) → pc 수준까지 발전 → apple 이 arm cpu 아키텍쳐 기반의 m1 cpu 를 만들었어
- virtual box 는 x-86 기반
- 아키텍처 종류
    - x86 : 인텔기반 32bit CPU
    - x86_64 ( amd64) : Intel 기반 64bit CPU 이며, x86과 호환. 사실상 amd 가 만들었는데 인텔과 크로스 라이센싱해서 둘다 쓴다
    - arm : arm 기반 32bit CPU, x86 과 전혀 호환 안된다
    - arm64 : arm 기반의 64bit CPU. 32bit arm 과 호환
- 모바일은 앱은 arm 아키텍처로 만들어지니까 pc 에서는 안돌아가고 m1 에서 돌아감
- m1에서 Rosseta 라는 에뮬레이터 있어서 일종의 x86 가상 환경 만들어 실행하기 때문에 인텔용 프로그램 돌아감
