# 웹 프레임워크 이해하기

# MTV 구조와 URLs

# Model과 ORM

## Form & Data
- HTML form element를 통해 사용자와 애플리케이션 간의 상호작용 이해하기

## Sending form data (Client)
- HTML form element : action (위치), method (방식) 속성 정의 필요
- HTML label : for 속성, input의 id와 일치해야 됨
- HTML input : type, name, id 속성 (name으로 server에 data 전달, 서버는 name 속성에 설정된 값을 통해 입력 데이터에 접근 가능)

```
<form action="{% url 'articles:catch' %}" method="GET">
  <label for="message">Throw</label>
  <input type="text" id="messege" name="messege">
  <input type="submit">
</form>
```

- HTTP: HTML 문서와 같은 리소스들을 가져올 수 있도록 해주는 프로토콜
- HTTP request methods: GET, POST, PUT, DELETE

- Query String Parmeters: 사용자가 입력 데이터를 전달하는 방법 중 하나로, url 주소에 데이터를 파라미터를 통해 넘기는 것
```
http://host:port/path?key=value&key=vlaue
```

## Retrieving the data (Server)
- 데이터 가져오기 : query string prameters를 어떻게 접근할까?
- 모든 요청 데이터는 view 함수의 첫번째 인자 request에 들어있다.
```
request.GET
<QueryDict: {'messege': ['데이터']}>

request.GET.get
'데이터'
```

- 요청과 응답 객체 흐름 (이해가 잘 안되어서 다 적어봄)
```
1. 페이지가 요청되면 Django는 요청에 대한 메타데이터를 포함하는 HttpRequest Object를 생성

2. 그리고 해당하는 적절한 view 함수를 로드하고 HttpRequest를 첫번째 인자로 전달

3. 마지막으로 view함수는 HttpResponse object를 반환
```


## Database
- 체계화된 데이터의 모임
- 검색 및 구조화 같은 작업을 보다 쉽게 하기 위해 조직화된 데이터를 수집하는 저장 시스템

## Model
- 웹 애플리케이션의 데이터를 구조화하고 조작하기 위한 추상적인 계층(모델)을 제공
- 모델 클래스 1개 == 데이터베이스 테이블 1개
```
class Article(models.Model):
  title = models.CharField(max_length=10)
  content = models.TextField()
```

- CharField: 길이의 제한이 있는 문자열을 넣을 때 사용
- TextField: 글자의 수가 많을 때 사용


## Migrations
- Django가 모델에 생긴 변화(필드 추가, 수정 등)를 실제 DB에 반영하는 방법

```
python manage.py makemigrations
python mange.py migrate
```

- 설계도를 실제 db.sqlite3 DB 파일에 반영
```
python manage.py showmigrations
python manage.py sqlmigrate articles 0001
```

## ORM
- Object-Relational-Mapping
- 객체 지향 프로그래밍 언어를 사용하여 호환되지 않는 유형의 시스템 간에 데이터를 변환하는 기술
- Django 는 내장 Django ORM을 사용

## 사전 준비 (SQlite 확장 프로그램)
- SQlite 설치
- DB 우클릭- Open Database
- table을 직관적으로 확인할 수 있음
- pip install ipython
- pip install django-extensions

## QuerySet API
- Django가 제공하는 ORM을 사용해 데이터베이스를 조작하는 방법
- Article.objects.all() : Modelclass.Manager.QuerysetAPI
- objects manager: Django 모델이 데이터베이스 쿼리 작업을 가능하게 하는 인터페이스
- 기본적으로 Django는 모든 모델 클래스에 objects라는 Manager 객체를 자동 생성함
- Query: 데이터베이스에 특정한 데이터를 보여달라는 요청, Django는 응답 데이터를 QuerySet이라는 자료 형태로 변환하여 전달함.

## CREATE
- python manage.py shell_plus (shell_plus 실행하여 DB 조작)
```
article = Article()
article.title
article.save()

article = Article(title='second', content='django!')
article.save

Article.objects.create(title='third', content='django!')
```
- .save: 객체를 데이터베이스에 저장함

## READ
- QuerySet API method를 사용해 데이터를 다양하게 조회하기
- 크게 두가지로 분류됨
```
1. Methods that "return new querysets"
2. Methods that "do not return querysets"
```

- all(): 전체 데이터 조회
- get(): 단일 데이터 조회 pk 이용
- filter: 지정된 조회 매개변수와 일치하는 객체를 포함하는 새 QuerySet을 반환

## UPDATE
-Update 과정
```
1. 수정하고자 하는 article 인스턴스 객체를 조회 후 반환값을 저장
2. article 인스턴스 객체의 인스턴스 변수 값을 새로운 값으로 할당
3. save() 인스턴스 메서드 호출
```

## DELETE
- Delete 과정
```
1. 삭제하고자 하는 article 인스턴스 객체를 조회 후 반환 값을 저장
2. delete() 인스턴스 메서드 호출
```