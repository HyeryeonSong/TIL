# TypeScript


### Type 지정
```typescript
let age:number = 30;
let isAdult:boolean = true;
let a:number[] = [1,2,3];
let a2:Array<number> = [4,5,6];

let week1:string[] = ['mon', 'tue', 'wed'];
let week2:Array<String> = ['mon', 'tue', 'wed'];

```


### 튜플(Tuple) ; index별로 타입이 다를 때
```typescript
let b:[string, number];

b = ['z', 1];

b[0].toLowerCase(); // 가능
b[1].toLowerCase(); // 불가능
```

### void, never
void : 함수에서 아무것도 반환하지 않을 때 사용
```typescript
function sayHello():void{
  console.log('hello');
}
```
never : 항상 error를 반환하거나 영원히 끝나지 않는 타입으로 사용
```typescript
function showError(){
  throw new Error();
}

function infLoop(){
  whild(true){
    // do something
  }
}
```

### enum : 비슷한 값들끼리 묶기
```typescript
enum OS {
  Window,
  IOS,
  Android
}

let myOS:OS; //myOS에 OS타입을 지정(myOS엔 Window, IOS, Android만 입력 가능
myOS = OS.Window
```

### null, undefined
```typescript
let a:null = null;
let b:undefined = undefined;
```

### interface
```typescript
interface User{
  name : string;
  age : number;
  gender?: string;
}

let user : User = {
  name : 'Jenny',
  age : 30
}

user.age = 10;
user.gender = "male";

```

### interface 함수 정의
```typescript
interface Add {
  (num1:number, num2:number): number; // 숫자로 반환
}

const add : Add = function(x, y){
  return x + y;
}

add(10, 20); //

---

interface IsAdult{
  (age:number):boolean;
}

const amy:IsAdult = (age) => {
  return age > 19;
}

amy(33) // true
```

### interface로 class 정의(implements)
```typescript
interface Car {
  color: string;
  wheels: number;
  start(): void;
}

class Bmw implements Car {
  color;
  wheels = 4;
  constructor(c:string){
    this.color = c;
  }
  start(){
    console.log('go!');
  }
}

const b = new Bmw('green');
console.log(b) // Bmw: { "wheels": 4, "color": "green"}
b.start(); // go!
```


### interface 확장(extends)
```typescript
interface Car {
  color: string;
  wheels: number;
  start(): void;
}

interface Benz extends Car { // Car의 속성을 그대로 가져오고 필요한 속성은 추가로 정의
  door: number;
  stop(): void;
}

const benz : Benz = {  
  door : 5,
  stop(){
    console.log('stop!');
  };
  color: 'black',
  wheels: 4,
  start(){}
}

```