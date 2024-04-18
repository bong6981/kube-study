# EKS 실습
- AWS GUI 기준

## VPC 만들기
- AZ
- subnet
- nat gateway
- vpc endpoint
- dns

## IAM 만들기
- EKS -cluster 역할
- WorkNode 관련 역할 [참고링크](https://docs.aws.amazon.com/ko_kr/eks/latest/userguide/create-node-role.html
)

## EKS cluster 만들기

## 계정 Access key, secret key 생성 후 `aws configure` 업데이트
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

