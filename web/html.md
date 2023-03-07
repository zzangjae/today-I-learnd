# HTML & Internet

## vscode 단축키
- alt + shift + 화살표 : 복사
- alt + 화살표 : 이동
- ctrl + d : 다중 선택

## HTML?
- 웹 페이지의 구조를 잡는 도구
- HTML (Hyper Text Markup Language)
- Hyper Text: 참조를 통해 사용자가 한 문서에서 다른 문서로 즉시 접근할 수 있는 텍스트
- Markup Language: 태그 등을 이용하여 문서나 데이터의 구조를 명시하는 언어

## HTML 문서 구조화
- 텍스트 요소
```
<a></a> href 속성을 활용하여 다른 URL로 연결하는 하이퍼링크 생성
<b></b> 굵은 글씨 요소
<i></i> 기울임 글씨 요소
<br> 텍스트 내에 줄 바꿈 생성
<img> src 속성을 활용하여 이미지 표현
<span></span> 의미 없는 인라인 컨테이너
```

## 그룹 컨텐츠
```
<p></p> 하나의 문단 (paragraph)
<hr> 주제를 분리하기 위한 수평선 (A Horizontal Rule)
<div></div> 의미 없는 블록 레벨 컨테이너
```

## form
- 사용자의 정보를 제출하기 위한 영역
- 기본 속성 : action (form을 처리할 서버의 URL), method (Http)

## input
- 다양한 타입을 가지는 입력 데이터 유형과 위젯이 제공됨
- 대표적인 속성: name, value, ...등

## input label
- label을 클릭하여 input 자체의 초점을 맞추거나 활성화 시킬 수 있음
- 사용자는 선택할 수 있는 영역이 늘어나 웹 / 모바일(터치) 환경에서 편하게 사용할 수 있음
- label과 input 입력의 관계가 시각적 뿐만 아니라 화면리더기에서도 label을 읽어 쉽게 내용을 확일할 수 있도록 함
- 
```
<label for="agreement>개인정보 수집에 동의합니다.</label>
<input type="checkbox" name="agreement" id="agreement">
```

## input 유형 - 일반
- 일반적으로 입력을 받기 위하여 제공되며 type으로 HTML기본 검증 혹은 추가 속성을 활용할 수 있음
- text: 일반 텍스트 입력
- password: 입력 시 값이 보이지 않고 문자를 특수기호(*)로 표현
- email: 이메일 형식이 아닌 경우 form 제출 불가
- number: min, max, step 속성을 활용하여 숫자 범위 설정 가능
- file: accept 속성을 활용하여 파일 타입 지정 가능

## input 유형 - 항목 중 선택
- label로 선택에 대한 내용을 작성하고, 항목으로 선택할 수 있는 input을 제공
- 동일한 범주에 속하는 항목들은 name을 통일하고, 선택된 항목의 값은 value로 지정함
- checkbox: 다중 선택
- radio: 단일 선택

## input 유형 - 종합
- input 요소의 동작은 type에 따라 달라짐


