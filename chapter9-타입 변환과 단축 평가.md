## 9.1 타입 변환이란?
- 자바스크립트의 모든 값은 타입이 있다. 값의 타입은 개발자의 의도에 따라 다른 타입으로 변환할 수 있다. 개발자가 의도적으로 값의 타입을 변환하는 것을 
**명시적 타입 변환** 또는 **타입 캐스팅**이라 한다.
  ```javascript
  var x = 10;
  var str = x.toString();
  console.log(typeof str, str); // string 10
  
  // 그렇다고 변수 x의 값이 변경된 것은 아니다.
  console.log(typreof x, x); // number 10
  ```
- 자바스크립트 엔진에 의해 암무적으로 타입이 자동 변환되기도 한다. 이를 **암묵적 타입 변환** 또는 **타입 강제 변환**이라 한다.
  ```javascript
  var str = x + '';
  console.log(typrof str, str) // string 10
  ```
- 암묵적 타입 변환은 기존 변수 값을 재할당하여 변경하는 것이 아니다. 자바스크립트 엔진은 표현식을 에러 없이 평가하기 위해 피연산자의 값을 암묵적으로 타입 변환해 새로운 타입의 값을 만들어 
단 한 번 사용하고 버린다.

## 9.3 명시적 타입 변환
- String()
- Number()
- Boolean()

## 9.4 단축 평가
  ```javascript
  'Cat' && 'Dog' // -> "Dog"
  ```
- 논리곱 연산다는 두 개의 피연산자가 모두 true로 평가될 때 true를 반환한다. 또한, 논리곱 연산자는 좌항에서 우항으로 평가가 진행된다.
- 논리곱 연산자는 논리 연산의 결과를 결정하는 두 번째 피연산자, 즉 문자열 'Dog'를 그대로 반환한다.

  ```javascript
  'Cat' || 'Dog' // -> 'Cat'
  ```
- 논리합 연산자는 두 개의 피연산자중 하나만 true로 평가되어도 true를 반환한다.
- 첫 번째 피연산자 'Cat'은 Truthy의 값이므로 true로 평가횐다. 이 시점에서는 두 번째 피연산자까지 평가를 진행하지 않아도 되므로 논리 연산의 결과를 결정한 
첫 번째 피연산자 'Cat'을 그대로 반환한다.
- 논리 연산의 결과를 결정하는 피연산자를 타입 변환하지 않고 그대로 반환하는 것을 `단축 평가`라고 한다. 단축 평가는 표현식을 평가하는 도중에 평가 결과가 확정된 셩우 나머지 평가 과정을 
생략하는 것을 말한다.
  ```javascript
  // 논리합(||) 연산자
  'Cat' || 'Dog' // -> "Cat"
  false || 'Dog' // -> "Dog"
  'Cat' || false // -> "Cat"
  
  // 논리곱(&&) 연산자
  'Cat' && 'Dog' // -> "Dog"
  false && 'Dog' // -> false
  'Cat' && false // -> false
  ```
