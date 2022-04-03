# HTML
## html이란?
#### (Hypertext Markup Language)<br>하이퍼 텍스트 마크업 언어<br>(프로그래밍 언어는 아니다)<br>하지만 프로그래밍을 할 수 있다. 우리가 보는 웹페이지가<br>어떻게 구조화되어 있는지 브라우저로<br>하여금 알 수 있도록 하는 마크업 언어.<br><br>

### html은 elements로 구성되어 있으며<br>tags는 웹 상의 다른 페이지로 이동하게 하는<br>하이퍼링크 내용들을 생성, 단어강조 의 역할을 합니다.<br><br>

+ 마크업
#### 마크업이란 파일이 화면에서 어떻게<br>보여야할 것인지를 나타내기 위해,<br>또는 그 문서의 논리적인 구조를<br>묘사하기 위해서, 텍스트나 워드프로세싱 파일의<br>특정 위치에 삽입되는 일련의 문자들이나 기호들.
+ 태그
#### 마크업에 사용되는 표지를 흔히 태그라고 부른다.<br>예를 들어  다음 내용을 보자면
```
Hello world nice to meet you
```
만약 이문장을 표시하고 싶다면<br>
태그중 \<p>로 감싸 엘리먼트 문단으로 명시할 수 있다.
```
<p>Hello world nice to meet you</p>
```
##### (html의 요소는 대소문자를 구분하지 않는다.)<br>ex : \<title>=\<Title>=\<TITLE>=\<TiTlE><br><br>
## 여는 태그(Opening tag)
#### 여는 태그는 요소의 이름과 열고닫는 <>로 구성<br>요소가 시작되는  부분 부터 효과가  적용되기 시작함
##### (아래의 경우 \<p>가 해당)
```
<p>Hello world nice to meet you</p>
```
## 닫는 태그(Closing tag)
#### 닫는 태그는 요소이름 앞에 슬래시(/)가 있는 것만 제외하면<br>여는 태그와 같습니다. 닫는 태그는 요소의 끝에 달아줍니다.
##### (아래의 경우 \</p>의 해당)
```
<p>Hello world nice to meet you</p>
```
## 내용(Content)
#### 요소의 내용이며 텍스트 잧체를 의미함
##### (아래의 경우 Hello world nice to meet you가 해당)
```
            (content)
                |
    __________________________
   |                          |
<p>Hello world nice to meet you</p>
```
## 요소(Element)
#### 여는 태그, 닫는 태그, 내용을 모두 포함한 것.
##### (아래의 경우 전체가 해당)
```
            (element)
                |
 _________________________________
|                                 |
<p>Hello world nice to meet you</p>
```
## \<em>content\</em>
#### 요소의 경우 그 줄의 강조 효과를 줍니다.
EX)
```
<em>Hello world nice to meet you</em>
```
->&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<em>Hello world nice to meet you</em> 와 같이 출력한다.<br><br>

## \<p>content\<strong>content\</strong>\</p>
#### p가 열린후 strong이 열리고 strong이 닫힌후 p가 닫혀야 합니다.
EX)
```
<p>Hello world <strong>nice to meet you</strong></p>
```
-> Hello world <strong> nice to meet you</strong> 으로 출력된다.
##### 아래의 경우 p가 열린후 strong이 열리고<br>p가 닫힌후 strongdl 닫혔기 때문에 잘못된 문장입니다.
```
<p>Hello world <strong>nice to meet you</p></strong>
```
##### 요소 안에 요소를 담기 위해서는 내포되어 지는 요소는 다른 요소 속에서<br>열고 닫혀야 하며 다른 요소를 포함시키는 요소는 그 바깥에서 열고 닫혀야 합니다.
<br><br>

 HTML은  두가지 요소가 있습니다. 바로 
 + 블록 레벨 요소(Block level element) 와
 + 인라인 요소(Inline element) 입니다.
<br><br>

