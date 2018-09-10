# Android Application Components

안드로이드의 컴포넌트에는 주로 네가지의 컴포넌트가 있다.



## Activity

Activity는 사용자 화면을 제공하는 **UI**.
눈에 보이는것들은 Activity라고 생각 하면 됨.



## Service

백그라운드 프로세스라고 생각 하면 간단함.

### Local Service

특정한 Application에서만 실행 할 수 있는 Serivice. 지역성을 ㄱ짐

### Remote Service

외부 앱에서 실행 할 수 있는 Service.



## Broadcast Receiver

말 그대로 'Broadcast' 즉, 모든 앱들이 받을 수 있는 메세지를 처리 하는 컴포넌트.
안드로이드에서 특정 이벤트를 알리고 싶을때 사용.
Broadcast를 만들 수도 있음.

예시

- 부팅이 완료될 때
- 화면이 켜질 때
- 화면이 꺼질 때
- 날짜가 변경될 때
- 시간이 변경될 때
- SMS 문자 메시지를 받을 때
- 외장 메모리 카드를 기기에 꽂을 때
- 외장 메모리 카드를 기기로부터 뺄 때 



## Contents Provider

안드로이드에서 어플리케이션끼리 데이터를 공유하기 위해 만들어진 컴포넌트.

예시

* 주소록
* 통화 기록
* 멀티미디어 파일들
* 환경 설정 값들



2018-09-04 김도현 작성