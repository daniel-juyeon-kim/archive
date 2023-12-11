# this <!-- omit in toc -->

this는 자기 자신이 속한 객체, 자신이 생성할 인스턴스를 가리키는 **자기 참조 변수**입니다.

this를 통해 속한 객체, 인스턴스의 프로퍼티 메서드에 접근이 가능합니다. this는 자바스크립트 엔진에 의해 생성되고, **this 바인딩**은 함수 호출 방식에 따라 **동적으로 결정**됩니다.

## 함수 호출 방식 <!-- omit in toc -->

- [일반 함수 호출](#일반-함수-호출)
- [메서드 호출](#메서드-호출)
- [생성자 함수 호출](#생성자-함수-호출)
- [Function.prototype.call/apply/bind](#functionprototypecallapplybind)

### 일반 함수 호출

**일반 함수 호출**에서 this는 **전역 객체**가 바인딩 됩니다.

strict mode에서는 `undefined`가 바인딩 되고 콜백 함수도 일반 함수로 호출되면 전역 객체가 바인딩 됩니다.

### 메서드 호출

메서드 호출에서는 this에 **메서드를 호출한 객체**가 바인딩 됩니다.

### 생성자 함수 호출

생성자 함수 내부의 this에는 생성할 인스턴스가 바인딩 됩니다.

### Function.prototype.call/apply/bind

Function.prototype.call/apply/bind에는 Function.prototype.call/apply/bind 메서드의 첫 번째 인수로 전달한 객체가 바인딩 됩니다.

## 요약

|                함수                |                            this 바인딩 객체                            |
| :--------------------------------: | :--------------------------------------------------------------------: |
|           일반 함수 호출           |                                전역 객체                                |
|            메서드 호출             |                          메서드를 호출한 객체                          |
|          생성자 함수 호출          |                       생성자 함수가 생성할 함수                        |
| Function.prototype.call/apply/bind | Function.prototype.call/apply/bind 메서드의 첫 번째 인수로 전달한 객체 |
