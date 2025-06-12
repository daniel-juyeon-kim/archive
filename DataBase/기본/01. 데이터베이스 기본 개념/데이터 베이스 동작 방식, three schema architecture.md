### database

관련된 데이터를 조직화한 것으로 전자적으로 저장 사용함

### DBMS

DB 정의, 만들기, 관리를 제공하는 시스템

DB를 정의하기 위해 기술한 데이터(meta data)도 DBMS를 통해 저장 관리된다.
(e.g. 데이터 유형, 구조, 제약조건, 보안, 저장, 인덱스, 사용자 그룹)

### database system

database + database system + 연관된 application, 줄여서 database라고 함

### database system 동작 방식

![alt text](<database system 동작 방식.drawio.svg>)

### data models

DB의 구조를 추상화해 표현하는데 사용하는 개념들(모델링)로 Conceptual, Logical, Physical data model이 있는데 추상화 수준, DB 구조화 방식이 다르다.

#### Data Model 종류

- Conceptual(high level) data model(개념적 모델링) (e.g. ER Diagram)
  - 일반인이 쉽게 이해할 수 있는 개념들로 이루어진 모델
  - 추상화 수준 가장 높음
  - 비즈니스 요구사항을 추상화하여 기술할 때 사용
- Logical(representational) data model(논리적 모델링)
  - 특정 DBMS에 종속되지 않으면서 실제 데이터가 저장될 때와 크게 다르지 않은 모델
- Physical(low level) data model(구조적 모델링)
  - 특정 DBMS에 종속된 모델

### DataBase Schema

Data model을 바탕으로 database의 구조를 기술한 것, 데이터베이스를 설계하고 한번 정해지면 잘 안바뀐다. (구조)

#### database state

특정 시점에 DB에 있는 실제 데이터

#### three schema architecture

각 레벨을 독립시켜 어느 레벨에서의 변화가 다른 레벨에 영향을 주지 않게 함, 실제 데이터는 internal level에 존재함

- database system을 구축하는 아키텍쳐중 하나
- user application으로 부터 물리적인 데이터베이스를 분리시키려는 목적
- 3가지 레벨이 존재하고 각각의 레벨마다 스키마가 정의되어 있음
  - external schema at external level (user view)
  - conceptual schema at conceptual level
  - internal schema at internal level

![alt text](<three schema architecture.drawio.svg>)

#### external schema (external view, user view)

- 각 사용자에 따라 필요한 내용만 공개(view)
- logical data model을 통해 표현

#### conceptual schema

- 전체 데이터베이스에 대한 구조를 기술
- 물리적인 데이터베이스에 대한 내용을 숨기고 추상화
- entities, data types, relationship, user operator, constraint에 집중
- logical data model을 통해 표현

#### internal schema

- 물리적으로 데이터가 어떻게 저장되는지 physical data model을 통해 표현
- data storage, data structure, access path(e.g. index)등의 내용 기술
