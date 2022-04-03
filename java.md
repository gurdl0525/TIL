#  java 문법
## PRINT
+ println
#### 자바의 기본 출력형이며 다음과 같을 때 에는 <br>str이라는 변수 안에 있는 HelloWorld라는 문장을 출력한다.
```
    String str = "HelloWorld";
    System.out.println(str);
```
#### 하지만 다음과 같이 변수 이름을 ""(큰따옴표)안에<br>집어 넣게 되면 HelloWorld대신 str이라는 변수 이름을 출력한다.<br>사실 변수 이름이 아니라 str을 문장으로 받아들여 그자체를 출력한 것이다.
```
    String str = "HelloWorld";
    System.out.println("str");
```
##### (단축키->sout엔터)<br><br>
+ printf
#### printf도 println과 생긴 것은 비슷하나 차이점이 하나 존재한다. 
```
    int num = 56;
    System.out.printf("%d", num);
```
#### 바로 C언어의 printf와 출력하는 방법이 같다.<br>println은 변수를 출력할때 ()안에 넣으면 <br>바로 출력되는 반면 printf는 ()안에 ""를 넣고<br>그안에 자료형을 써준 후 ""뒤에 ,를 찍고 변수를 써준다.
##### (단축키->souf엔터)<br><br>

## SCAN
#### 자바의 스캔은 여러과정이 필요하다.<br>클래스를 선택한다.
```
package lec1;

public class hello {
    // public static void main(String[] args) 도 
    // main엔터하시면 인텔리제이가 알아서 쳐줍니다.
    public static void main(String[] args) {

    }
}
```
#### 그 다음 
```
package lec1;

import java.util.Scanner;
// Scanner쳤을때 엔터누르면 생깁니다.

public class hello {
 
    public static void main(String[] args) {
    
    Scanner
    // Scanner를 쳤을때 엔터 한번을 눌러주세요.
    // 안 그러면 오류납니다.
     
    }
}
```
#### 그 다음 먼저 스캐너를 생성해 줍니다.
```
package lec1;

import java.util.Scanner;

public class hello {
 
    public static void main(String[] args) {
    // 입력받을 스캐너를 만든다. 그리고 System안으로 스캔한다.
    Scanner scan = new Scanner(System.in);
    // scan은 스캐너이름 영어로 되어있다면 바꿀 수있다.
     
    }
}
```
#### 스캔받을 스캐너 생성후엔 직접 스캔을 받아봅시다!
```
package lec1;

import java.util.Scanner;

public class hello {
 
    public static void main(String[] args) {

    Scanner scan = new Scanner(System.in);

//  자료형+변수이름=스캐너이름.next자료형();
//  자료형에는 문장:String 정수:int 등등 대체가능
//  물론 변수이름도 변경 가능

    String str = scan.nextLine();

//  next다음엔 String은 Line 
//  int형은 Int, double 형은 Double을 써주면 된다.

    }
}
```
#### 이렇게 스캔을 받아서 str(변수)안에 집어 넣었다. <br><br>

## 연산자
#### 연산자 또한 C언어와 굉장히 유사하다.
```
package lec2;

public class opt {
    public static void main(String[] args) {

    System.out.println(1 == 2); //거짓. false 출력
    System.out.println(1 == 1); //진실. true 출력
    System.out.println("one" == "two"); //거짓. false 출력
    System.out.println("one" == "one"); //진실. true 출력

    System.out.println("\n");

    System.out.println(1 != 2); //진실. true 출력
    System.out.println(1 != 1); //거짓. false 출력
    System.out.println("one" != "two"); //진실. true 출력
    System.out.println("one" != "one"); //거짓. false 출력

    // >,<,>=,<=도 위와같이 참,거짓으로 출력
    System.out.println("\n");

    String a = "HelloWorld";
    String b = new String("HelloWorld");
    System.out.println(a == b);
    System.out.println(a.equals(b));

    }
}
```
#### 와 같이 C언어처럼 <br>!= 은 둘이 같으면 flase, 둘이 같지 않으면 true 출력하고<br>== 은 둘이 같으면 true, 둘이 같지 않으면 false값을 출력한다.<br>
#####  나머지 연산자 C와 같음으로 생략<br><br>

