# Study

## 6-1 객체의 기본

1. 객체
- 객체는 이름과 값으로 구성되어있고 0개 이상의 프로퍼티(속성)로 구성된 집합이다.
- 배열은 요소에 접근할 때 인덱스를 사용하지만, 객체는 키를 사용하여 값에 접근한다.
- 객체 뒤에 대괄호[] 또는 온점 . 을 사용하여 객체의 값에 접근할 수 있다.
- 객체 생성 시 식별자와 문자열 모두 사용 가능하나 식별자로 사용할 수 없는 단어를 사용할 땐 문자열과 대괄호를 사용하여 키에 접근한다.

2. 속성과 메소드
- 객체 내부 값인 프로터피는 모든 형태의 자료형을 가질 수 있다.
- 함수도 객체이다. 따라서 함수는 값으로 취급할 수 있기 때문에 프로퍼티 값으로 사용할 수 있다. 
  프로퍼티 값이 함수일 경우 일반함수와 구분하기 위해 메서드(method)라 부른다.
  즉, 메서드는 객체에 묶여 있는 함수를 의미한다.
  
  ```javascript
  var circle = {
    radius: 5, // <- 프로퍼티
    
    //원의 지름
    getDiameter: function () { // <- 메서드
      return 2 * this.radius; // this는 circle을 가리킨다.
    }
   };
   console.log(circle.getDiameter()); // 10
  
  
- 메서드 내부에서 사용한 this 키워드는 객체 자신(circle 객체)을 가리키는 참조변수이다.
- 자기 자신이 가진 속성이라는 것을 표시한다.

3. 동적으로 객체 속성 추가/제거
- 객체 생성 후 속성을 지정하고 값을 입력하면 된다. 
- 객체를 곤솔 출력에서 쉽게 볼 수 있는 방법.
- 객체 속성 추가
  ```javascript
   // 객체를 선언
  const person = {
    name: 'Lee'
   };
   
   person.age = 20;
  //출력
  console.log(person); // {name: "Lee", age: 20}
  ```
  
- 객체 속성 제거
  ```javascript
  const person = {
    name: 'Lee'
   };
  
   person.age = 20; // 동적 생성
  
   delete person.age; // 생성 되었던 age 프로퍼티를 delete 연산자로 삭제
   
   delete person.address; // person 객체에 address 프로퍼티는 존재하지 않음. 따라서 사게할 수 없고, 이때 에러가 발생하지 않음.
  
   console.log(person); // {name: "Lee"}
   ```
   
4. 메소드 간단 선언 구문
ES5에서 메서드를 정의하려면 프로퍼티 값으로 함수를 할당한다.

  ```javascript
   const obj = {
   name: 'Lee',
   sayHi: function() {
    console.log('Hi!' + this.name);
      }
   };
   
   obj.sayHi(); // Hi! Lee
   ```
   
ES6에서는 메서드를 정의할 때 function 키워드를 생략한 축약 표현을 사용할 수 있다.

  ```javascript
  const obj = {
  name: 'Lee',
  //메서드 축약 표현
  sayHi() {
    console.log('Hi!' + this.name);
    }
  }
  
  obj.sayHi(); // Hi! Lee
  
  
  
  
  

