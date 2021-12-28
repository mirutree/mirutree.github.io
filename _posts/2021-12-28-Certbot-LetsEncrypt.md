---
layout: post
title: (YuldoStudy) Certbot을 이용한 Let’s Encrypt 와일드 카드 인증서 발급
subtitle : 
tags: [yuldo study]
author: mirutree
comments : True
---
이 포스팅은 [Xshell - AWS EC2서버에 접속, Nginx 설치](https://mirutree.github.io/2021/12/27/Xshell-Nginx.html)포스팅과 이어지는 내용이다.
   
### Certbot을 이용한 Let’s Encrypt 와일드 카드 인증서 발급
 > HTTPS를 사용하기 위해 무료 인증서인 Let’s Encrypt 와일드 카드 인증서 발급받는 과정

   
&nbsp;&nbsp;
 - **Certbot 설치**
 ```
sudo apt-get update
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:certbot/certbot
sudo apt-get update
```
   
&nbsp;&nbsp;
 - **Nginx에 Cerbot 패키지 설치**
```
sudo apt-get install python-certbot-nginx
```
   
&nbsp;&nbsp;
 - **DNS 방식 와일드카드 인증서 요청**
 - 다음 certbot 명령은 도메인 **\*.mirutree.site** 의 와일드카드 인증서를 요청하는 명령어이다.
 ```
certbot certonly --manual --preferred-challenges dns -d "*.mirutree.site" -d "mirutree.site"
 ```
    
&nbsp;&nbsp;
 - **DNS 레코드 설정**    
 ![image](https://user-images.githubusercontent.com/63778557/147529447-6806070e-d740-489c-b4c4-cce5226b71f9.png)
      - ❗**인증을 Verification 할때 이미 DNS TXT Record가 존재해야한다.**
      - 이미지와 같이 발급해준 값을 DNS TXT Record에 추가해준다.
      - [Gaia - DNS 레코드 설정](https://github.com/mirutree/mirutree.github.io/blob/main/_posts/2021-12-23-Gabia-DNS-record.md)을 참고한다.   
   
&nbsp;&nbsp;
 - 인증완료   
 ![image](https://user-images.githubusercontent.com/63778557/147527952-a04017a4-1f34-46b1-bb3b-d0e38801f65b.png)
      - 다음과 같이 축하한다는 메시지가 나오면 완료된 것이다.
   
&nbsp;&nbsp;