## 블록 레벨 요소(Block level elements)
#### 블록 레벨 요소는 앞뒤 요소사이에 Line을 하나 만듭니다. 
예를 들면 
```
<p>Hello world</p><p>nice to meet you</p>
```
-> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Hello world<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;nice to meet you</p>
#### 와 같이 출력됩니다. 엔터를 치지 않아도 줄바끔이 되는 것이죠.<br>블록 레벨 요소는 인라인 요소에 중첩될 수 없습니다.<br>하지만 블록 레벨 요소는 다른 블록 레벨 요소에 중첩될 수 있습니다.<br><br>

## 인라인 요소(Inline elements)
#### 항상 블록 레벨 요소내에 포함되어 있습니다.<br>인라인 요소는 문서의 한 단락같은 큰 범위에는 적용될 수 없고<br>문장, 단어 같은 작은 부분에 대해서만 적용될 수 있습니다.
```
<em>Hello</em><em>world</em><em>nice to meet you</em>
```
-> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<em>Hello</em><em>world</em><em>nice to meet you</em>
#### 인라인 요소는 새로운 줄(Line)을 만들지 않습니다.
##### 인라인 요소에는 하이퍼링크를 정의하는 요소인 \<a><br>텍스트(Text)를 강조하는 요소인 \<em>,\<strong> 등이 있습니다.
<br><br>

## 빈 요소(Empty elements)
#### 모든 요소가 여는태그, 내용, 닫는 태그 패턴을 따르는 것은 아닙니다.<br>문서에 무언가를 첨부하기 위해 단일 태그(Single tag)를 사용하는 요소도 있습니다.<br>를 들어 \<img> 요소는 해당 위치에 이미지를 삽입하기 위한 요소입니다:
```
<img src="https://raw.githubusercontent.com/mdn/beginner-html-site/gh-pages/images/firefox-icon.png">
```
-> <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/mdn/beginner-html-site/gh-pages/images/firefox-icon.png">
##### (빈 요소는 가끔 void 요소로 불리기도 합니다)
<br><br>

## 속성(Attributes)
#### 속성은 요소에 실제론 나타내고 싶지 않지만<br>추가적인 내용을 담고 싶을 때 사용합니다.<br><br>요소는 아래와 같이 속성을 가질 수 있습니다.
```
      (attributes)
            |
    _________________
   |                 |
<p class="editor-note">My cat is very grumpy</p>
```
#### 속성은 요소에 실제론 나타내고 싶지 않지만<br>추가적인 내용을 담고 싶을 때 사용합니다.<br><br>속성을 사용할 때에는 아래 내용을 지켜야 합니다.
+ 요소 이름 다음에 바로 오는 속성은 요소 이름과<br>속성 사이에 공백이 있어야 되고, 하나 이상의<br>속성들이 있는 경우엔 속성 사이에 공백이 있어야 합니다.
+ 속성 이름 다음엔 등호(=)가 붙습니다.
+ 속성 값은 열고 닫는 따옴표로 감싸야 합니다.
<br><br>

## \<a>
#### 요소 중 하나인 \<a> 요소는 "anchor"를 의미하는데<br>닻이 배를 항구로 연결하듯 텍스트를 감싸서 하이퍼링크로 만듭니다.<br>이 요소는 여러 속성을 가질 수 있지만 아래에 있는 두 개가 주로 사용됩니다.
<br>

+ href: 이 속성에는 당신이 연결하고자 하는 웹 주소를 지정합니다.<br>그 예로, href="https://github.com/squall7011"
+ title: title 속성은 링크에 대한 추가 정보를 나타냅니다.<br>그 예로, title="My gIthub homepage".<br>이 내용은 링크 위로 마우스를 옮겼을 때 나타날 것입니다.
+ target: target 속성은 링크가 어떻게 열릴 것인지를 지정합니다.<br>예를 들어, target="_blank" 는 링크를 새 탭에서 보여줍니다.<br>당신이 현재 탭에서 링크를 보여주고싶다면 이 속성을 생략하면 됩니다.
#### 이 모든 것을 종합해보면
``` 
<p>A link to my <a href="https://github.com/squall7011" title="My gIthub homepage" target="_blank">Github</a>.</p>
```
-><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A link to my <a href="https://github.com/squall7011" title="My gIthub homepage" target="_blank">Github</a>.</p>
로 활용할 수 있다.

