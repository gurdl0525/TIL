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
#### 요소는 "ed아래와 같이 속성을 가질 수 있습니다.
```
<p class="editor-note">My cat is very grumpy</p>
```
#### 속성은 요소에 실제론 나타내고 싶지 않지만<br>추가적인 내용을 담고 싶을 때 사용합니다.<br><br>속성을 사용할 때에는 아래 내용을 지켜야 합니다.
+ 요소 이름 다음에 바로 오는 속성은 요소 이름과<br>속성 사이에 공백이 있어야 되고, 하나 이상의<br>속성들이 있는 경우엔 속성 사이에 공백이 있어야 합니다.
+ 속성 이름 다음엔 등호(=)가 붙습니다.
+ 속성 값은 열고 닫는 따옴표로 감싸야 합니다.