## 조건문
+ if
#### if문 역시 C언어와 굉장히 유사하다.
```
package lec3;

public class conditional {
    public static void main(String[] args) {

    //  먼저 변수 생성
        int num1 = 5;
        int num2 = 1;

    //  C언어 처럼 ()안에 조건식을 넣고 
    //  조건식이 참이라면 {}안에 코드를 실행한다.
        if(num1 > num2){
            System.out.println(num1);
        }
    }
}
```
+ else
#### else if와 else도 마찬가지이다.
```
package lec3;

public class conditional {
    public static void main(String[] args) {

        int num1 = 5;
        int num2 = 1;

        if (num1 > num2){
            System.out.println(num1);
        }

        //  if()에 만족하지 않을 때,
        //  else if()안에 식을 만족할 때
        else if (num2 > num1){
            System.out.println(num2);
        }
        else{
            System.out.printf("%d = %d", num1, num2);
        }
    }
}
```
#### 처럼 사용할 수 있으며<br>C언어와 한가지 다른점이 있는데<br>바로 String 문장형 자료를 사용할때는<br>== 대신 .equals()를 사용한다.
+ ex)
```
package lec3;

public class conditional {
    public static void main(String[] args) {

        String str = "HelloWorld";

        if (str.equals("HelloWorld)){
            System.out.println(str);
        }
        else{
            System.out.println("not");
        }
    }
}
```
#### 와 같이 사용가능 하다.<br><br>


## 전처리기
#### 자바는 전처리기를 지원하지 않는다.<br>따라서 다음과같은 방법을 사용한다.
```
//  1.먼저 변수 하나를 생성한다.
public class define {
    public static final boolean DEBUG = true;

//  2. 사용하고 싶은 곳에서 아래와 같이 사용한다.
    if (JFTPD.DEBUG) 
        System.out.println(strLine);
}
```
=======
#  java 문법
## PRINT
+ println
#### 자바의 기본 출력형이며 다음과 같을 때 에는 <br>str이라는 변수 안에 있는 HelloWorld라는 문장을 출력한다.
```
    String str = "HelloWorld";
    System.out.println(str);
```
#### 하지만 다음과 같이 변수 이름을 ""(큰따옴표)안에<br>집어 넣게 되면 HelloWorld대신 str이라는 변수 이름을 출력한다.<br>사실 변수 이름이 아니라 str을 문장으로 받아들여 그자체를 출력한 것이다.
```
    String str = "HelloWorld";
    System.out.println("str");
```
##### (단축키->sout엔터)<br><br>
+ printf
#### printf도 println과 생긴 것은 비슷하나 차이점이 하나 존재한다. 
```
    int num = 56;
    System.out.printf("%d", num);
```
#### 바로 C언어의 printf와 출력하는 방법이 같다.<br>println은 변수를 출력할때 ()안에 넣으면 <br>바로 출력되는 반면 printf는 ()안에 ""를 넣고<br>그안에 자료형을 써준 후 ""뒤에 ,를 찍고 변수를 써준다.
##### (단축키->souf엔터)<br><br>

## SCAN
#### 자바의 스캔은 여러과정이 필요하다.<br>클래스를 선택한다.
```
package lec1;

public class hello {
    // public static void main(String[] args) 도 
    // main엔터하시면 인텔리제이가 알아서 쳐줍니다.
    public static void main(String[] args) {

    }
}
```
#### 그 다음 
```
package lec1;

import java.util.Scanner;
// Scanner쳤을때 엔터누르면 생깁니다.

public class hello {
 
    public static void main(String[] args) {
    
    Scanner
    // Scanner를 쳤을때 엔터 한번을 눌러주세요.
    // 안 그러면 오류납니다.
     
    }
}
```
#### 그 다음 먼저 스캐너를 생성해 줍니다.
```
package lec1;

import java.util.Scanner;

public class hello {
 
    public static void main(String[] args) {
    // 입력받을 스캐너를 만든다. 그리고 System안으로 스캔한다.
    Scanner scan = new Scanner(System.in);
    // scan은 스캐너이름 영어로 되어있다면 바꿀 수있다.
     
    }
}
```
#### 스캔받을 스캐너 생성후엔 직접 스캔을 받아봅시다!
```
package lec1;

import java.util.Scanner;

public class hello {
 
    public static void main(String[] args) {

    Scanner scan = new Scanner(System.in);

//  자료형+변수이름=스캐너이름.next자료형();
//  자료형에는 문장:String 정수:int 등등 대체가능
//  물론 변수이름도 변경 가능

    String str = scan.nextLine();

//  next다음엔 String은 Line 
//  int형은 Int, double 형은 Double을 써주면 된다.

    }
}
```
#### 이렇게 스캔을 받아서 str(변수)안에 집어 넣었다. <br><br>

