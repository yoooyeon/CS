# Exception
## Exception이란?
- 프로그램 실행 중 발생하는 비정상적인 상황
- 개발자가 처리할 수 있는 문제

## 해결 방법
1. **예외 던지기 / throw e**
2. **예외 처리 / try-catch 블록**

## Checked Exception, Unchecked Exception
### Checked Exception
- RuntimeException을 제외한 예외
- 컴파일러가 이 예외를 감지하고 처리 여부를 검사
- 해당 예외를 처리하는 코드를 작성하거나 메서드 선언부에 throws 절로 예외 처리를 선언
- 주로 외부 리소스에 대한 접근이나 입출력 작업, 네트워크 통신 등과 관련된 예외들이 있음
### Unchecked Exception
- RuntimeException 클래스를 상속받은 예외
- 컴파일러가 이 예외를 감지하거나 검사하지 않음
- 즉, 개발자가 별도로 예외 처리 코드를 작성하지 않아도 됨
- Unchecked Exception이 발생하면 예외를 처리하지 않은 채 프로그램이 중단될 수 있으므로, 
  개발자는 프로그램의 안정성을 고려하여 적절한 예외 처리를 해야 합니다.
