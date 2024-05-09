# EKS 실습
- AWS GUI 기준

## VPC 만들기
- VPC 등을 선택
- AZ 2개
- subnet 4개 ( 퍼블릭 2, 프라이빗 2)
- nat gateway (1개의 az) 
- vpc endpoint (없음)
- dns

## IAM 만들기
- EKS -cluster 역할 생성
- WorkNode 관련 역할 [참고링크](https://docs.aws.amazon.com/ko_kr/eks/latest/userguide/create-node-role.html)
    - AmazonEC2ContainerRegistryReadOnly
    - AmazonEKSWorkerNodePolicy 

## EKS cluster 만들기
- 역할에 아까 만들어 둔 역할
- 클러스터 액세스 허용 : 퍼플릭 및 프라이빗 

## AWS CLI 
- 계정 Access key, secret key 생성 후 `aws configure` 업데이트
`~/.aws/config` 파일과 `~/.aws/credential` 파일 수정

```
☁  .aws  aws configure list
      Name                    Value             Type    Location
      ----                    -----             ----    --------
   profile                   saehim              env    ['AWS_PROFILE', 'AWS_DEFAULT_PROFILE']
access_key     ****************WME7 shared-credentials-file
secret_key     ****************noNt shared-credentials-file
    region                us-east-1      config-file    ~/.aws/config

☁  .aws  aws eks update-kubeconfig --region us-east-1 --name eks --profile saehim
Added new context arn:aws:eks:us-east-1:450172767368:cluster/eks to /Users/berapt/.kube/config
```
- 디폴트 프로필 수정 `export AWS_DEFAULT_PROFILE=study`
- 프로필 확인 `aws configure list`
- kube 환경 업데이트 `aws eks update-kubeconfig --region us-east-1 --name eks --profile saehim`
- 연결 확인 `kube get svc`

### default 프로필 바꾸기
`export AWS_DEFAULT_PROFILE={profile}`
