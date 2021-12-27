---
layout: post
title: (YuldoStudy) Xshell - AWS EC2서버에 접속하여 Nginx 설치
subtitle : Xshell을 이용하여 AWS EC2 ubuntu 서버에 접속해서 Nginx를 설치한다.
tags: [yuldo study]
author: mirutree
comments : True
---

### 새 세션 만들기 및 프라이빗 키 파일 연결
 - XShell에서 `파일` > `새로 만들기`를 눌러서 새 세션을 만든다.
   
&nbsp;&nbsp;
 - 등록정보 - 연결   
![image](https://user-images.githubusercontent.com/63778557/147436634-98126f45-ca20-4ee3-b3a5-b35dc4256fe3.png)
    - 이름 : 본인이 알아볼만한 이름을 넣는다.
    - 호스트 : AWS EC2 인스턴스에서 발급받은 ip주소를 넣는다.
   
&nbsp;&nbsp;
 - 등록정보 - 연결 > 사용자 인증   
![image](https://user-images.githubusercontent.com/63778557/147436716-249fb60c-45f0-45a7-875b-dbef433b41e9.png)   
    - 사용자 이름은 ubuntu 방법은 Public Key를 선택한다.
    - `연결`버튼을 누른다.
   
&nbsp;&nbsp;
 - 보안경고창이 뜨면 `수락 및 저장`버튼을 누른다   
![image](https://user-images.githubusercontent.com/63778557/147436770-26a4347e-3540-40b3-bac8-18419ac2a42d.png)   
   
&nbsp;&nbsp;
 - `찾아보기` > `사용자 키`를 눌러서 SSH 사용자 인증한다.(또는 이미 등록된 키가 있다면 선택한다.   
![image](https://user-images.githubusercontent.com/63778557/147436855-6118646e-9600-4f99-aaa2-a7241d45b346.png)   
   
&nbsp;&nbsp;
 - 사용자 키 등록   
![image](https://user-images.githubusercontent.com/63778557/147436911-ee5b3f89-3f5d-4067-a734-3d904c719e72.png)   
 - `가져오기`버튼을 눌러서 인스턴스를 생성할 때 발급받았던 프라이빗키(확장자 .pem)를 선택한다.
 - 등록된 사용자 키를 선택한 후 확인을 누른다.   
   
&nbsp;&nbsp;

### Ubuntu에 Nginx설치
 - 서버에 접속하면 계정이름이 `ubuntu`인지 확인한다.
 - Linux Ubuntu(우분투)에서 복사 붙여넣기는 `Ctrl` + `Insert` / `Shift` + `Insert`
      
&nbsp;&nbsp;
 - 루트로 이동
 ```
 sudo -s 
 ```
    
 &nbsp;&nbsp;
 - 날짜 설정 - time Zone을 'Asia/Seoul'로 설정한다.
 ```
 dpkg-reconfigure tzdata
 ```
 ![image](https://user-images.githubusercontent.com/63778557/147440782-9fcb5958-dfee-46b2-945a-23b4a916f31f.png)   
    
&nbsp;&nbsp;
  - 다운받기 전에 전체 패키지를 업데이트, 업그레이드 한다.
```
sudo apt-get update
sudo apt-get upgrade
```
      
&nbsp;&nbsp;
 - 해당 경로(apt repository)에 nginx.list파일을 생성하고 nano에디터를 이용해 편집(설치하고자 하는 nginx 버전)
    - nano단축키 ⬇️
    - `Ctrl` + `O` : 파일 저장하기
    - `Ctrl` + `X` : nano에서 빠져나가기
    - [더 많은 nano 단축키 보기](https://www.nano-editor.org/dist/latest/cheatsheet.html)

```
nano /etc/apt/sources.list.d/nginx.list
```  
```
#Ubuntu 18.04
deb http://nginx.org/packages/mainline/ubuntu/ bionic nginx
deb-src http://nginx.org/packages/mainline/ubuntu/ bionic nginx
```
![image](https://user-images.githubusercontent.com/63778557/147446357-f746f94c-94be-4be6-b219-dae87bc5f92f.png)  
   
&nbsp;&nbsp;

 - nginx (보안)key download 및 추가
 ```
wget http://nginx.org/keys/nginx_signing.key
sudo apt-key add nginx_signing.key
```
 - 패키지 업데이트
```
sudo apt-get update
```
 - nginx 설치
```
sudo apt-get install nginx
```
 - nginx 설치 확인
```
nginx -V
```
   
&nbsp;&nbsp;






















