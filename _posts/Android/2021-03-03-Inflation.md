---
layout: post
current: post
cover:  assets/images/welcome.jpg
navigation: True
title: Layout Inflation
date: 2021-03-03 18:50:00
tags: [Android]
class: post-template
subclass: 'post'
author: gMinGit
---

안드로이드의 앱은 어떻게 만들어지는 걸까?

안드로이드 앱을 만들기 위해서는 화면을 구성하고 배치하기 위한 XML 레이아웃 파일과

화면의 기능을 담당하는 소스코드 파일이 필요하다.

그렇다면 어떻게 XML 레이아웃 파일과 소스코드 파일이 연결되는 걸까?

우리가 간단하게 안드로이드 스튜디오에서 예제 프로젝트를 실행하게 되면

> public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
}

다음과 같이 코드가 생성된다. super.onCreate(savedInstanceState) 코드의 경우는 부모 클래스의 함수를 그대로 부르는것이다.

그렇다면 남아있는 것은 setContentView(R.layout.activity_main) 이 부분이다.

따라서 이 부분이 소스코드 파일과 XML 레이아웃 파일을 이어주는 역할을 한다고 볼 수 있다.

여기서 파라미터 값을 살펴보면 R은 res 폴더를 의미하고 layout은 layout 폴더를 의미한다.

따라서 res/layout/activity_main.xml을 의미하는 것으로 볼 수 있다.

실제로 앱을 실행하게 되면 XML 레이아웃이 객체화되어 소스코드 파일에서 사용된다.

이 과정을 인플레이션이라고 한다.

> 인플레이션 : XML 레이아웃의 내용이 메모리에 객체화되는 과정

이러한 인플레이션의 과정이 setContentView(R.layout.activity_main) 해당 부분에서 일어나게 된다.

이 부분을 증명하기 위해서 해당 호출 과정의 전에서 xml 레이아웃에 있는 리소스들을 접근하게 되면 앱이 실행하지 않고 종료하는

것으로 알 수 있다. (시간이 된다면 한번 해보는것을 추천한다.)

하지만 setContentView 라는 메서드는 xml 파일을 객체화 하는 역할 뿐 아니라 화며에 나타낼 뷰를 지정하는 역할도 수행합니다.

그렇다면 화면 전체의 XML 레이아웃이 아닌 별도의 XML 레이아웃 파일을 인플레이션 작업을 할 순 없는걸까요?

이 과정은 다음시간에 다루어 보도록 하겠습니다.