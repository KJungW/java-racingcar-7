# java-racingcar-precourse

## :dart: 자동차 경주 구현 기능 정리

### 자동차 이름 입력 기능

- 사용자는 입력을 통해 n 대의 자동차 이름을 입력할 수 있다.
- 자동차 이름은 쉼표(,)를 기준으로 구분한다.
- 입력된 자동차 이름의 개수가 경주에 참여할 자동차 개수가 된다.
- 입력 과정 예시
  ``` 
  경주할 자동차 이름을 입력하세요.(이름은 쉼표(,) 기준으로 구분)
  pobi,woni,jun
  ```

### 전진 시도 횟수 입력 기능

- 사용자는 경주 동안 몇번의 전진 시도를 할지 입력할 수 있다.
- 전진 시도 횟수를 입력한 뒤에는 비어있는 한 줄을 출력한다.
  ``` 
  시도할 횟수는 몇 회인가요?
  5
  
  ```

### 자동차 경주 진행 기능

- 주어진 횟수 동안 n 대의 자동차는 전진 또는 멈출 수 있다.
- 각각의 자동차는 0에서 9 사이의 무작위 값이 4 이상이 나올 경우에만 전진한다.
- 자동차 경주의 우승자는 가장 많이 전진한 자동차이다.
- 우승자는 한대이거나 여러 대일 수 있다.

### 자동차 경주 결과 출력 기능

- 우승자를 출력한다.
- 우승자가 여러 명일 경우 쉼표(,) 기준으로 구분한다.
- 단일 우승자 출력 예시
  ``` 
  최종 우승자 : pobi
  ```
- 복수 우승자 출력 예시
  ``` 
  최종 우승자 : pobi, jun
  ```

### 자동차 경주 진행 상황 출력 기능

- 전진 시도를 할 때마다 자동차 이름과 전진 거리를 같이 출력한다.
- 모든 진행 상황이 출력된 후에는 비어있는 한 줄을 출력한다.
  ``` 
  실행 결과
  pobi : -
  woni :
  jun : -
  
  pobi : --
  woni : -
  jun : --
  
  pobi : ---
  woni : --
  jun : ---
  
  pobi : ----
  woni : ---
  jun : ----
  
  pobi : -----
  woni : ----
  jun : -----

  ```

### 자동차 이름 입력에 대한 검증 기능

- 비어있는 값 입력 검증
    ```
    " "    
    ```
- 자동차 이름이 한개만 입력된 경우 검증
    ```
    "green"
    "green:blue:red"
    ```
- 구분자의 양옆에 자동차 이름이 존재하지 않는 경우 검증
    ```
    ",blue,red"
    "green,,red"
    "green,blue"
    ```
- 자동차 이름이 5자보다 많을 경우 검증
    ```
    "greenCar,blueCar"
    ```
- 위와 같은 검증을 통과하지 못할 경우 IllegalArgumentException을 발생시킨 후 애플리케이션은 종료되어야 한다.

### 전진 시도 횟수 입력에 대한 검증 기능

- 비어있는 값 입력 검증
    ```
    " "    
    ```
- 숫자가 아닌 값이 들어올 경우 검증
    ```
    "five"
    ```
- int 범위를 벗어난 큰 값이 들어올 경우 검증
    ```
    "99999999999999999999999999999999"
    ```
- 0이나 음수가 들어올 경우 검증
    ```
    "0"
    "-10"
    ```
- 위와 같은 검증을 통과하지 못할 경우 IllegalArgumentException을 발생시킨 후 애플리케이션은 종료되어야 한다.

## :clapper: 전체 실행 결과 예시

```
경주할 자동차 이름을 입력하세요.(이름은 쉼표(,) 기준으로 구분)
pobi,woni,jun
시도할 횟수는 몇 회인가요?
5

실행 결과
pobi : -
woni :
jun : -

pobi : --
woni : -
jun : --

pobi : ---
woni : --
jun : ---

pobi : ----
woni : ---
jun : ----

pobi : -----
woni : ----
jun : -----

최종 우승자 : pobi, jun
```

## :pushpin: 올바른 과제 진행을 위한 체크리스트와 규칙

### 공통 피드백에 의한 과제 체크리스트 (체크가 필요한 것을 선별)

- **요구사항을 정확하게 준수한다.**
    - 과제 진행 요구 사항 + 기능 요구 사항 + 프로그래밍 요구 사항 준수 여부 체크
- **Git으로 관리할 자원을 고려한다.**
    - 관리할 필요가 없는 파일들을 .gitignore에 명시했는지 체크
- **커밋 메시지를 의미 있게 작성한다**
    - 7자기 약속에 맞게 커밋 메세지를 작성했는지 체크
- **커밋 메시지에 이슈 또는 풀 리퀘스트 번호를 포함하지 않는다**
    - 커밋 메시지의 이슈 도는 풀 리퀘스트 번호 포함 여부 체크
