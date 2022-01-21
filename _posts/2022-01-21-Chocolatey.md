---
layout: post
title: Chocolatey 사용법
subtitle : 윈도우용 패키지 매니저 Chocolatey 간단 사용법
tags: [Chocolatey]
author: mirutree
comments : True
---

### 🍫 Chocolatey?
![image](https://user-images.githubusercontent.com/63778557/150445945-ecf258fd-dde2-4e02-9ecf-17d02ded73d6.png)   
Chocolatey를 사용하면 윈도우에서 사용하는 여러 프로그램 설치나 버전관리를 손쉽게 할 수 있다.
  
&nbsp;&nbsp;
### 🍫 Chocolatey 설치하는 법
 - [https://chocolatey.org/](https://chocolatey.org/) Chocolatey 사이트에 접속한다.
 - Get Started 클릭   
  ![image](https://user-images.githubusercontent.com/63778557/150446578-1b209cac-e066-406d-95c7-bb0dae8f1dc9.png)
 - 개인용 설치 커맨드를 복사한다   
  ![image](https://user-images.githubusercontent.com/63778557/150465254-b1069f60-7cb3-4815-9229-80e8ff7ee80c.png)
 - **Windows PowerShell**을 관리자모드로 실행하여 복사한 커맨드를 붙여넣어 설치한다
 -![image](https://user-images.githubusercontent.com/63778557/150465429-cd2cc7ad-3919-4c6c-956b-e2aa182b162e.png)
   
&nbsp;&nbsp;
### 🍫 Chocolatey를 사용하여 패키지 설치
 - ***ex1)***
   - Chocolatey 사이트의 상단 메뉴에서 커뮤니티로 이동한다
   - 설치할 패키지를 검색한 후 커맨드를 복사한다
   - ![image](https://user-images.githubusercontent.com/63778557/150471427-2b9594ad-abb3-406a-8d01-0cd4a7a71586.png)
   - **Windows PowerShell**에 커맨드를 붙여넣어 설치한다.
    
 &nbsp;&nbsp;
 - ***ex2)*** 
   - **Windows PowerShell**에 `choco install <패키지이름>` 커맨드를 입력하여 설치한다.
```
#노트패드 설치 커맨드
choco install notepadplusplus
```   
   



