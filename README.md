# 코어함수

  - 문자 (String)
  - 숫자 (Number)
  - 배열 (Array)
  - 객체 (Object)

## 문자 (String)

  ### charAt(n)

  Returns: String <br>

  : n번째에 있는 문자를 구합니다.

  ```js
  'abc'.charAt(1);      //'b'
  ```

  ### charCodeAt(n)

  Returns: Number <br>

  : n번째에 해당되는 문자값의 유니코드를 반환합니다.

  ```js
  var str = "HELLO WORLD";
  var n = str.charCodeAt(0);
  // 72  // H의 유니코드값 72를 반환
  ```
  > charCodeAt()의 역은 String.fromCharCode()입니다.

  ### concat(*str1*, *str2*, ...)

  Returns: String <br>

  : 원래 문자열에 *str1*, *str2* 등을 병합하여 반환합니다.

  ```js
  'hello'.concat(' ', 'world', '!');        // 'hello world!'
  ```

  ### indexOf(*serchString*, *position*)

  Returns: Number <br>

  : *position*(Zero-based)에서 시작해 *searchString*을 찾으면 그 위치를, 찾지 못하면 -1을 반환합니다.

  ```js
  'aXaX'.indexOf('X');      // 1
  'Apple Mango'.indexOf('Lemon');      // -1
  ```

  ### lastIndexOf(*serchString*, *position*)

  Returns: Number <br>

  : *position*(기본값은 문자열 끝)에서 시작해 *searchString*을 검색합니다. *searchString*을 찾으면 그 위치를, 찾지 못하면 -1을 반환합니다.

  ```js
  > 'aXaX'.lastIndexOf('X');        // 3
  > 'aXaX'.lastIndexOf('X', 2);     // 1
  ```

  ### replace(*search*, *replacement*)

  Returns: String <br>

  : *search*를 찾아 *replacement*로 교체합니다. *search*에는 문자열이나 정규표현식을 쓸 수 있고, *replacement*에는 문자열이나 함수를 쓸 수 있습니다.

  ```js
  var str = 'Apple Mango';
  var str2 = str.replacement('Apple', 'Lemon')
  console.log(str2);
  // 'Lemon Mango'
  ```

  ### slice(*start*, *end* + 1)

  : *start* 위치에서 시작하고 *end* 바로 앞에서 끝나는 부분 문자열을 반환합니다. 두 매개변수 모두 음수를 쓸 수 있으며, 음수를 쓰면 문자열 길이가 매개변수에 더해집니다.

   ```js
   'abc'.slice(2)       //'c'
   'Apple Mango'.slice(6,11)        //'Mango'
   'abc'.slice(-2)      //'bc'
   ```

  ### split(*separator*,*limit*)

  : *separator*로 구분한 배열을 반환하며, 매개변수는 다음 2가지입니다.

  > *separator* : 문자열 또는 정규표현식으로, 생략하면 전체 문자열을 배열 형태로 반환합니다.  <br>
  > *limit* : 반환할 배열의 최대 길이입니다.

  ```js
  > 'a, b,c, d'.split(',')          // 문자열
  //[ 'a', ' b', 'c', ' d' ]
  > 'test'.split()                  // 구분자 없음
  // [ 'test' ]
  ```

  ### substr(*start*,*length*)

  : *start* 위치에서 시작하여 가져올 *length*를 지정하며 그만큼의 문자열을 추출할 수 있습니다.

  ```js
  > var input = "abcdefg"
  > var str = input.substr(0,2);
  // "ab"
  > var input = "abcdefg"
  > var str = input.substr(2);
  // "cdefg"                        // 두번째 인자를 지정 안할 시 시작위치에서부터 문자열 끝까지의 길이가 설정됩니다.
  ```

  ### toLowerCase()

  : 원래 문자열의 문자를 모두 소문자로 바꾼 새 문자열을 반환합니다.

  ```js
  > 'HELLO'.toLowerCase()
  // 'hello'
  ```

  ### toUpperCase()

  : 원래 문자열의 문자를 모두 대문자로 바꾼 새 문자열을 반환합니다.

   ```js
   > 'hello'.toUpperCase()
   // 'HELLO'
   ```

  ### trim()

  : 문자열의 앞뒤 공백을 제거합니다.

 ```js
 > var str = '  Mango   ';
 > var newStr = str.trim();
 // 'Mango'
 ```

