# CSS

## CSS
- Cascading Style Sheets
- 스타일을 지정하기 위한 언어
- 선택하고, 스타일을 지정한다.

## CSS 구문
```
h1{
  color: blue;
  font-size: 15px;
}
```
- 선택자(Selector): h1
- 선언(Declaration) : color: blue;
- 속성(Property): color, font-size, ...
- 값(Value): 15px, blue ...

## CSS 정의 방법
- 인라인(inline)
- 내부 참조(embedding) - <style>
- 외부 참조(link file) - 분리된 CSS 파일

## CSS 정의 방법 - 인라인
```
<h1 style = "color: blue; font-size: 100px;"> Hello </h1>
```

## CSS 정의 방법 - 내부 참조
```
<head>
<style>
h1{
  color: blue;
  font-size: 100px;
}
</style>
</head>
```

## CSS 정의 방법 - 외부 참조
```
<link rel="stylesheet" href="mystyle.css">
```

## 개발자 도구 - f12 (chrome)
- 개발자 도구를 이용하여 현재 페이지가 어떻게 만들어졌는지 볼 수 있음
- style, computed ...

## 선택자 (Selector) 유형
- 기본 선택자: 전체 선택자(*), 요소(tag)선택자, 클래스(class)선택자, 아이티(id) 선택자, 속성(attr) 선택자

- 결합자(Combinators): 자손 결합자, 자식 결합자

## class vs id
- 여러 곳에 사용하고 싶다: class
- 하나에만 적용하고 싶다: id
- .green (클래스 선택자), #purple (id 선택자)

## CSS 적용 우선순위 (cascading order)
1. 중요도 (Importance) - 사용시 주의 (!important)
2. 우선순위 (Specificity): 인라인 > id > class, 속성 > 요소

## CSS 상속
- CSS는 상속을 통해 부모 요소의 속성을 자식에게 상속한다.
- 속성 중에는 상속이 되는 것과 되지 않는 것들이 있다.
- 상속 되는 것: Text관련 요소(font, color, text-align) ...
- 상속 되지 않는 것: Box model 관련 요소, position관련 요소 ...
- 자세한 내용은 MDN 가서 확인하기

## 자식결합자, 자손결합자
```
.box > p (자식 결합자)
box라는 클래스를 가진 얘들중 자식 중 p태그가 있는 요소들을 선택

.box p (자손 결합자)
box라는 클래스 아래의 모든 p태그에다 적용
```




