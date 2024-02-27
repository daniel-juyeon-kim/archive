## ER_NOT_SUPPORTED_AUTH_MODE: Client does not support authentication protocol requested by server

### 문제 상황

- typeorm의 quick start > Installation 과정 후 아래 에러 발생

#### log

```shell
ts-node main.ts
Error: ER_NOT_SUPPORTED_AUTH_MODE: Client does not support authentication protocol requested by server; consider upgrading MySQL client
    at Handshake.Sequence._packetToError (/Users/gimjuyeon/Documents/learn-typeorm/node_modules/mysql/lib/protocol/sequences/Sequence.js:47:14)
    at Handshake.ErrorPacket (/Users/gimjuyeon/Documents/learn-typeorm/node_modules/mysql/lib/protocol/sequences/Handshake.js:123:18)
    at Protocol._parsePacket (/Users/gimjuyeon/Documents/learn-typeorm/node_modules/mysql/lib/protocol/Protocol.js:291:23)
    at Parser._parsePacket (/Users/gimjuyeon/Documents/learn-typeorm/node_modules/mysql/lib/protocol/Parser.js:433:10)
    at Parser.write (/Users/gimjuyeon/Documents/learn-typeorm/node_modules/mysql/lib/protocol/Parser.js:43:10)
    at Protocol.write (/Users/gimjuyeon/Documents/learn-typeorm/node_modules/mysql/lib/protocol/Protocol.js:38:16)
    at Socket.<anonymous> (/Users/gimjuyeon/Documents/learn-typeorm/node_modules/mysql/lib/Connection.js:88:28)
    at Socket.<anonymous> (/Users/gimjuyeon/Documents/learn-typeorm/node_modules/mysql/lib/Connection.js:526:10)
    at Socket.emit (node:events:519:28)
    at Socket.emit (node:domain:488:12)
    --------------------
    at Protocol._enqueue (/Users/gimjuyeon/Documents/learn-typeorm/node_modules/mysql/lib/protocol/Protocol.js:144:48)
    at Protocol.handshake (/Users/gimjuyeon/Documents/learn-typeorm/node_modules/mysql/lib/protocol/Protocol.js:51:23)
    at PoolConnection.connect (/Users/gimjuyeon/Documents/learn-typeorm/node_modules/mysql/lib/Connection.js:116:18)
    at Pool.getConnection (/Users/gimjuyeon/Documents/learn-typeorm/node_modules/mysql/lib/Pool.js:48:16)
    at /Users/gimjuyeon/Documents/learn-typeorm/node_modules/typeorm/src/driver/mysql/MysqlDriver.ts:1268:18
    at new Promise (<anonymous>)
    at MysqlDriver.createPool (/Users/gimjuyeon/Documents/learn-typeorm/node_modules/typeorm/src/driver/mysql/MysqlDriver.ts:1265:16)
    at MysqlDriver.connect (/Users/gimjuyeon/Documents/learn-typeorm/node_modules/typeorm/src/driver/mysql/MysqlDriver.ts:400:36)
    at DataSource.initialize (/Users/gimjuyeon/Documents/learn-typeorm/node_modules/src/data-source/DataSource.ts:253:27)
    at Object.<anonymous> (/Users/gimjuyeon/Documents/learn-typeorm/src/main.ts:32:15) {
  code: 'ER_NOT_SUPPORTED_AUTH_MODE',
  errno: 1251,
  sqlMessage: 'Client does not support authentication protocol requested by server; consider upgrading MySQL client',
  sqlState: '08004',
  fatal: true
}
```

#### package.json

```json
"dependencies": {
    "mysql": "^2.18.1",
    "reflect-metadata": "^0.2.1",
    "typeorm": "^0.3.20"
}
```

### 문제 해결

- package.json의 mysql을 mysql2로 대체 `"mysql": "npm:mysql2@^2.1.0",`
- docker 에서 `--default-authentication-plugin=mysql_native_password`
- mysql에서 `ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '12345678';`
- **package.json의 mysql삭제 mysql2 설치**

typeorm의 문서에도 mysql2 드라이버를 설치 할 수 있다고 나와있다.

### 참고

- [stack over flow](https://github.com/typeorm/typeorm/issues/2093)
