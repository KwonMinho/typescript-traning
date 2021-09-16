# typescript-traning

타입스크립트 학습하기 위한 프로젝트들 모음

타입스크립트는 우리의 멍청한 실수로 부터 보호해준다.

# grammer

타입스크립트는 예측 가능한 함수 리턴 타입, 예측 가능한 함수 인자 타입, 인터페이스와 같은 기능을 제공하여 개발할 때의 실수를 줄여준다.

<br>

```typescript
//인터페이스는 js에서 드러나지 않음
interface Human {
  name: string;
  age: number;
  gender: string;
}
```

<br>

때론, node, express, react 같은 걸 사용할 때는 interface 대신에 class를 사용하기도 한다.

```typescript
class Human {
  public name: string;
  public age: number;
  public gender: string;
  constructor(name: string, age: number, gender: string) {
    this.name = name;
    this.age = age;
    this.gender = gender;
  }
}
```

<br>

자바스크립트와 다르게, 해당 변수가 어떤 타입인지를 명시한다.

```typescript
const getBlockchain = (): Block[] => blockchain;
const getHashForBlock = (aBlock: Block): string =>
  Block.calculateBlockHash(
    aBlock.index,
    aBlock.previousHash,
    aBlock.timestamp,
    aBlock.data
  );
```

<br><br>

# 프로젝트에 typescript 셋팅

`타입스크립트 설치(global은 옵션)`

```
npm install -g typescript
```

`tsconfig.json 만들어주기`

```typescript
example of tsconfig.json
{
    "compilerOptions": {
        "module": "commonjs",
        "target": "ES2015",
        "sourceMap": true,
        "outDir": "dist"
    },
    "include": [
        "src/**/*"
    ],
    "exclude": [
        "node_modules"
    ]
}
```

`ts 파일 complie 하는 명령어`

```
tsc
```

`tsc-watch: 파일 변경될때마다 자동 빌드`

```
1. npm link typescript(전역으로 typescript 설치할때만)
2. npm install tsc-watch --dev
```

```json
  "scripts": {
    "start": "tsc-watch --onSuccess \"node dist/index.js\" "
  }
```
