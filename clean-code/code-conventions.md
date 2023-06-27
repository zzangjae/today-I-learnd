# Code Conventions
- 읽고, 관리하기 쉬운 코드를 작성하기 위한 일종의 코딩 스타일 규약
- 사전에 코드의 스타일을 통일함으로써 협업에 용이하다

## 코딩 컨벤션의 필요 요소
- 파일의 구성
- Naming Convention
- 들여쓰기
- 주석
- 선언
- 명령문
- 공백

### 1. 파일의 구성
- 2천 줄 이상의 긴 파일로 구성되는 것을 지양
- 자바 소스 파일은 여러 section을 식별하는 주석으로 구성
- 소스파일 순서 1. 주석, 2. 패키지 및 import 문, 3. 클래스 및 인터페이스
- Beginning Comments (Classname, Version imformation, Date, Copyright notice) 

### 2. Naming Convention
- 패키지 이름은 소문자로 작성한다. (언더바, 대문자 사용 지양)
- 클래스 이름은 Camel Case를 사용
- 메소드 명은 기본적으로 동사로 시작하며 다른 타입으로 변환하는 메소드는 전치사 사용 가능
- 상수 이름은 대문자로 작성하며 합성어는 언더바를 이용하여 구분한다.
- 가독성 있는 변수명 (이해하기 쉬운 변수 명으로 작성한다)

### 3. 선언 (클래스 등의 소수 구성요소를 선언할 때의 규칙)
- import 시에는 와일드 카드 없이 필요한 클래스 명을 명시적으로 작성
- 변수 선언문은 한 문장에서 하나의 변수만을 다룬다

### 4. 들여쓰기
- 탭을 사용하여 들여쓴다. 1개의 탭 사이즈는 4개의 스페이스와 같도록 설정

### 코드 컨벤션
- 협업을 이용할 때 코드 컨벤션을 통일해주는 과정이 필요하다.
- Kotlin Coding Convention
- Google Java Style Guide
- NHN 코딩 컨벤션
- Java Code Convention - Oracle