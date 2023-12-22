# async, await

async, await은 프로미스를 기반으로 동작합니다.

async, await은 동기 처리처럼 프로미스를 사용할 수 있습니다. 프로미스가 아니면 async, await을 사용할 수 없습니다.

## async

async 함수는 언제나 프로미스를 반환합니다.

async 함수가 명시적으로 프로미스를 반환하지 않아도 async 함수는 암묵적으로 resolve 하는 프로미스를 반환합니다.

## await

await은 프로미스가 settled 상태가 될 때까지 대기하다가 settled 상태가 되면 resolve 한 처리 결과를 반환합니다.

## 에러 처리

async 함수 내에서 catch 문을 상용해서 에러 처리를 하지 않으면 async 함수는 발생한 에러를 reject 하는 프로미스를 반환한다.

## 활용

Promise.all, Promise.allSettled, Promise.race를 이용하여 동시에 처리해야 할 비동기는 묶어서 처리하고 순차적으로 실행해야 하는 비동기 함수들은 await 등을 이용하여 처리합니다.
