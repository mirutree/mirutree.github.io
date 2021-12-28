---
layout: post
title: (YuldoStudy) Gabia - DNS 레코드 설정
subtitle : 도메인에 ip연결하기
tags: [yuldo study]
author: mirutree
comments : True
---

### 도메인과 네임서버(생활코딩 참조)
 - ip는 인터넷에 연결된 각각의 장치의 고유주소이며 4마디 혹은 8마디의 숫자로 되어 있다.
 - **도메인?** 
    - ip는 사람이 이해하고 기억하기 어렵기 때문에 이를 위해서 ip에 이름을 부여할 수 있게 했는데, 이것을 도메인이라고 한다. 
    - ex) naver.com -> 220.95.233.172
 - **DNS(Domain Name System)?**
    - 웹사이트의 IP 주소와 도메인 주소를 이어주는 시스템이다.
 - **네임서버?**
    - 도메인에 해당하는 ip를 알려주는 서비스
     
&nbsp;&nbsp;&nbsp;
### Gabia에서 DNS 레코드 설정하기   
 - 가비아에서 도메인을 구입하는 과정은 생략했다.
 - [가비아 DNS 레코드 설정하는 공식 가이드](https://customer.gabia.com/manual/dns/3041/3040)
   
&nbsp;&nbsp;   
 - 가비아 로그인 후 > `My가비아` > `DNS 관리툴` 버튼을 누른다.
 - 구입한 도메인의 `설정` 버튼을 누른다.
  ![image](https://user-images.githubusercontent.com/63778557/147191835-3af4fdd7-6629-4be3-9811-3b246d1d01d9.png)
 - 레코드를 설정한다.
 ![image](https://user-images.githubusercontent.com/63778557/147531019-518cd077-d691-4b4c-898e-50af5fc10fa4.png)
   - A 레코드 설정
     -  도메인 또는 서브도메인(하위도메인)에 IP주소를 지정하는 것
     -  **@** : 2차도메인 없이 `mituree.com`이라는 주소에 입력된 ip주소에 연결
     -  **www** : `www.mirutree.site`같이 서브도메인을 붙여서 값에 입력된 ip주소와 연결
   - TXT 레코드 설정
     - 사이트 소유권을 인증해야하는 경우 설정
     - ex) Let's Encrypt 와일드카드 인증서 발급받을 때 : `_acme-challenge`라는 이름으로 발급받은 값을 넣는다.

   
&nbsp;&nbsp;&nbsp;















