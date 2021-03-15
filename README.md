# Ajax를 공부해 보았습니다.

## REST API

http를 이용해서 기계들이 통신할때,
resource는 uri로, 행위는 method로, 결과는 응답코드로 확인이 가능합니다.
반드시 post, get, put, patch, delete CRUD의 내용의 원래뜻을 기반으로 사용해야합니다.

### Resource

REST API의 resource는 uri를 통해서 표현이 됩니다.
예를들어 topic이라는 객체가 있다고 합시다.
내용 전체를 식별하고 싶다면, collection을 이용합니다. (http://example.com/topics)
하나하나를 분석하고 싶으면 element를 이용합니다. (http://example.com/topics/1) 즉, element가 모이면 collection이 되는 것입니다. element의 id값을 이용하는 것이 일반적입니다.

### Method

정보를 가공하는 방법입니다.
C : create ---> post
R : read ---> get
U : update ---> put/ patch
D : delete ---> delete

rest api는 통신 규약인 http를 이용하기 때문에 http가 가지고 있는 메소드를 이용합니다.
이것은 웹브라우저로 한정되는것이 아닌, 웹서버, 모바일웹, 웹브라우저로 웹서버와 통신할때도 사용합니다.

## 리펙토링 - 함수화

중복되는 코드는 따로 함수로 만들어서 그 함수를 호출하는 연습을 해보았습니다.

## fragment identifier

초기 페이지 기능을 구현해 보았습니다. 특정구역에 id값을 부여하여, 그 구역으로 이동할때, url을 이용해 보았습니다.
ex) http://127.0.0.1:5500/Path.html#three


### 글목록 추가
데이터를 추가할때, index.html 파일을 수정하지 않고, 데이터가 들어있는 list라는 파일을 수정하는것을 통해서 사용자들이 마음대로 수정해서 사고가 나는것을 방지할 수 있고, 콘텐츠를 입력하는 입장에서는 콘텐츠를 어디에 입력을 해야하는가, 어떻게 수정하는가에 대한것에 자유를 얻을 수 있게 만들었습니다.


## fetch API polyfill
오래된 브라우저에 특정 기능이 사용되지 못할때 polyfill을 사용합니다. polyfill은 최신 브라우저에서는 동작하지 않고, 과거 브라우저에만 동작을 하게 합니다.