## Classical inheritance
- 자동화된 메시지 전달(automatic message delegation)
- 상속 시스템은 객체가 이해하지 못한 메시지르 어디로 전달(forward)해야 하는지를 정의한다.
- 명시적으로 메시지를 위임하는 코드를 작성하지 않아도 된다.
- superclass와 subclass가 존재함

## Where should use inheritance
- 안티패턴: 메시지 송신자가 "나는 네가 누구인지 알고있다. 때문에 네가 무엇을 하는지도 안다."
- 이 패턴이 숨겨진 하위타입(subtype), 흔히 하위 클래스라 말하는 것을 드러내주고 있다.

## Multiple inheritance
- 상속은 두 객체 사이의 정의
- 첫 번째 객체(subclass)가 이해할 수 없는 메시지를 수신하면 이를 다음 객체(superclass)에게 자동으로 전달 또는 위임
- 만약 superclass가 2개 이상이라면...?(다중상속) -> 메시지 전달 대상이 모호해짐

## Rule
- 하위클래스는 상위클래스의 특수한 형태(specialization)이다.
- 상위클래스와 협업할 수 있는 모든 객체는 하위클래스에 대해 아무것도 모른 채 하위클래스와 협업할 수 있어야 한다.
- 1. 모델링하는 객체들이 명백하게 일반-특수 관계를 따라야한다.
- 2. 올바른 코딩 기술을 사용해야 한다.

## Abstract
- 추상성: 모든 구체적인 것으로부터 분리된 것
- 모두 아래로 내리고 그 다음에 필요한 것만 위로 올리기
- 새로운 상속 관계를 만드는 리팩터링을 할 때, 구체적인 것을 내리기보다는 추상적인 것을 끌어올리자

## Template method pattern
- 기본 구조를 상위클래스가 정의하고 상위클래스에서 메시지를 전송하여 하위클래스의 특수한 값을 얻는 기술
- 템플릿 메서드 패턴을 사용하는 클래스는 자신이 전송하는 메서드를 직접 구현해 놓아야 한다.

## Manage Coupling
- super같은 키워드를 이용하여, 코드 중복을 감소할 때, 상위클래스의 의존성이 높아짐
- 훅 메시지를 사용하여 하위클래스의 결합을 없앨 수 있다.
- 훅(hook) 메시지: 정해진 메서드 구현을 통해 하위클래스가 정보를 제공할 수 있도록 만들어주는 메시지
- 이를 통해, 하위클래스는 알고리즘에 대해 몰라도 되며, 상위클래스가 모든 권한을 가질 수 있게 된다.