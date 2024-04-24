### ekctl 설치 
https://docs.aws.amazon.com/ko_kr/emr/latest/EMR-on-EKS-DevelopmentGuide/setting-up-eksctl.html

### cli로 node group 생성
https://docs.aws.amazon.com/ko_kr/eks/latest/userguide/create-managed-node-group.html

### 우리는 직접 생성
https://kschoi728.tistory.com/84

#### node group 생성시 오류
- node group 생성 subnet이 public 일 때 에러가 남
  - 생성한 vpc의 public subnet에서 퍼블릭 IPv4 주소 자동 할당 옵션을 켜줌
  - 해당 public subnet으로 node group 생성하는 것으로 해결
 
```
One or more Amazon EC2 Subnets of [subnet-0b21c02b2160dd553, subnet-00bb4c0b0ee941b9e] for node group kube-study-node-group does not automatically assign public IP addresses to instances launched into it. If you want your instances to be assigned a public IP address, then you need to enable auto-assign public IP address for the subnet. See IP addressing in VPC guide: https://docs.aws.amazon.com/vpc/latest/userguide/vpc-ip-addressing.html#subnet-public-ip
```

- 성공!!
```
☁  ~  kubectl get node
NAME                          STATUS   ROLES    AGE    VERSION
ip-10-0-10-168.ec2.internal   Ready    <none>   6m8s   v1.29.0-eks-5e0fdde
ip-10-0-16-15.ec2.internal    Ready    <none>   6m6s   v1.29.0-eks-5e0fdde
ip-10-0-4-240.ec2.internal    Ready    <none>   6m6s   v1.29.0-eks-5e0fdde
```

---
## eks에서 실습해보기
- pod 생성해보기 실습
- pod yaml로 생성해보기 실습
- pod yaml에 컨테이너 추가해보기 실습
- 