- **이름을 통해 의도를 드러낸다**
    - 이름을 통해 변수의 역할, 함수의 역할, 클래스의 역할에 대한 의도를 드러냈는지 체크
    - 연속된 숫자를 덧붙이거나(**a1**, **a2**, ..., **aN**), 불용어(**Info**, **Data**, **a**, **an**, **the**) 사용x 체크
- **축약하지 않는다**
    - 축약어를 사용하지 않았는지 체크
    - 클래스와 메서드 이름을 한두 단어로 유지하려고 노력했는지 체크
    - 문맥을 중복하는 이름 제거 체크
- **공백도 코딩 컨벤션이다**
    - if, for, while문 사이의 공백 체크
- **공백 라인을 의미있게 사용한다.**
    - 문백 분리 여부로 공백라인을 사용했는지 체크
- **스페이스와 탭을 혼용하지 않는다.**
    - 풀 리퀘스트를 작성한 후, 스페이스(space)와 탭(tab)을 혼용하지 않았는지 체크
- **의미없는 주석을 달지 않는다.**
    - 의도를 드러내기 힘든 경우에만 주석을 달았는지 체크
- **Java에서 제공하는 API를 적극 활용**
    - 기존에 Java에 구현되어 있는 기능을 불필요하게 구현하지 않았는지 체크
- **배열 대신 컬렉션 사용**
    - 배열 말고 컬렉션을 사용

### 개인 피드백에 의한 과제 체크리스트

- **어렵고 긴 요구사항은 쪼개서 구현하기**
- **객체 지향적인 프로그래밍하기**
    - MVC 패턴을 적용해 Model/View/Cotroller로 책임을 분리해 보자.
- **예외 케이스를 명확하게 분리하자**
    - 같은 예외 클래스라고 해도 예외 케이스마다 별도의 에러 메세지를 사용하기
- **README.md를 보다 풍부하게 작성하자**
    - 구현 기능 목록 (대분류와 소분류를 통해 보다 구체적으로 작성)
    - 추가로 설정한 체크리스트와 규칙
    - 과제를 수행할 때 중점적으로 신경을 쓰고자 하는 점
    - 프로젝트 디렉토리 tree 첨부하기
    - 과제 진행 중에 발생한 예상치 못한 문제와 해결 방법
    - 어떤 부분에서 리펙토링을 적용했는지
- **리펙토링**
    - 최소 2가지 이상의 파트에서 리펙토링 진행
- **목표와 진행상황 그리고 회고가 들어간 의미 있는 최종 회고록 작성**

### 커밋 메세지 체크리스트

- AngulerJS 커밋 메세지 컨밴션을 제대로 준수한다.
- ‘좋은 커밋 메세지를 작성하기 위한 7가지 약속’을 참조해 부가적인 규칙을 준수한다.
  ```
  - AngularJS 커밋 컨밴션 규칙을 지키면 자동으로 지켜지는 항목
    - 1. 제목과 본문을 한 줄 띄워 분리하기
    - 4. 제목 끝에 . 금지
  - AngularJS 커밋 컨밴션 규칙에 적용할 수 있는 항목
    - 2. 제목은 영문 기준 50자 이내로 (한글/영어 기준 40자로 결정)
    - 6. 본문은 영문 기준 72자마다 줄 바꾸기 (한글/영어 기준 50자로 결정)
    - 7. 본문은 어떻게보다 무엇을, 왜에 맞춰 작성하기
  - AngularJS 커밋 규칙을 지키기 위해 적용할 수 없는 항목
    - 5. 제목은 명령조로
        - AngularJS 커밋 규칙 : Subject line의 type은 이미 소문자로 정해져 있음
    - 3. 제목 첫글자를 대문자로
        - AngularJS 커밋 규칙 : Subject line의 type은 이미 소문자로 정해져 있음
  ```

### 지원서에 작성했던 클린코드 목표를 위한 주차별 클린코드 추가 규칙

- 1주차
    - 축약어 사용하지 않기 (ex. amt → amount, res → result)
    - 클래스명은 명사 또는 명사구로 구성하기
    - 함수명은 “동사 + 목적어”로 구성하기
- 2주차
    - 함수는 작게 만들어야한다.
        - 함수내부가 15줄이 넘어가지 않도록 설정 (SIG 참조)
    - 함수의 추상화 수준을 일관적으로 유지

## :clipboard: 과제를 수행할 때 중점적으로 신경을 쓰고자 하는 점

저번 주 과제를 보고 스스로 부족한 점을 정말 많이 느껴 피드백과 학습을 열심히 진행했다.
이번 주는 피드백과 학습을 진행하며 작성한 과제 체크리스트와 규칙을 준수하며 과제를 완료하는 것을 최우선 목표로 두고자 한다.

- 과제에 주어진 필수 요구사항 준수
- 공통/개인 피드백에 의한 체크리스트 준수
- 커밋 메세지 체크리스트 준수
- 지원서에 작성했던 클린코드 목표를 위한 주차 별 클린코드 추가 규칙 준수
- (추가) 학습했던 내용 (ex. Git심화, AssertJ, JUnit5의 ParameterizedTest 등) 적용해 보기

