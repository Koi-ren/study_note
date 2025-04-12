#Python #Async #Sync
## 정의

### **동기식 프로그래밍 (Synchronous Programming)**
- **설명**: 작업이 순차적으로 실행되며, 한 작업이 완료될 때까지 다음 작업이 대기하는 방식
- **특징**: 코드가 작성된 순서대로 실행되며, 작업이 끝날 때까지 프로그램은 블록(block) 상태에 있음
- **장점**:
  - 코드가 직관적이고 이해하기 쉬움
  - 디버깅이 비교적 간단함
  - 작업 순서가 중요한 경우 적합
- **단점**:
  - 시간이 오래 걸리는 작업(I/O, 네트워크 요청 등)이 있을 경우, 프로그램이 멈춘 듯한 느낌을 줄 수 있음
  - 자원 낭비 가능성(대기 시간 동안 CPU가 유휴 상태)

### **비동기식 프로그래밍 (Asynchronous Programming)**
- **설명**: 작업이 독립적으로 실행되며, 한 작업의 완료를 기다리지 않고 다음 작업을 시작하는 방식
- **특징**: 작업이 백그라운드에서 실행되며, 완료 시 콜백, 프로미스, 또는 `async/await`를 통해 결과를 처리
- **장점**:
  - I/O 작업(파일 읽기/쓰기, 네트워크 요청 등)에서 효율적
  - 사용자 경험이 향상됨(예: UI가 멈추지 않음)
  - 자원을 효율적으로 사용
- **단점**:
  - 코드가 복잡할 수 있음(콜백 지옥, 비동기 흐름 관리)
  - 디버깅이 동기식보다 어려울 수 있음

## 차이점

| **구분**           | **동기식**                              | **비동기식**                            |
|--------------------|-----------------------------------------|-----------------------------------------|
| **실행 순서**     | 순차적, 작업 완료까지 대기              | 비순차적, 작업 완료 여부와 관계없이 진행 |
| **성능**          | 시간이 오래 걸리는 작업에서 비효율적     | 시간이 오래 걸리는 작업에서 효율적      |
| **코드 복잡도**   | 간단하고 직관적                        | 상대적으로 복잡(콜백, 프로미스 등 필요) |
| **사용 사례**     | 간단한 스크립트, 순서 중요한 작업       | 네트워크 요청, 파일 I/O, 사용자 입력 처리 |

## 어떤 상황에서 어떤 방식을 선택해야 하는가?

### 동기식을 선택해야 할 때
- **작업 순서가 중요한 경우**: 예를 들어, 데이터베이스에서 데이터를 조회한 후 그 데이터를 기반으로 계산을 해야 할 때
- **간단한 작업**: 짧은 스크립트나 소규모 프로그램에서 비동기 처리의 오버헤드가 필요 없을 때
- **CPU 중심 작업**: 복잡한 연산처럼 I/O 대기가 없는 작업

### 비동기식을 선택해야 할 때
- **I/O 중심 작업**: 파일 읽기/쓰기, API 호출, 데이터베이스 쿼리 등 시간이 오래 걸리는 작업
- **사용자 경험 최적화**: UI가 멈추지 않도록 해야 하는 경우(예: 웹 애플리케이션, GUI 프로그램)
- **대량의 병렬 작업**: 여러 요청을 동시에 처리해야 할 때(예: 서버에서 다수의 클라이언트 요청 처리)

## 파이썬에서의 예시

### 동기식 프로그래밍 예시
```python
import time

def fetch_data(url):
    print(f"Fetching data from {url}...")
    time.sleep(2)  # 네트워크 요청 시뮬레이션
    print(f"Data fetched from {url}")
    return f"Data from {url}"

def main():
    start = time.time()
    result1 = fetch_data("site1.com")
    result2 = fetch_data("site2.com")
    print(result1, result2)
    print(f"Total time: {time.time() - start:.2f} seconds")

main()
```
**설명**: `fetch_data`가 순차적으로 실행되며, 첫 번째 요청이 끝날 때까지 두 번째 요청이 대기. 총 소요 시간은 약 4초

### 비동기식 프로그래밍 예시
```python
import asyncio
import time

async def fetch_data(url):
    print(f"Fetching data from {url}...")
    await asyncio.sleep(2)  # 비동기 대기
    print(f"Data fetched from {url}")
    return f"Data from {url}"

async def main():
    start = time.time()
    result1, result2 = await asyncio.gather(
        fetch_data("site1.com"),
        fetch_data("site2.com")
    )
    print(result1, result2)
    print(f"Total time: {time.time() - start:.2f} seconds")

asyncio.run(main())
```
**설명**: `fetch_data`가 병렬적으로 실행되며, 두 요청이 동시에 처리됨. 총 소요 시간은 약 2초

## 참고노트
[[비동기식 프로그래밍]]
[[동기식 프로그래밍]]