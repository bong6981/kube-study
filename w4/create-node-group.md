### ekctl 설치 
https://docs.aws.amazon.com/ko_kr/emr/latest/EMR-on-EKS-DevelopmentGuide/setting-up-eksctl.html

### cli로 node group 생성
https://docs.aws.amazon.com/ko_kr/eks/latest/userguide/create-managed-node-group.html

### 우리는 직접 생성
https://kschoi728.tistory.com/84

#### node group 생성시 오류
- node group 생성 subnet이 public 일 때 에러가 남
  - public subnet에서 퍼블릭 IPv4 주소 자동 할당 옵션을 켜줌
  - public subnet에서만 node group 생성
- 
