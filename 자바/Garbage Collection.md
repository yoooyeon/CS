# Garbage Collection

## Garbage Collection 이란?
가비지 컬렉션은 프로그램에서 더 이상 사용되지 않는 객체들을 식별하고 메모리를 해제하여 사용할 메모리 공간을 확보하는 것을 말한다. 
JVM에서는 Execution Engine에 GC가 위치한다. 
GC는 JVM의 Runtime Data Areas의 Heap 영역을 대상으로 작동한다. 
Heap 영역은 new 연산자로 생성되는 객체들을 저장하는 곳이다.

### Heap 영역 구조
- Young 영역
  - Eden
  - Survivor 0
  - Survivor 1
- Old 영역


### 동작 과정

1. 객체 생성
새로 생성된 객체들은 Eden 영역에 할당
Eden 영역이 가득 차면, 살아남은 객체들은 S0 또는 S1 중 하나의 Survivor 영역으로 이동
이미 한 번 Minor GC를 거친 이후에도 살아남은 객체는 다음 번 Minor GC 시에 반대쪽 Survivor 영역으로 이동

2. Minor GC
Eden 영역과 하나의 Survivor 영역이 가득 차면, 해당 영역의 살아남은 객체를 다른 Survivor 영역으로 옮기며, 동시에 더 이상 참조되지 않는 객체는 마크 후 해제
만약 Survivor 영역에 더 이상 공간이 부족하다면, 객체들 중 살아남은 것은 Old 영역으로 이동
이러한 과정을 반복하면서 Young 영역에서 더 이상 살아남지 못한 객체들은 제거

3. Major GC (Full GC)
Old 영역에 있는 객체들 중에서도 더 이상 참조되지 않는 객체들은 마크 후 해제
Major GC (또는 Full GC)는 Old 영역에서 발생하며, Old 영역 내에서의 메모리 정리를 수행
Major GC가 발생하면 일시적으로 애플리케이션 스레드가 일시 중단되는 "Stop the World" 현상이 발생

4. 메모리 재배치와 Compaction
가비지 컬렉션 후에 빈 공간이 발생하면, 이 공간을 효율적으로 사용하기 위해 메모리 재배치가 수행
이를 통해 메모리 단편화를 최소화하고 연속된 블록을 만들어 성능을 향상

### 장점
- 개발자가 동적으로 할당된 메모리 전체를 관리할 필요가 없음
### 단점
- 가비지 컬렉션이 수행되는 정확한 시점을 알 수가 없음
- 가비지 컬렉션이 실행될 때는 반드시 애플리케이션을 중지시키는 Stop The World가 수행되고 이는 오버헤드를 발생
