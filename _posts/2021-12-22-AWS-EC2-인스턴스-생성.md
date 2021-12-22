---
layout: post
title: (YuldoStudy) AWS - EC2 인스턴스 생성
subtitle : AWS - EC2에서 인스턴스 생성 과정과 탄력적ip 설정
tags: [yuldo study, aws]
author: mirutree
comments : True
---
   
   
#### EC2(Amazon EC2)란? (위키백과 참고)
 - EC2는 Amazon Elastic Compute Cloud의 약자로 AWS(아마존 웹 서비스)에서 제공하는 서비스이다.
 - 사용자가 가상 컴퓨터를 임대받아 그 위에 자신만의 애플리케이션을 실행할 수 있게 한다.
 - 사용자가 AMI(아마존 머신 이미지)로 부팅하여 아마존이 "인스턴스"라 부르는 가상 머신을 원하는 소프트웨어를 포함하여 구성할 수 있게 하는 웹 서비스를 제공한다.
 - [EC2 공식 가이드](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html)
   
#### EC2 인스턴스 생성
 - **AWS에 가입 후 로그인하여 관리콘솔에서 EC2를 선택한다**
  <br />![image](https://user-images.githubusercontent.com/63778557/147049972-0a4ac171-ae94-4f00-8e03-15a320ac9491.png)
      
 - **우측 위에서 Region을 선택한다.**
  ![image](https://user-images.githubusercontent.com/63778557/147053659-a821ddb1-83d5-44be-a60f-ee5d4ed6d257.png)
    - AWS 는 Region 별로 리소스를 제공한다. 한국 리전은 `ap-northeast-2`   
    - [region에 대한 공식 가이드](https://docs.aws.amazon.com/ko_kr/AWSEC2/latest/UserGuide/using-regions-availability-zones.html)   
   
 - **좌측 메뉴에서 인스턴스를 선택한다.**  
 ![image](https://user-images.githubusercontent.com/63778557/147050398-bf0dfa83-704a-4e3c-8d5d-a39139ef692b.png)
   
 - **기존 인스턴스가 있다면 요금이 부과되지 않도록(...) 인스턴스를 종료하고 1분 정도 기다린다.**
  ![image](https://user-images.githubusercontent.com/63778557/147053390-5e5704f7-7d44-403d-9190-a8473f037f67.png)
   
 - **단계1 AMI선택**
 ![image](https://user-images.githubusercontent.com/63778557/147054200-a0a1ea1f-27b3-47e1-bb97-34c074596d81.png)
    - Ubuntu Server 18.04를 선택한다
   
 - **단계2 인스턴스 유형 선택**
  ![image](https://user-images.githubusercontent.com/63778557/147054876-9ec8dec9-77e8-43bb-91b7-3834b60bad69.png)
    - 프리티어 사용 가능 선택 후 다음을 누른다 
   
 - **단계3 인스턴스 세부 정보 구성**
  ![image](https://user-images.githubusercontent.com/63778557/147056076-7c023331-954a-4815-8430-a7d3c0564e49.png)
    - 다음 선택
    
  - **단계4 스토리지 추가**
   ![image](https://user-images.githubusercontent.com/63778557/147056519-23f57a0f-387f-4d42-86fa-84418c2170d2.png)
    - 크기는 30, (무료이기 때문에) 볼륨 유형은 범용 SSD로 선택 후 다음을 누른다
   
 - **단계5 태그 추가**
  ![image](https://user-images.githubusercontent.com/63778557/147057349-26e43097-d10b-4c1f-b010-3fd61ad288ec.png)
    - 키에는 Name을, 값에는 내가 알아볼 수 있는 임의의 이름을 넣고 다음을 누른다
   
 - **단계6 보안 그룹 구성**
  ![image](https://user-images.githubusercontent.com/63778557/147058241-8f08e4ea-62d7-4157-a60a-bf1a8d2e2a85.png)
    - 기존에 설정해둔것이 있으면 기존을 선택한다. 맨 아래에 있는 것이 최신이다.
    - 검토 및 시작을 누른다
   
 - **단계7 검토**
    - 설정을 검토 후 `시작하기`버튼을 누른다 
   
 - **키 페어 생성**
 - ![image](https://user-images.githubusercontent.com/63778557/147059111-ddd227fa-3222-48ac-a324-6c6e0670fdc5.png)
    - [키페어에 대한 설명](https://docs.aws.amazon.com/ko_kr/AWSEC2/latest/UserGuide/ec2-key-pairs.html)
    - 기존에 다운받은 키페어가 있기 떄문에 기존을 선택했다 (맨 아래가 최신)
    - AWS에서 가상 서버에 접근하려면 개인키(private key)와 공개키(public key)로 구성된 키 페어(key pair)가 필요하다. 
    - 공개키는 인스턴스에 저장하고, 개인키는 .pem파일로 다운받아 사용자가 저장한다.
    - 인스턴스 시작을 누른다.
   
 ---
 #### 탄력적 IP(Elastic IP)를 이용해 고정 IP 부여
 











