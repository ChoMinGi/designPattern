## 흐름도
<img width="900" alt="image" src="https://github.com/user-attachments/assets/25e76187-d478-4eb0-bdff-b76ddfaef477">
save() 메서드를 선언해놓은 인터페이스를 하위 클래스들이 구현하고. 만약 다른 결제수단이 추가되는 경우 팩토리 인터페이스의 코드는 변화할 필요없이 새로운 팩토리 클래스를 구현하면된다.

## 설계 관점
1. 팩토리 메서드 상위 클래스에 생성관련 인터페이스 제공
2. 객체 변환과 객체 생성을 모두 하위 클래스 내에 구현
3. v2와 객체 생성 파트가 비슷하다 느낄수 있지만 생성 책임이 팩토리 메서드의 서브클래스에 있다.
4. 변환 과정 또한 팩토리 메서드 패턴의 하위 클래스에 이임하였다.

## 설계 패턴; 팩토리 메서드 패턴
- 하위 클래스에 각 도메인 별로 `PaymentArchive` 객체로 변환하는 과정을 구현
- 팩토리 메서드를 통해 전략을 선택하고 각 결제 수단에 적합한 변환 로직을 실행

## 장점

1. 상위 클래스의 수정 없이 하위 클래스의 추가확장에 용이하기 때문에 확장성 측면에서 유리하다.
 - OCP 원칙을 잘 따른다고 봐야한다.
2. 의존성 역전 원칙(DIP)이 철저하게 지켜지기에 유연성과 재사용성이 높다.
 - 객체 생성에 대한 책임이 인터페이스에 있기에 서비스 코드가 클래스에 의존하지 않는다.

## 단점
1. 확장성 측면에서는 v1 보다는 떨어지고 계층구조로 인해 코드가 비대해진다.
