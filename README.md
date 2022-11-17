"# myTIL" 
## [javascript] 고차함수, 고차함수 메서드  
 
## 📌 일급 객체 
1. 변수에 할당할 수 있다.

2. 전달인자로 사용할 수 있다.

3. 다른 함수의 결과로서 리턴될 수 있다.

 

함수는 일급 객체이기 때문에 위 세가지 행동을 할 수 있다!  


## 📌 고차 함수
: 다른 함수를 전달인자로 받거나, 결과로서 함수를 리턴하는 함수

 

#### ◽ Callback 함수
 : 함수에서 호출하는 함수

 
#### ◽ 고차함수 메서드
◽ array.filter(callback) 

  [🍔, 🍓, ☕, 🍑, 🍉].filter( 과일 )   =>   [🍓, 🍑, 🍉]

  배열에서 함수의 불리언 값이 true인 것만 배열로 리턴한다.



◽ array.map(callback)  

  [🐥, 🐛, 👶].map( 시간 )   =>   [🐓, 🦋, 👩]

  배열 데이터를 함수를 적용한 데이터로 바꾼 배열로 리턴한다.

 

◽ array.reduce(callback, initial value)  

  [🥦, 🥑, 🥬, 🍎].reduce(손질한 재료 합치기(손질된 재료, 배열의 요소), 그릇)   =>  🥗

  배열 데이터를 반복하며 함수에 전달인자로 넣으며 누적한 값을 리턴한다.

 

  ❕ 이때 initial value는 처음 누적 값으로 사용될 인자이다. 인자를 넣지 않으면 배열의 첫번째 값이 첫 누적 값이 된다.  

 

  reduce에서 callback 함수는 보통 두개의 인자를 가진다.  

  두개의 인자는 누적되는 값과 배열에서 들어올 값이다.  

 

#### ◽ 추상화
변수에 함수를 할당하고 나면, 함수 안의 논리를 일일이 떠올리지 않아도 함수를 사용할 수 있게된다.  

이처럼 추상화를 하면 생산성이 올라간다.  

 

함수 = 값을 전달 = 값에 대한 복잡한 논리를 감춤 = 값 수준의 추상화  

고차 함수  = 함수를 전달 = 함수에 대한 복잡한 논리를 감춤 = 함수 수준의 추상화  

 

고차함수를 사용하면 더 높은 단계의 추상화가 가능해지고 생산성이 올라간다.  

 

 

#### 📝 틀렸던 문제
```javascript
function calcuate(x, y, z){
	const plus = function (num1, num2){
		return num1 + num2;
	}
	return plus(x, y) * z
}
```
위 함수가 고차함수가 아닌 이유  

1. 전달인자로 함수를 받고 있지 않다.

2. 함수의 리턴 값이 함수가 아니다.

> plus(x, y)는 이미 계산된 상수  


[진주의 개발괴발 가기](https://2realzoo.tistory.com/entry/S2-unit1-javascript-%EA%B3%A0%EC%B0%A8-%ED%95%A8%EC%88%98-%EA%B3%A0%EC%B0%A8%ED%95%A8%EC%88%98-%EB%A9%94%EC%84%9C%EB%93%9C)  

 
