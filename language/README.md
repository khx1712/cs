# JAVA

* [JVM, JRE, JDK 차이점](#JVM-JRE-JDK-차이점)
* [JVM](#JVM)
* [Garbage Collection](#Garbage-Collection)
* [VO, DTO, POJO, JavaBeans 차이점](#VO-DTO-POJO-JavaBeans)
* [람다 표현식과 함수형 인터페이스](#람다-표현식과-함수형-인터페이스)
* [직렬화(Serializable)](#직렬화(Serializable))
---

##### JVM, JRE, JDK 차이점 <a id="JVM-JRE-JDK-차이점"></a>
- ```JVM```(Java Virtual Machine)
  - 자바 바이트코드(.class)를 실행할 수 있는 주체이다.
  - 모든 자바 프로그램을 CPU나 운영 체제의 종류와 무관하게 동일하게 동작할 것을 보장하기 위해 필요하다.
  - Class Loader, JVM Memory, Execution Engine 등으로 구성된다.
- ```JRE```(Java Runtime Environment)
  - JVM이 자바 프로그램을 동작시킬 때 필요한 라이브러리 파일들과 기타 파일들을 포함하여 JVM의 실행환경을 구성한다.
  - JVM + Java API로 구성된다.
- ```JDK```(Java Development Kit)
  - JRE + 개발 도구(컴파일러, 디버거 등)로 구성된다.
- 포함관계는 JDK > JRE > JVM 순이다.

---

##### JVM <a id="JVM"></a>
- 컴파일된 자바 바이트코드는 ```Class Loader```에 의해 ```JVM Memory```에 올려지고, ```Execution Engine```에 의해 실행된다.
- 구성
![image](https://user-images.githubusercontent.com/35156064/119359057-2d175000-bce4-11eb-98cb-0f021fa811c4.png)
  - ```Class Loader```
  - ```JVM Memory```
    - Method Area(class variable)
    - Heap(instance variable)
    - JVM Language Stack(local variable)
    - PC Register
    - Native Method Stacks
  - ```Execution Engine```

---

##### Garbage Collection <a id="Garbage-Collection"></a>
- 정의 : 프로그램이 동적으로 할당했던 메모리 영역 중에서 ```unreachable```한 영역(어떤 변수도 가리키지 않게 된 영역)을 탐지하여 자동으로 해제한다.
- 장단점
  - 장점
    - 유효하지 않은 포인터 접근 방지
    - 메모리 누수 방지
  - 단점
    - 어떤 메모리를 해제할지 결정하는 데 따른 비용 발생
    - GC가 일어나는 타이밍이나 점유 시간 예측에 대한 어려움

*GC(Garbage Collection)를 수행할때, GC를 수행하기 위한 Thread 이외의 모든 Thread의 작업이 멈추는 ```stop-the-world```가 발생하므로 시스템에 큰 영향을 끼친다. 따라서, GC 옵션 등은 지속적인 튜닝과 모니터링을 통해서 해당 서비스에 가장 적합한 값을 찾는 것이 중요하다.

---

##### VO, DTO, POJO, JavaBeans 차이점 <a id="VO-DTO-POJO-JavaBeans"></a>

- ```VO(Value Object)```
  - java.lang.Integer와 같이 값(value)을 포함하고 있는 객체
- ```DTO(Data Transfer Object)```
  - 계층 간 데이터 교환을 위해 사용하는 객체
- ```POJO(Plain Old Java Object)```
  - 간단하고 경량적인 자바 객체
- ```JavaBeans```
  - Sun의 JavaBeans 컨벤션을 따르는 객체
  - JavaBeans 컨벤션
    - public default 생성자를 가져야한다.
    - 클래스의 속성은 getter/setter로 접근이 가능해야한다. 
    - 클래스는 serializable 해야한다.

---

##### 람다 표현식과 함수형 인터페이스 <a id="람다-표현식과-함수형-인터페이스"></a>

- ```함수형 인터페이스```란, ```추상 메소드```가 ```1개```인 인터페이스이다. 
- ```람다 표현식```이란, 메소드를 하나의 식으로 표현한 표현식으로, 클래스를 작성하고 객체를 생성할 필요없이 메소드를 사용가능하게 하는 것이다.
- 람다 표현식이 나오기 이전에는 ```익명 클래스```를 활용해 함수형 인터페이스를 활용하였으며, ```람다 표현식```이 나오고 나서부터는 람다 표현식을 이용해 함수형 인터페이스를 활용할 수 있게 되었다.
  - ```익명 클래스```를 사용한 경우  
  ![image](https://user-images.githubusercontent.com/35156064/120796517-dd534700-c575-11eb-88d3-5569bded880e.png)  
  - ```람다 표현식```을 사용한 경우  
  ![image](https://user-images.githubusercontent.com/35156064/120796562-eb08cc80-c575-11eb-9785-aa953f633593.png)  
- 즉, 람다 표현식은 1개의 추상 메소드를 구현한 익명 클래스와 같다고 할 수 있다.
- 람다 표현식을 사용하면 기존의 불필요한 코드를 줄이기에 코드가 간결해지며 가독성이 높아진다는 장점이 있다.
---

##### 직렬화(Serializable) <a id="직렬화(Serializable)"></a>

