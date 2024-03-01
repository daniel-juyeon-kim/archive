## 문제상황

TypeORM의 DataSource의 entities속성을 "./entity/*.ts"로 변경

```shell
EntityMetadataNotFoundError: No metadata for "User" was found.
    at DataSource.getMetadata (/Users/gimjuyeon/Documents/learn-typeorm/node_modules/src/data-source/DataSource.ts:450:30)
    at /Users/gimjuyeon/Documents/learn-typeorm/node_modules/src/persistence/EntityPersistExecutor.ts:85:30
    at Array.forEach (<anonymous>)
    at /Users/gimjuyeon/Documents/learn-typeorm/node_modules/src/persistence/EntityPersistExecutor.ts:77:30
    at Array.map (<anonymous>)
    at EntityPersistExecutor.execute (/Users/gimjuyeon/Documents/learn-typeorm/node_modules/src/persistence/EntityPersistExecutor.ts:73:34)
    at processTicksAndRejections (node:internal/process/task_queues:95:5)
```

### 원인

상대경로가 아닌 절대경로를 지정해야한다.

### 해결

__dirname 사용

### 참조

https://github.com/typeorm/typeorm/issues/1327
