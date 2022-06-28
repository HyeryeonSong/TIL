# JavaScript


### 객체지향언어(Object-oriented Language)

+ class : template
+ object : instance of class


### Class 선언
```javascript
// constructor
constructor(name, age){
  this.name = name;
  this.age = age;
}

// methods
speak() {
  console.log(`${this.name}: hello!`)
}

const amy = new Person('amy', 20);
console.log(amy.name); // amy
console.log(amy.age); // 20
amy.speak(); // amy: hello!
```


### Getter and setters
+ get : 인수가 없는 함수. 프로퍼티를 읽을 때 동작 / 값을 return
+ set : 인수가 하나인 함수, 프로퍼티에 값을 쓸 때 동작 / 값을 설정 할 수 있음.

### Fields(public, private)
+ 최신기능으로, 지원되지 않는 브라우저가 많음
```javascript
class Experiment {
  publicField = 2, // 외부에서도 출력 가능
  #privateField = 0, // 앞에 #을 붙일경우 외부로 출력이 불가능
}

const experiment = new Experiment();
console.log(experiment.publickField); // 2
console.log(experiment.privateField); // undefined
```

### 상속(inheritance) & 다양성
+ a way for one class to extend another class.
```javascript
class Shape {
  constructor(width, height, color){
    this.width = width;
    this.height = height;
    this.color = color;
  }

  draw() {
    console.log(`drawing ${this.color} color of`)
  }

  getArea() {
    return this.width * this.height;
  }
}

class Rectangle extends Shape {}
class Triangle extends Shape {
  draw() {
    super.draw(); // 이전에 작성한 함수도 호출하고 싶을때
    console.log('triangle!') // triangle!
  }

  getArea(){ // default : 필요한 함수만 overwrite(이전에 작성한 함수는 호출되지 않음)
    return (this.width * this.height) / 2;
  }
}

const rectangle = new Rectangle(20, 20, 'blue');
rectangle.draw(); // drawing blue color of
console.log(reactangle.getArea()); // 400

const triangle = new Triangle(20, 20, 'red');
triangle.draw(); // drawing red color of
console.log(triangle.getArea()); // 20


```


## 유용한 사이트
+ [JavaSccript MDN reference](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference) 
  + 자바스크립트 내부에 포함되어있는 오브젝트들의 종류 등을 확인할 수 있음 
