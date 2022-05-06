## 1. 다형성(polymorphism)이란?

다형성이란 여러 형태를 취할 수 있는 능력을 뜻한다. 

* 예를 들어, 부모 클래스가 'ABC'라는 이름의 메서드를 가지고 있다고 가정할 때, 그의 자식 클래스도 동일한 'ABC'라는 이름의, 고유한 파라미터와 변수를 가지고 있는 메서드를 소유할 수 있다는 것이다.



## 2. `__init__()`이란?

객체지향프로그래밍 용어에서 쓰이는 생성자와 동일한 파이썬 클래스에서 예약된 함수이다.

* 언제든지 새로운 객체가 시작될 때 자동으로 호출되고, 새로운 객체가 생성되는 순간에 바로 메모리를 할당한다.
* 변수를 초기화하기 위해서도 사용될 수 있다.



## 3. lambda와 def의 차이점은?

* ### def

  * ```python
    def add(x, y):
        return x + y
    print(add(3,5))
    
    #출력결과 >> 8
    ```

  * 함수의 이름이 선언되어야 한다.

  * 함수를 거친 결과를 return 값으로 반환한다.

  * **재사용이 필요할 경우 def를 통해 함수를 선언한다**

* ### lambda

  * ```python
    add = lambda x,y: x+y
    print(add(2,3))
    
    #출력결과 >> 5
    ```

  * 기본적으로 이름이 없는 함수를 만든다.

  * 한 줄로 더 간결하게 사용할 수 있다.

  * return 키워드를 사용하지 않는다.

  * **일회성 함수를 사용하고 싶을 때 lambda를 활용한다**

  

## 4. Garbage Collector의 작동방식을 설명해주세요.

* 파이썬에서 메모리를 관리하는 방법

  * Generational Garbage Collection(세대별 가비지 컬렉션)
  * **Reference Counting(레퍼런스 카운팅)** -- 주로 사용

* 레퍼런스 카운팅이란 우리가 객체를 만들 때마다 그 객체가 얼마나 사용되고 있는지 카운팅한다. 객체가 참조될 때마다 증가, 참조 해제 시 감소하는데, 이 값이 0이 되면 메모리 할당을 해제한다.

* ```python
  import sys
  
  text = '나는 쓰레기차다!'
  print(sys.getrefcount(text))
  
  lst = [text]
  print(sys.getrefcount(text))
  
  tup = (text)
  print(sys.getrefcount(text))
  
  tup = 0
  print(sys.getrefcount(text))
  
  lst = 0
  print(sys.getrefcount(text))
  
  >>> 2
  >>> 3
  >>> 4
  >>> 3
  >>> 2
  # 처음 print 할 때 count+1, 그 이후는 pass
  ```

  

## 5. GIL이란 무엇인가요?

* Global Interpreter Lock
* 한 스레드만이 파이썬 인터프리터를 컨트롤할 수 있게 해주는 Lock
* 하나의 스레드에 모든 자원을 허가하고, 그 후에는 락을 걸어 다른 스레드는 실행할 수 없도록 막아버림![img](https://blog.kakaocdn.net/dn/bAMe0O/btqHOZLSxjm/g3KOLQOBuZAFZQ5tz5OrK0/img.png)

* 사용하는 이유
  * 멀티스레드인 경우 여러 스레드가 하나의 객체를 사용한다면, reference count를 관리하기 위해 모든 객체에 대한 lock이 필요할 것
  * refcount를 수정하려고 할 때마다 lock을 걸어야 하는데 모든 객체에 lock을 거는 것도 부담이고, 데드락의 위험성도 갖고 있음
  * 이러한 비효율을 막기 위해 GIL을 사용
  * 하나의 lock을 통해 모든 객체에 대한 reference count의 동기화 문제를 해결