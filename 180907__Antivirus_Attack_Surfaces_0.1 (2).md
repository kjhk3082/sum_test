# Antivirus Attack Surfaces

[TOC]

------



## Local Attack Surface

**Local Attack Surface**란 해커가 로컬의 안티 바이러스 리소스에 접근 함으로서 취약점을 발생 시킬 수 있는 표면들을 말한다.



### 파일/디렉토리 권한 취약성

설정 파일이나 엔진이 저장된 곳의 권한등이 잘못 설정 되어 있을 경우 해커에게 악의적으로 이용 당할 수 있다



### 올바르지 않은 Access Control Lists (Windows)

예시로 Panda Antivirus에서 WebProxy.EXE와 SrvLoad.EXE가 판다 서비스에서 실행 되어졌는데, 어떠한 이유로 안티바이러스 엔지니어들이 ACL을 Null로 설정 하여 모든 로컬 유저들이 해당 프로세스들로 뭔가 할 수 있었다. 예를 들어 `CreateRemoteThread` API 를 이용해 DLL Injection 하여 SYSTEM 권한을 얻어 낼 수 있었다.



------



## Remote Attack Surface

**Remote Attack Surface**란 adjacent network (LAN)이나 external network (WAN)으로부터 노출되어 있는 표면(Surface)를 말한다.



### File Parsers

백신의 플러그인중 PDF, ELF, PE, Zip, 7z, Adobe Flash, Javascript등에서 악성코드를 탐지하기 위한 플러그인의 설계 실수로 인해 취약점이 발생 할 수 있다.

즉, 다양한 파일 벡터를 어택 벡터로 연관 지을 수 있다.



### Generic Detection and File Disinfection Code

백신에서 악성 행위를 탐지 하기 위해 파일을 자동으로 분석 하고, 해당 악성 코드 부분을 '제거' 하는 행위에서 백신 엔지니어의 설계 실수로 인해 취약점이 발생 할 수 있다.



### 네트워크 서비스, 관리자 패널

백신의 세팅이나 서비스를 위해 http등 사용자가 웹, 소켓등을 이용 해 접근 할 수 있는 벡터를 말한다.

* User의 정확한 체크 없이 패널을 이용해 설정을 건드릴 수 있는 경우
* 실재하지 않는 사용자 인증
* 수동적인 암호화 방식, 적합하지 않은 모드를 이용한 명령 실행 (암호화가 깨질 수 있음)
* `ClientLibraryName`과 같은 인자가 서비스에서 RCE를 일으킬 수 있는 경우 (취약점 예시.)



### 서비스 업데이트

http와 같은 방식을 이용 해 백신의 중요한 부분을 업데이트 시킬 경우 데이터 변조를 당할 수 있고, 또한 SSL/TLS가 적용 되어 있더라도 올바르지 않은 인증 알고리즘을 가지고 있을 경우도 포함 된다.



### 안티바이러스가 사용자의 웹 브라우저 이용에 영향을 끼칠 경우

안티바이러스의 기능중 사용자의 웹 브라우저를 통한 악성 코드 실행을 방지 하기 위해 보호를 적용 할 경우 (Dll Injection, ActiveX 등 ) 해당 모듈의 설계 실수로 인해 취약점이 발생 할 수 있다.



### 프로토콜 파싱 과정

파일 포맷과 비슷



------



## Todo

안드로이드 어택 벡터 Android Hacker's Handbook 보고 정리



## References

* Antivirus Hacker's Handbook