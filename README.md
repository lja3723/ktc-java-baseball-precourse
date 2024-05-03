# java-baseball-precourse

## 개요

이 프로그램은 **숫자야구** 게임을 구현한다. 숫자야구란 1부터 9까지 서로 다른 수로 이루어진 3자리의 수를 맞추는 게임이다.

숫자야구에는 다음과 같은 상황이 존재하며, 프로그램은 이 상황(힌트)을 매 번 사용자에게 알린다.

- **스트라이크**
  - 같은 수가 같은 자리에 있는 경우
- **볼**
  - 숫자가 다른 자리에 있는 경우
- **낫싱**
  - 숫자가 전혀 없는 경우

사용자는 이 힌트를 이용해 상대방의 수를 맞추면 승리한다.

```
e.g.
상대방(컴퓨터)의 수가 425일 때,
- 123을 제시한 경우: 1스트라이크
- 456을 제시한 경우: 1볼 1스트라이크
- 789를 제시한 경우: 낫싱
```

## 요구 사항

- Git의 커밋 단위는 기능 목록 단위로 추가한다.
  - [AngularJS Git Commit Message Conventions](https://gist.github.com/stephenparish/9941e89d80e2bc58a153)을 참고해 커밋 메시지를 작성한다.

### 기능 요구 사항

- 위 숫자 야구 게임에서 상대방의 역할을 컴퓨터가 한다. 컴퓨터는 1에서 9까지 서로 다른 임의의 수 3개를 선택한다. 게임 플레이어는 컴퓨터가 생각하고 있는
3개의 숫자를 입력하고, 컴퓨터는 입력한 숫자에 대한 결과를 출력한다.
- 이 같은 과정을 반복해 컴퓨터가 선택한 3개의 숫자를 모두 맞히면 게임이 종료된다.
- 게임을 종료한 후 게임을 다시 시작하거나 완전히 종료할 수 있다.
- 사용자가 잘못된 값을 입력할 경우 `IllegalArgumentException` 을 발생시킨 후 애플리케이션은 종료되어야 한다.

#### 실행 결과 예 

```
숫자를 입력해 주세요 : 123
1볼 1스트라이크
숫자를 입력해 주세요 : 145
1볼
숫자를 입력해 주세요 : 671
2볼
숫자를 입력해 주세요 : 216
1스트라이크
숫자를 입력해 주세요 : 713
3스트라이크
3개의 숫자를 모두 맞히셨습니다! 게임 종료
게임을 새로 시작하려면 1, 종료하려면 2를 입력하세요.
1
숫자를 입력해 주세요 : 123
1볼
…
```

### 프로그래밍 요구사항 1

- JDK 17 버전에서 실행 가능해야 한다.
- 프로그램 실행의 시작점은 `Application` 의 `main()` 이다.
- `build.gradle` 파일은 변경할 수 없으며, 제공된 라이브러리 이외의 외부 라이브러리는 사용하지 않는다.
- 프로그램 종료 시 `System.exit()` 를 호출하지 않는다.
- 프로그래밍 요구 사항에서 달리 명시하지 않는 한 파일, 패키지 등의 이름을 바꾸거나 이동하지 않는다.

### 프로그래밍 요구사항 2

- 자바 코드 컨벤션을 지키면서 프로그래밍한다.
  - 기본적으로 [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html)을 원칙으로 한다.
  - 단, 들여쓰기는 '2 spaces'가 아닌 '4 spaces'로 한다.
- **indent(인덴트, 들여쓰기) depth를 3이 넘지 않도록 구현**한다. 2까지만 허용한다.
  - 예를 들어 while문 안에 if문이 있으면 들여쓰기는 2이다.
  - 힌트: indent(인덴트, 들여쓰기) depth를 줄이는 좋은 방법은 함수(또는 메서드)를 분리하면 된다.
- **3항 연산자를 쓰지 않는다.**
- **함수(또는 메서드)가 한 가지 일만 하도록** 최대한 작게 만들어라.
- JUnit 5와 AssertJ를 이용하여 정리한 기능 목록이 정상적으로 작동하는지 테스트 코드로 확인한다.
- 테스트 도구 사용법이 익숙하지 않다면 아래 문서를 참고하여 학습한 후 테스트를 구현한다.
  - [JUnit 5 User Guide](https://junit.org/junit5/docs/current/user-guide/)
  - [AssertJ User Guide](https://assertj.github.io/doc/)
  - [AssertJ Exception Assertions](https://www.baeldung.com/assertj-exception-assertion)
  - [Guide to JUnit 5 Parameterized Tests](https://www.baeldung.com/parameterized-tests-junit-5)

## 기능 목록

> ✔️ **일러두기**
> - [ ] : 미구현한 기능
> - [x] : 구현한 기능
> - [ ] <기능> (test: -/yes) : <기능>에 대한 테스트케이스 작성 여부

### 게임 준비

- [ ] (test: -) 컴퓨터는 서로 다른 임의의 수 3개를 선택한다.

### 게임 중

#### 사용자 인터랙션

- [ ] (test: -) 사용자 입력을 받는다.
- [ ] (test: -) 사용자 입력이 유효한 지 판단한다.
  - 유효 조건: 서로 다른 3자리 숫자 입력
- [ ] (test: -) 유효하지 않은 사용자 입력이 들어온 경우 `IllegalArgumentException`을 발생시킨다.

#### 프로그램 계산

- [ ] (test: -) 유효한 사용자 입력에 대해 일치 결과(스트라이크, 볼, 낫싱)를 계산한다.

#### 프로그램 인터랙션 

- [ ] (test: -) 계산된 일치 결과를 출력한다.
- [ ] (test: -) 계산된 일치 결과가 3 스트라이크인 경우 게임 종료 신호를 발생시킨다.

### 게임 종료

- [ ] (test: -) `IllegalArgumentException`이 발생하면 애플리케이션을 종료시킨다.
- [ ] (test: -) 게임 종료 신호를 수신하면 **게임 종료 선택지**(게임을 다시 시작하거나 애플리케이션을 종료하는 선택지)를 출력하고 사용자 입력을 받는다.
- [ ] (test: -) 게임 종료 선택지에 대한 사용자 입력이 유효한 지 판단한다.
  - 유효 조건: 1 또는 2 입력
- [ ] (test: -) 게임 종료 선택지에서 유효하지 않은 사용자 입력이 들어온 경우 `IllegalArgumentException`을 발생시킨다.
- [ ] (test: -) 게임 종료 선택지에 대한 사용자 입력에 따라 게임을 다시 시작하거나 애플리케이션을 종료시킨다.