# JAVA

* [JVM, JRE, JDK 차이점](#JVM-JRE-JDK-차이점)
* [JVM](#JVM)

---

##### JVM, JRE, JDK 차이점 <a id="JVM-JRE-JDK-차이점"></a>
- JVM
  - Java Virtual Machine
  - 자바 바이트코드(.class)를 실행할 수 있는 주체이다.
  - 모든 자바 프로그램을 CPU나 운영 체제의 종류와 무관하게 동일하게 동작할 것을 보장하기 위해 필요하다.
  - Class Loader, JVM Memory, Execution Engine 등으로 구성된다.
- JRE
  - Java Runtime Environment
  - JVM이 자바 프로그램을 동작시킬 때 필요한 라이브러리 파일들과 기타 파일들을 포함하여 JVM의 실행환경을 구성한다.
  - JVM + Java API로 구성된다.
- JDK
  - Java Development Kit
  - JRE + 개발 도구(컴파일러, 디버거 등)로 구성된다.
- 포함관계는 JDK > JRE > JVM 순이다.

---

##### JVM <a id="JVM"></a>
- Class Loader에 의해 컴파일된 자바 바이트코드를 JVM Memory에 올리고, Execution Engine에 의해 바이트코드가 실행된다.
![image](https://user-images.githubusercontent.com/35156064/119359057-2d175000-bce4-11eb-98cb-0f021fa811c4.png)