## :file_folder:프로젝트 구조

  ```
  ├─main
│  └─java
│      └─racingcar
│          │  Application.java
│          │
│          ├─controller
│          │      RacingController.java
│          │
│          ├─model
│          │      Car.java
│          │
│          ├─service
│          │      InputDecodeService.java
│          │      InputValidationService.java
│          │      RacingService.java
│          │
│          ├─validator
│          │      StringValidator.java
│          │
│          └─view
│                  InputView.java
│                  OutputView.java
│
└─test
    └─java
        └─racingcar
            │  ApplicationTest.java
            │  IntegrationTest.java
            │
            ├─model
            │      CarTest.java
            │
            ├─service
            │      InputDecodeServiceTest.java
            │      InputValidationServiceTest.java
            │      RacingServiceTest.java
            │
            ├─test_data_generator
            │      CarGenerator.java
            │
            └─validator
                    StringValidatorTest.java
  ```

## :pencil2:과제에서 발생한 예상치 못한 문제와 해결방안

### 문제 상황

초기 애플리케이션에서는 RacingContoller의 하나의 public 메서드 안에 모든 비즈니스 로직이 담긴 private 메서드들이 배치되어 있는 형태였다. 그래서 비즈니스 로직들을 단위 테스트하고자 할 때
비즈니스 로직을 각각 테스트하는 것이 아니라 모든 비즈니스 로직이 담긴 하나의 거대한 public 메서드를 테스트할 상황에 놓였다. 이를 어떻게 해야 할지 고민하던 중 RacingController가 혼자 너무 많은
역할을 맡고 있다는 것을 깨닫게 되었다. 그래서 비즈니스 로직을 종류별로 분류해 service로 분리하는 방안을 생각하게 되었다. 결국 controller에 있던 많은 private 메서드가 service의
public/private 메서드로 변환되도록 리펙토링을 진행했다. service의 public 메서드를 통해 비즈니스 로직들을 각각 단위 테스트를 할 수 있었다, (service의 private 메서드는 충분히
작아 public 메서드를 테스트할 때 같이 테스트를 할 수 있었다.)

### 해결과정

많은 역할을 맡고 있는 클래스로 인해 현재 프로젝트에서는 테스트 부분에서 문제가 생겼다. 하지만 만약 크기가 큰 프로젝트였다면 너무 많은 역할을 맡고 있는 클래스로 인해 클래스의 내부코드가 매우 복잡해질 것이고,
코드 재사용이 되지 않아 수많은 중복 코드가 생기게 될 것이다. 이는 코드의 가독성과 유지보수성 그리고 안정성을 떨어뜨려 애플리케이션을 망가뜨리게 될 것이다.

### 느낀점

이렇게 이번 프리코스 과제를 통해 역할이 큰 클래스로 인한 문제를 겪어보았고, 해결해 보았다. 이번 경험을 통해 역할이 커질수록 문제가 되는 것은 함수만이 클래스도 똑같다는 것을 깨닫게 되었다. 다음 주 3주차
과제에서는 클래스의 역할이 너무 커지지 않게 초기 설계를 하고, 설령 역할이 커지더라도 바로 역할을 분리하면서 과제를 진행하려고 한다.

## :high_brightness:리펙토링을 적용한 부분

리펙토링을 적용한 부분

1. 컨트롤러가 수행하고 있었던 너무 많은 책임들을 나눠 service로 분리
2. 잘못 설계된 메서드명을 수정
3. 컨트롤러의 생성자 주입을 제거
   (생성자 주입의 대상인 컨트롤러의 내부 부품이 앞으로 바뀌지 않을 것이라고 판단)

## :pill:과제를 마친 뒤에 아쉬운 점

- 시간 배분의 아쉬움
    - 공통 피드백과 개인 피드백을 통해 스스로 부족한 점을 많이 느끼게 되면서 너무 과한 학습계획을 잡았던 것 같다. 그래서 생각보다 학습 과정이 길어졌고 과제의 시작이 늦어졌다. 과제를 원하는 만큼
      완성하기는 했지만 다음 주부터는 좀 더 시간적인 배분을 해서 여유를 가지고 과제를 진행하는 편이 좋을 것 같다.
- 테스트 작성의 미숙함
    - 지금까지는 항상 Mockito와 같은 모킹 라이브러리를 가지고 테스트하다 보니 모킹없이 어떻게 테스트를 해야할지 막막했다. 사실 지금 작성한 테스트도 고칠 점이 많을 것이라 생각한다. 다음 주에는
      다른 분들의 코드를 참조하며 테스트 부분에서 고칠 점이나 발전시킬 수 있는 점이 없는지 개인 피드백 해보려고 한다.
- 개발 순서에 대한 아쉬움
    - 1주차 피드백 영상을 보고 어려운 요구사항은 쪼개서 구현한다는 점은 잘 지킨 것 같지만, 필수적인 요구사항을 먼저 빠르게 구현하고 그다음에 추가적인 요구사항을 구현해야 한다는 점은 잘 지키지 못한 것
      같다. 다음 주는 이 점을 고려해서 프로그램 구현 계획을 세워보려고 한다. 

  