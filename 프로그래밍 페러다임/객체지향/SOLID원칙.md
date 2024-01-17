# SOLID 원칙

SOLID 원칙에는 단일 책임 원칙, 개방 폐쇄 원칙, 리스코프 치환 원칙, 인터페이스 분리 원칙, 의존 역전 원칙이 있습니다.

## SRP (Single Responsibility Principle, 단일 책임 원칙)

각 클래스는 하나의 책임만을 가져야 한다.

## OCP (Open Close Principle, 개방-폐쇄 원칙)

소프트웨어 요소는 확장에는 열려 있으나 변경에는 닫혀 있어야 한다

기존의 코드는 그대로, 확장은 열려 있어야 합니다.

## LSP (Liskov Substitution Principle, 리스코프 치환 원칙)

프로그램의 객체는 프로그램의 정확성을 깨뜨리지 않으면서 하위 타입의 인스턴스로 바꿀 수 있어야 한다.

부모 객체에 자식 객체를 넘어 넣어도 시스템에 문제가 발생하지 않아야 합니다.

## ISP (Interface Segregation Principle, 인터페이스 분리 원칙)

하나의 일반적인 인터페이스가 아닌 구체적인 여러 개의 인터페이스를 만들어야 한다.

## DIP (Dependency Inversion Principle, 의존 역전 원칙)

변하기 쉬운 것에 의존하는 경우 상위 클래스나 인터페이스 인터페이스로 추출하여 영향을 받지 않게 해야 한다.