## 숫자 (Number)

  ### Number()

  : 숫자데이터로 변환합니다.

  ```js
   Number('');      // 0
   Number('123');       // 123
   Number(false);        // 0
   Number(true);       // 1
   Number('22 33');     // NaN
   Number('Hello');     // NaN

   console.log(typeOf Number ('hello'));   //Number


   Number('20px');      // NaN
   parseInt('20px');    // 20
   parseFloat('20px')       //20
  ```

  ### isNaN()

  : 값이 잘못된 숫자인지 판별합니다.

  ```js
  isNaN(NaN);     // true
  isNaN(33);      // false
  isNaN('33');        // false
  isNaN(true);        // false
  isNaN('2017/11/02');      //true
  isNaN(undefined);     //true
  ```

  ### parseInt()

  : 문자를 해석하여 정수로 반환합니다.

  ```js
  parseInt(1);      // 1
  parseInt('23');     // 23
  parseInt('99.9%');      // 99
  parseInt('168 cm');     // 168     <-'문자 데이터'가 숫자로 시작하는 경우, 중간에 포함된 문자 전까지만 해석합니다.
  parseInt('I am 31');        // NaN
  parseInt(true);     // NaN
  parseInt(false);      //NaN
  ```

  ### parseFloat()

  : 문자열로 변환하고 앞 공백을 잘라낸 뒤, 앞에서부터 부동소수점 숫자로 볼 수 있는 만큼을 떼어 숫자로 바꿉니다. <br>
  부동소수점 숫자로 볼 수 있는 부분이 없으면 NaN을 반환합니다.

  ```js
  parseFloat(1);        // 1
  parseFloat('23');       // 23
  parseFloat('99.9%');        // 99.9
  parseFloat('168.8 cm');     // 168.8
  parseFloat('I am 31');      // NaN
  parseFloat(true);       // NaN
  parseInt(false);      //NaN
  ```

  ### .toFixed()

  : 숫자에 소숫점 자리를 지정합니다.

  ```js
  > var number = 0.12345678912345678.toFixed(2);
  > console.log(number);
  // '0.12'
  > console.log(typeOf(number));
  //'string'
  ```
  ### .toString()

  : 숫자를 문자 데이터로 변환합니다.

   ```js
   > var str = 9876.6543.toString();
   console.log(typeOf(str));
   // 'string'
   console.log(str);
   // '9876.6543'
   ```


