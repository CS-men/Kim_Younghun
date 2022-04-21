## 1. 파이썬에는 .pyc 파일이 있습니다. .py 파일과의 차이점을 설명하세요.

두 파일 모두 바이트코드를 가지고 있지만 .pyc는 .py 파일의 컴파일된 버전입니다. 플랫폼에 독립적인 바이트코드를 가지고 있습니다. 따라서, 우리는 .pyc 형식을 지원하는 어떤 플랫폼에서도 그것을 실행할 수 있으며, Python은 성능을 향상시키기 위해 자동으로 .pyc 파일을 생성합니다. .pyc 파일은 PVM(Python Virtual Machine)에 의해 실행되고, 지워도 되지만, 성능 저하가 생길 수 있습니다.



## 2. try... except... else 구문에서 else는 언제 실행되나요?

if..else 블록에서는 if 조건문이 False 일때 else 구문이 실행되지만, try... except... else 구문에서는 try 구문에서 exception이 생기지 않는 경우에만 else 구문이 실행 됩니다.



## 3. Python은 open()을 통해 파일을 열 때, 파일 처리 모드를 설정합니다. 어떤 모드가 있나요?

파이썬에 파일 처리 모드 종류는 다음과 같습니다.

- 읽기 전용 – 'r'
- 쓰기 전용 – 'w'
- 읽기-쓰기 – 'rw'
- 덧붙이기 – 'a'

또한, 't' 옵션으로 텍스트 파일을 열 수 있는데요. 텍스트 파일을 읽기 위해 열려면 'rt' 모드를 사용할 수 있습니다. 그리고 이진(바이너리) 파일의 경우 'b'를 사용합니다.



## 4. try...raise...finally 구문이 어떻게 작동하는지 설명해 주세요.

이 구문은 우리가 예외 처리를 할 때 사용하는 키워드들 입니다. 우리는 try 블록 안에 오류가 발생할 가능성이 있는 코드를 넣고, raise 구문으로 오류를 명시적으로 제기하며, 어쨌든 마지막으로 실행하고자 하는 코드를 finally 블록에 씁니다.

```python
try:
    raise KeyboardInterrupt
finally:
    print('Goodbye, world!')


>>> Goodbye, world!
Traceback (most recent call last):
  File "python.py", line 5, in <module>
    raise KeyboardInterrupt
KeyboardInterrupt
```



## 5. 파이썬에서 언더스코어(_) 는 언제 사용하나요?

인터프리터가 사용하고, 값을 무시하고 싶을때나, 변수 앞뒤에 붙여 다른 의미로 사용하기도 합니다. PEP 15에서는 숫자 리터럴의 자릿수 구분자 역할이 추가되었습니다.