## 연산자
#### 연산자 또한 C언어와 굉장히 유사하다.
```
package lec2;

public class opt {
    public static void main(String[] args) {

    System.out.println(1 == 2); //거짓. false 출력
    System.out.println(1 == 1); //진실. true 출력
    System.out.println("one" == "two"); //거짓. false 출력
    System.out.println("one" == "one"); //진실. true 출력

    System.out.println("\n");

    System.out.println(1 != 2); //진실. true 출력
    System.out.println(1 != 1); //거짓. false 출력
    System.out.println("one" != "two"); //진실. true 출력
    System.out.println("one" != "one"); //거짓. false 출력

    // >,<,>=,<=도 위와같이 참,거짓으로 출력
    System.out.println("\n");

    String a = "HelloWorld";
    String b = new String("HelloWorld");
    System.out.println(a == b);
    System.out.println(a.equals(b));

    }
}
```
#### 와 같이 C언어처럼 <br>!= 은 둘이 같으면 flase, 둘이 같지 않으면 true 출력하고<br>== 은 둘이 같으면 true, 둘이 같지 않으면 false값을 출력한다.<br>
#####  나머지 연산자 C와 같음으로 생략<br><br>

## 조건문
+ if
#### if문 역시 C언어와 굉장히 유사하다.
```
package lec3;

public class conditional {
    public static void main(String[] args) {

    //  먼저 변수 생성
        int num1 = 5;
        int num2 = 1;

    //  C언어 처럼 ()안에 조건식을 넣고 
    //  조건식이 참이라면 {}안에 코드를 실행한다.
        if(num1 > num2){
            System.out.println(num1);
        }
    }
}
```
+ else
#### else if와 else도 마찬가지이다.
```
package lec3;

public class conditional {
    public static void main(String[] args) {

        int num1 = 5;
        int num2 = 1;

        if (num1 > num2){
            System.out.println(num1);
        }

        //  if()에 만족하지 않을 때,
        //  else if()안에 식을 만족할 때
        else if (num2 > num1){
            System.out.println(num2);
        }
        else{
            System.out.printf("%d = %d", num1, num2);
        }
    }
}
```
#### 처럼 사용할 수 있으며<br>C언어와 한가지 다른점이 있는데<br>바로 String 문장형 자료를 사용할때는<br>== 대신 .equals()를 사용한다.
+ ex)
```
package lec3;

public class conditional {
    public static void main(String[] args) {

        String str = "HelloWorld";

        if (str.equals("HelloWorld)){
            System.out.println(str);
        }
        else{
            System.out.println("not");
        }
    }
}
```
#### 와 같이 사용가능 하다.<br><br>


## 전처리기
#### 자바는 전처리기를 지원하지 않는다.<br>따라서 다음과같은 방법을 사용한다.
```
package lec4;

public class define {
    public static void main(String[] args) {

//  1.먼저 변수 하나를 생성한다.
    public static final boolean DEBUG = true;

//  2. 사용하고 싶은 곳에서 아래와 같이 사용한다.
    if (JFTPD.DEBUG) 
        System.out.println(strLine);

    }
}
```
<br><br>

## 형변환
#### 형식이 다른 데이터를 더하려면 한쪽의 데이터 타입을<br>다른 쪽의 데이터 타입으로 전환 해야한다.<br>따라서 이러한 형 번환을 자바가 자동으로<br>처리해주는 것을 자동 형 변환 이라고 한다.
+ 자동(암시적) 형 변환
```
package lecc5;

public class conversion {
    public static void main(String[] args) {

    //  double 형 변수 a에 float형인 
    //  3.0을 집어넣기 위해 3.0F라고 써준다.
        double a = 3.0F;

    //  반면 0.123456789는 double형 변수이기 때문에
    //  float형에 담을 수 없다.
        float b = 0.123456789;
    }
}
```
#### 따라서 byte -> short은 되지만<br>short -> byte는 되지 않는다.
===========================
#### byte->short<br>-----------------> int-> long -> float -> double
#### char->
===========================
+ 명시적 형 변환
#### 수동으로 형 변환 하는 것을 <br>명시적 형변환 이라 한다.
```
package lecc5;

public class conversion2 {
    public static void main(String[] args) {
  
    //  int형 변수 a에 float형 변수 0.3214를
    //  넣기 위해 명시적으로 형 변환을 해준다.
        int a = (int)1.3214F;

        System.out.println(a);
    }
}
```
#### 위와 같은 경우를 보면 자동 형 변환에서는 int형이<br>float형에 1뒤 .3214값을 담을 수 없어서 오류가 났지만<br>명시적 형 변환은 1뒤에 값을 모두 반올림 후<br>버려 버리기 때문에 1만 출력하게 된다.<br>따라서 자동 형 변환 보다는 자유로우나<br>자료형을 벗어난 값을 손실 하기 때문에 주의 해야 한다.
>>>>>>> Stashed changes