## 참과 거짓 속성(Bloolean attributes)
#### 값이 없는 속성이 있을텐데 <br>이를 불 속성이라고 하며,<br>일반적으로 그 속성의 이름과<br>동일한 하나의 값만을 가질 수 있습니다.
+  disabled<br>속성을 양식 입력 요소에 할당하면<br>사용자가 데이터를 입력할 수 없도록<br>비활성화(회색으로 표시) 할 수 있습니다.<br>

EX)
```
<input type="text" disabled="disabled">
```
-> <input type="text" disabled="disabled">

이를 다음과 같이 줄여쓸 수 있습니다.
```
<input type="text" disabled>
```
-> <input type="text" disabled>
<br><br>

## 속성값의 따옴표 생략
#### 웹을 둘러보면 따옴표가 없는 속성값을 포함한 온갖 이상한 마크업 스타일을 볼 것입니다.<br>어떤 상황에선 이런 것이 허용되지만, 다른 상황에서는 당신의 마크업 형식을 망쳐버립니다.<br>이전에 작성한 코드에서는 href 속성만 있는 기본적인 버전을 작성했습니다.
```
<a href=https://github.com/squall7011>My Github profile</a>
```
-> &nbsp;&nbsp;&nbsp;&nbsp;<a href=https://github.com/squall7011>My Github profile</a>
#### 하지만 여기에 title 속성을 추가하면 문제가 발생합니다.
```
<a href=https://github.com/squall7011 title=My Github homepage>My Github profile</a>
```
-> &nbsp;&nbsp;&nbsp;&nbsp;<a href=https://github.com/squall7011 title=My Github homepage>My Github profile</a>
#### 위와 같이 겉으로는 문제 없어 보여도<br>실제로 클릭해보면 작동하지 않는 것을 볼 수있다.<br>title 또한 제데로 동작하지 않는 것을 볼 수 있다.
##### (항상 속성값에 따옴표를 붙여야 합니다. 이런 오류를 피할 수도 있고, 코드의 가독성도 좋아지기 때문입니다.)
<br><br>

## 작은 따옴표,큰따옴표
#### 글에서 모든 속성값은 큰 따옴표에 둘러싸여 있는 것을 볼 수 있습니다.<br>하지만 당신은 어떤 사람의 HTML에서 작은 따옴표를 볼 수 있을 것입니다.<br>이 것은 스타일의 문제로, 당신이 좋아하는 방법을 사용하면 됩니다.<br>아래 두 문장은 똑같이 동작합니다.
```
<a href="http://www.example.com">A link to my example.</a>

<a href='http://www.example.com'>A link to my example.</a>
```
#### 주의해야할 점은 두 개를 섞어 쓰면 안된다는 것입니다. 다음은 잘못 사용한 예입니다
```
<a href="https://github.com/squall7011'>A Link My Git Hub.</a>
```
#### 만약 한 가지 따옴표를 사용했다면 다른 따옴표로 속성값을 둘러싸서 오류를 방지할 수 있습니다.
```
<a href="https://github.com/squall7011" title="Git hub profile">A Link My Git Hub.</a>
```
#### 하지만 만약 당신이 따옴표 안에 같은<br>따옴표를 사용하고 싶다면(작은 따옴표든 큰 따옴표든)<br>따옴표를 표시하기 위해서 HTML entities를 사용하면 됩니다.<br><br>
예를 들어 아래 문장을
```
<a href='https://github.com/squall7011' title='Git hub 'profile'>A Link My Git Hub.</a>
```
-> &nbsp;&nbsp;&nbsp;<a href='https://github.com/squall7011' title='My Git hub 'profile'>A Link My Git Hub.</a>
#### 이렇게 바꿔주면 잘 작동합니다.
```
<a href='https://github.com/squall7011' title='Git hub &#39;profile'>A Link My Git Hub.</a>
```
->&nbsp;&nbsp;&nbsp;&nbsp;<a href='https://github.com/squall7011' title='My Git hub &#39;profile'>A Link My Git Hub.</a>
#### title까지 잘 작동하는 걸 볼 수 있습니다.