## 배열 (Array)

  : 배열을 다루는 함수 메소드

  ### concat(*arr1*, *arr2*, ...)

  : 수신자의 모든 요소 다음에 *arr1*의 모든 요소, 다음에 arr2의 모든 요소, 이런식으로 이어지는 새 배열을 만듭니다. 매개변수가 배열이 아니면 요소로 추가됩니다.

  ```js
  > var arr = [ 'a', 'b' ];
  > arr.concat('c', ['d', 'e'])
  // [ 'a', 'b', 'c', 'd', 'e' ]
  > arr // concat()을 호출한 배열은 바뀌지 않습니다.
  //[ 'a', 'b' ]
  ```

  ### indexOf(*searchValue*, *startIndex*)

  : *startIndex*에서 시작해 *searchValue*를 찾습니다. 찾은 것이 있으면 첫번째 인덱스를 없으면 -1을 반환합니다. *startIndex*가 음수면 배열 길이를 더하고, 생략하면 전체 배열을 검색합니다.

   ```js
   >[ 3, 1, 17 ,1, 4 ].indexOf(1)
   //1
   > [3, 1, 17, 1, 4 ].indexOf(1, 2)
   //3
   ```

  ### join(*separator*)

  : 배열 요소 전체에 toString()을 적용해 문자열로 바꾸고 그 사이에 *separator*를 끼워 넣어 만든 문자열에 반환합니다. *separator*를 생략하면 기본값은 ','입니다.

  ```js
  > [3, 4, 5].join('-')
  // '3-4-5'
  > [3, 4, 5].join()
  //'3,4,5'
  > [3,4,5].join('')
  //'345'

  > [undefined, null] join('#') // undefined와 null을 빈 문자열로 바꿉니다.
  //'#'

  > ['a',,'b'].join('-') // 배열에 있는 구멍도 빈 문자열로 바뀝니다.
  //'a--b'
  ```

  ### pop()

  : 배열에서 마지막 요소를 제거하고 그 요소를 반환합니다.

  ```js
  > var arr = [ 'a', 'b' ];
  > arr.pop()
  //'b'
  > arr
  //[ 'a' ]
  ```

  ### push()

  : 배열에 지정된 요소를 추가하고 새 길이를 반환합니다.

  ```js
  > var arr = [ 'a', 'b' ];
  > arr.push('c', 'd')
  //4
  > arr
  // [ 'a', 'b', 'c', 'd' ]
  ```

  ### reverse()

  : 배열을 역정렬해서 반환합니다.

  ```js
  > var arr = [ 'a', 'b', 'c' ];
  > arr.reverse()
  //[ 'c', 'b', 'a']
  > arr // 거꾸로 정렬됨
  //[ 'c', 'b', 'a']
  ```

  ### shift()

  : 인덱스 0에 있는 요소를 제거하고 그 요소를 반환합니다. 이어지는 요소의 인덱스는 1씩 줄어듭니다.

  ```js
  > var arr = [ 'a', 'b' ];
  > arr.shift()
  //'a'
  > arr
  //['b']
  ```
  ### slice(*begin*, *end*)

  : *begin*에서 시작해 *end* 바로 앞까지 복사해 넣은 새 배열을 반환합니다.

  ```js
  > var arr= [ 'a', 'b', 'c', 'd' ].slice(1, 3);
  //['b', 'c']

  > [ 'a', 'b', 'c', 'd' ].slice(1) // end를 생략하면 배열 길이를 기본값으로 쓰입니다.
  //['b', 'c', 'd']

  > [ 'a', 'b', 'c', 'd' ].slice() // 두 인덱스를 생략하면 배열을 복사합니다.
  //[ 'a', 'b', 'c', 'd' ]

  > [ 'a', 'b', 'c', 'd' ].slice(1, -1) //인덱스가 음수면 배열 길이를 더합니다. 따라서 -1은 마지막 요소를 참조합니다.
  //[ 'b', 'c']
  > [ 'a', 'b', 'c', 'd' ].slice(-2)
  //[ 'c', 'd' ]
  ```

  ### sort()

  : 배열을 순서대로 정렬해서 반환합니다.

  ```js
  > var arr = [ 'banana', 'apple', 'fig', 'orange'];
  > arr.sort()
  //[ 'apple', 'banana', 'fig', 'orange']

  > var arr1 = [ -1, -20, 70, 7];
  > arr.sort()
  // [ -1, -20, 7, 70]
  // 정렬할 때는 값을 문자열로 비교하므로 숫자는 정확히 정렬되지 않을 수 있습니다.
  ```
  ### splice( *start*, *deleteCount*, *elem1*, *elem2*, ...)

  : *start* 에서 시작해 *deleteCount* 만큼 제거한 후 지정된 요소를 삽입합니다. ## *start* 위치에 있는 요소를 *elem1*으로, 그 다음 요소를 *elem2*로, 이런 식으로 *deleteCount* 만큼 교체합니다.

  ```js
  > var arr = [ 'a', 'b', 'c', 'd'];
  > arr.splice(1, 2, 'x');
  //[ 'b', 'c' ]
  > arr
  //[ 'a', 'x', 'd']
  ```

  > start에는 음수도 쓸 수 있으며, 값이 음수일 경우 길이에 더해 시작 인덱스로 삼습니다. 따라서 -1은 마지막 요소를 찾습니다.
  > deleteCount는 옵션으로, 생략할 경우 인덱스 start와 그 다음에 있는 요소를 모두 제거합니다.

  ```js
  > var arr = [ 'a', 'b', 'c', 'd' ];
  > arr.splice(-2)
  //[ 'c', 'd' ]
  > arr
  //[ 'a', 'b' ]
  ```

  ### unshift()

  : 지정된 요소를 배열 맨 앞에 추가하고 새 길이를 반환합니다.

  ```js
  > var arr = ['c', 'd'];
  > arr.unshift('a', 'e')
  //4
  > arr
  //['a', 'e', 'c', 'd']
  ```
  
