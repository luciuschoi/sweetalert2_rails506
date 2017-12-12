# SweetAlert2를 레일스 5.0.x 버전에서 사용하기

**레일스 5.1 <u>이전</u> 버전**에서는 디폴트로 **jquery**, **jquery_ujs** 를 사용하도록 되어 있어 **jquery** 의존성을 가지는 **SweetAlert2** 를 레일스에서 사용할 때 문제가 없어야 한다. 테스트를 위해 프로그젝트를 다름과 같이 새로 작성한다.

```sh
$ rails _5.0.6_ new sweetalert2_rails506 && cd sweetalert2_rails506
```

그리고 아래의 두 젬을 Gemfile에 추가하고 번들 인스톨한다. 

```ruby
gem 'sweetalert2'
gem 'rails-sweetalert2-confirm'
```

**application.js**

```js
//= require jquery
//= require jquery_ujs
//= require sweetalert2
//= require rails-sweetalert2-confirm
//= require turbolinks
//= require_tree .
```

**application.css**
```css
 *= require sweetalert2
 *= require_tree .
 *= require_self
```

**application.scss**
```scss
@import 'sweetalert2'
```

![](https://github.com/nicolasblanco/sweet-alert2-rails/raw/master/doc/sweet_alert.png)

**Post** 리소스를 아래와 같이 **scaffolding**하고 `db:migrate` 한다.

```sh
$ rails g scaffold Post title content:text
```

```sh
$ rails db:create && rails db:migrate
```

이제 서버를 시작을하고 브라우저에서 접속한다. 

```sh
$ rails s -p 3000
```

http://localhost:3000/posts 로 접속한 후 **post** 를 하나 생성한다. 그리고 방금 생성한 **post** 를 삭제하면 다음과 같은 자바스크립트 팝압창이 보이게 된다. 

![](app/assets/images/confirm_popup.png)

Voila~
