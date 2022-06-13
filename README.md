
# 자동차 경주 게임

## 기능 요구사항

- 각 자동차에 이름을 부여할 수 있다. 자동차 이름은 5자를 초과할 수 없다.  입력 예는 `pobi,crong,honux` 이다.
- 전진하는 자동차를 출력할 때 자동차 이름을 같이 출력한다. 
- 자동차 이름은 쉼표(,)를 기준으로 구분한다. 
- 전진하는 조건은 0에서 9 사이에서 random 값을 구한 후 random 값이 4이상일 경우이다. 
- 자동차 경주 게임을 완료한 후 누가 우승했는지를 알려준다. 우승자는 한명 이상일 수 있다.

## 이벤트 흐름

- 자동차 이름이 입력됐다.
- 시도할 횟수를 입력했다.
- 입력 횟수만큼 자동차들이 경쟁했다.
  - 조건에 맞는 자동차를 전진시켰다.
  - 움직인 결과를 출력했다.
- 우승한 자동차 이름를 출력했다.

## 모델링 

### 자동차 경주 게임 (RacingGame)

- 횟수를 입력한다.
    - 횟수는 자연수여야 한다.

- 게임을 시작한다.
  - 자동차 이름을 입력받아 자동차들을 생성한다.
  - 입력받은 횟수만큼 자동차들을 경쟁시킨다.


### 자동차들 (RacingCars)

상태

- 자동차의 리스트를 가지고 있다.
  - 자동차들의 이름을 입력받아 자동차의 리스트를 만든다.
  - 자동차 이름은 쉼표(,)를 기준으로 구분한다. `pobi,crong,honux` 형태로 입력받는다.
  - 자동차 이름이 고유해야 한다.
행위

- 각 자동차에게 움직인 거리를 출력하게 한다.

- 우승한 자동차 이름을 출력한다.
    - 가장 많은 거리를 움직인 자동차가 우승이다.
    - 우승자는 한명 이상일 수 있다.

- 자동차들을 경쟁시킨다.
  - 움직일지는 자동차들이 판단한다.

### 자동차 (RacingCar)

상태

- 자동차는 이름과 움직인 이동 거리를 가지고 있다.
  - 처음 생성한 자동차의 이동 거리는 0이다.
  - 자동차 이름은 5자를 초과할 수 없다.
  - 자동차 이름에는 문자열과 쉼표 외 문자열이 들어가면 안된다.
행위

- 조건에 맞으면 전진한다.
  - 전진하는 조건은 0에서 9 사이에서 random 값을 구한 후 random 값이 4이상일 경우이다.
- 움직인 결과를 출력한다.
  - 움직인 거리를 `-` 단위로 출력한다.
  - 출력 단위는 `자동차 이름 : - * 이동거리` 이다.