## 객체 (Object)

   : 자바스크립트의 거의 모든 것은 객체입니다. (기본 데이터 타입인 boolean, number, string, null, undefined 를 제외)

  > 그러면 배열의 자료형은 무엇일까?
  ```js
  > typeOf([]);
  // "object"
  ```

  > 배열은 객체를 기반으로 만들어졌으므로 배열과 객체는 상당히 비슷합니다. 차이가 있다면 배열은 요소 접근 시 **인덱스** 를 사용하지만, 객체는 **키** 를 사용한다는 점입니다.

  ### 객체의 생성방법

   **var 객체이름 = {키1: 값1, 키2: 값2, 키3: 값3... 키4:값4};**

  ```js
   > var person = {
        firstName : "Eunjung'"
        lastName : "Song"
        age : 31,
        eyeColor : "Brown"
    };
      > console.log(person);
   //  object[Object]{
   //  age: 31,
   //  eyeColor: "Brown",
   //  firstName: "Eunjung",
   //  lastName: "Song"
  ```

  ### 객체 호출방법

  : 배열과 비슷합니다. 객체 뒤에 대괄호'[ ]'나 '.'을 사용하고 키를 표시하여 객체의 요소에 접근할 수 있습니다.

  ```js
    person['firstName']      // "Eunjung"
    person['lastName']      // "Song"
    person.age              // 31
    person.eyeColor         // 'Brown'
  ```

   > 식별자가 아닌 문자를 키로 정의했을 때는 무조건 대괄호를 사용해야 객체의 요소에 접근할 수 있습니다.

   ### 속성(property)과 메소드(method)

   : 속성(property) - 객체에 연관 되어있는 값 <br>
    메소드(method) - 객체가 어떠한 행동을 하도록 시킴(동사)

   | 객체 | Properties(속성) | method(메소드) |
   |:-------------:|:----------------|:----------------|
   |![이미지](https://www.w3schools.com/js/objectExplained.gif) | car.name = Fiat <br> car.model = 800 <br> car.color = white <br> car.door = 2 | car.start() <br> car.drive() <br> car.break() <br> car.stop() |

   > 모든 자동차의 properties(성질)은 같지만 그에 해당하는 값은 다르다.
   > 모든 자동차는 같은 method(메소드)를 가지고 있지만 동작하는 방법은 다르다.

   ```js
   > var Obj = {
       number : 852,
       string : 'HELLO',
       boolean : true,
       array : [1, 2, 3, 4],
       method : function(){
   }
   };
   ```

   ### this 키워드

   : 메소드 내의 속성을 출력할 때, 자신의 속성을 분명히 표시해야 합니다. 이 때 this 키워드를 사용합니다.
   ```js
   > var person = {
        name : '타마짱'
        eat : function (food) {
            console.log(this.name + '은 ' + food + '을/를 먹습니다.');
        }
   };

   > person.eat('과자');

   // 타마짱은 과자을/를 먹습니다.
   ```
   > ++c언어, Java와 같은 프로그래밍 언어처럼 객체 내부에서 this 키워드를 생략 할 수 없습니다. 객체 내부에서 객체의 변수에 접근하려면 반드시 this 키워드를 사용해야만 합니다.







