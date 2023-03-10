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

## CSS 원칙
- 모든 요소는 네모(박스 모델)이고, 위에서부터 아래로, 왼쪽에서 오른쪽으로 쌓인다. 
- content, padding, border, margin 으로 box는 구성되어 있다.

## padding, border, margin 사용법
```
.margin-1{
  margin: 10px, 20px ..
  margin-top: 10px

}
```

```
.border{
  border: 2px dashed black;
}
```

## box sizing
- width는 padding 까지 보임
- box-sizing은 content-box padding을 제외한 순수 contents 영역만을 box로 지정

## emmit(short cut)
- ! + tab
- div.content
- div#content
- div.main-content*5
- div.my-content>p#test*5

## lorem
- 의미없는 화면을 라틴어로 채워줌.
- lorem10, lorem*5, lorem100

## CSS 원칙2
- 모든 요소는 네모(박스모델)이고, 좌측상단에 배치.
- display에 따라 크기와 배치가 달라진다.

## css display
- 인라인 vs 블록 요소
- span: 인라인 요소
- div: 블록 요소
- display:block
- display:inline

## block
- 줄 바꿈이 일어나는 요소
- 화면 크기 전체의 가로 폭을 차지한다
- 블록 레벨 요소 안에 인라인 레벨 요소가 들어갈 수 있음
- width, height를 주어도 margin은 한 줄을 가득 채움

## inline
- 줄 바꿈이 일어나지 않는 행의 일부 요소
- content를 마크업 하고 있는 만큼만 가로 폭을 차지한다.
- width, height , margin-top, margin-bottom을 지정할 수 없다
- 상하 여백은 line-height로 지정한다.

## 속성에 따른 수평 정렬
- margin-right:auto; (왼쪽 정렬)
- margin-left:auto (오른쪽 정렬)

## inline-block
- block과 inline 레벨 요소의 특징을 모두 가짐
- inline처럼 한 줄에 표시 가능하고, block처럼 width, height, margin 속성을 모두 지정할 수 있음

## none
- 화면에 표시하지 않고, 공간조차 부여되지 않음
- visibility:hidden은 공간은 차지하지만 보여지지 않음

## css position
```
position: static;
```
- static
- relative
- absolute
- sticky
- fixed 

## static
- 모든 태그의 기본 값(기준 위치)
- 일반적인 요소의 배치 순서에 따름(좌측 상단)
- 부모 요소 내에서 배치될 때는 부모 요소의 위치를 기준으로 배치 됨
- static 외의 좌표 프로퍼디는 top, bottom, left, right를 사용하여 이동 가능

## relative
- 자기 자신의 static 위치를 기준으로 이동
- 레이아웃에서 요소가 차지하는 공간은 static일 때와 같음

## absolute
- 요소를 일반적인 문서 흐름에서 제거 후 레이아웃 공간을 차지하지 않음 (normal flow에서 벗어남)
- static이 아닌 가장 가까이 있는 부모 / 조상 요소를 기준으로 이동

## fixed
- 요소를 일반적인 문서 흐름에서 제거 후 레아웃 공간을 차지하지 않음(normal flow)에서 벗어남
- 부모 요소와 관계없이 viewport를 기준으로 이동
- 스크롤 시에도 항상 같은 곳에 위치함

## sticky
- 스크롤에 따라 static에서 fixed로 바뀜

## Float
- 박스를 왼쪽 혹은 오른쪽으로 이동시켜 텍스트를 포함 인라인요소들이 주변을 wrapping 하도록 함
- 요소가 Normal flow를 벗어나도록 함

## Float 속성
- none
- left
- right
- float으로 layout을 잡는다.
- clear: both 이용해서 normal flow를 없애줄 수 있음
- Normal Flow에서 벗어난 레이아웃 구성

## Flexbox
- Layout을 위해 탄생함
- 행과 열 형태로 아이템들을 배치하는 1차원 레이아웃 모델
- 축: main axis, cross axis (메인 축, 교차 축)
- 구성요소: Flex Container(부모 요소), Flex Item(자식 요소)

## Flex Container (부모 요소)
- flexbox 레이아웃을 형성하는 가장 기본적인 모델
- Flex Item들이 놓여있는 영역
- display 속성을 flex혹은 inline-flex로 지정
- display: flex;

## Flex Item (자식 요소)
- 컨테이너에 속해 있는 컨텐츠 (박스)

## flex-direction (컨테이너 속성)
- flex-direction: column, row, column-reverse, row-reverse
- Main axis 기분 방향 설정
- 역방향의 경우 HTML 태그 선언 순서와 시각적으로 다르니 유의

## flex-wrap (컨테이너 속성)
- 아이템이 컨테이너를 벗어나는 경우 해당 영역 내에 배치되도록 설정
- 즉, 기본적으로 컨테이너 영역을 벗어나지 않도록 함
- flex-wrap: nowrap, wrap

## justify-content
- Main axis를 기준으로 공간 배분
- justify가 나오면 메인축 기준으로 무언가를 하겠구나 라고 생각
- flex-start, flex-end, center, space-between, space-around, space-evenly

## align-items
- 모든 아이템을 Cross axis 기준으로 정렬
- stretch, flex-start, flex-end, center, baseline

## align-content
- Cross axis를 기준으로 공간 배분 (아이템이 한 줄로 배치되는 경우 확인할 수 없음)
- flex-start, flex-end, center, space-between, space-around, space-evenly

## align-self
- 개별 아이템을 Cross axis 기준으로 정렬 (개별 아이템에 적용하는 속성)
- stretch, flex-start, flex-end, center 

## 기타 속성
- order: 배치순서를 원하는대로 바꿀 수 있음
- flex-grow : 