# 코어함수
 —
 코어함수란?
 —
- 코어함수
    - 문자 (String)
    - 숫자 (Number)
    - 배열 (Array)

## 문자 (String)
  - length : 문자열 개수
  - charAt(n) : n번째에 있는 문자를 구합니다
  ```js
  > 'abc'.charAt(1)
  //'b'
  ```
  - charCodeAt(n) : n번째에 해당되는 문자값의 유니코드를 반환합니다.
  ```js
  > var str = "HELLO WORLD";
  > var n = str.charCodeAt(0);
  // 72  // H의 유니코드값 72를 반환
  ```
  > charCodeAt()의 역은 String.fromCharCode()입니다.

  - concat(*str1*, *str2*, ...) : 원래 문자열에 *str1*, *str2* 등을 병합하여 반환합니다.
  ```js
  > 'hello'.concat(' ', 'world', '!')
  // 'hello world!'
  ```

  - indexOf(*serchString*, *position*) : *position*(Zero-based)에서 시작해 *searchString*을 찾으면 그 위치를, 찾지 못하면 -1을 반환합니다.
  ```js
  > 'aXaX'.indexOf('X')
  // 1
  > 'aXaX'.indexOf('X', 2)
  // 3
  ```

  - lastIndexOf(*serchString*, *position*) : *position*(기본값은 문자열 끝)에서 시작해 *searchString*을 검색합니다. *searchString*을 찾으면 그 위치를, 찾지 못하면 -1을 반환합니다.
  ```js
  > 'aXaX'.lastIndexOf('X')
  // 3
  > 'aXaX'.lastIndexOf('X', 2)
  // 1
  ```

  - replace(*search*, *replacement*) : *search*를 찾아 *replacement*로 교체합니다. *search*에는 문자열이나 정규표현식을 쓸 수 있고, *replacement*에는 문자열이나 함수를 쓸 수 있습니다. *search*에 /g 플래그가 없는 정규표현식을 쓰면 일치하는 첫 번째 것만 교체됩니다.
  ```js
  > 'iixxxixx'.replace('i', 'o')
  // 'o/g/gixxixx'

  ```

  - slice(*start*, *end*) : *start* 위치에서 시작하고 *end* 바로 앞에서 끝나는 부분 문자열을 반환합니다. 두 매개변수 모두 음수를 쓸 수 있으며, 음수를 쓰면 문자열 길이가 매개변수에 더해집니다.
   ```js
   > 'abc'.slice(2)
   //'2'
   > 'abc'.slice(1,2)
   //'b'
   > 'abc'.slice(-2)
   //'bc'
   ```

  - split(*separator*,*limit*) : *separator*로 구분한 배열을 반환하며, 매개변수는 다음 2가지입니다.
  > *separator* : 문자열 또는 정규표현식으로, 생략하면 전체 문자열을 배열 형태로 반환합니다.  <br>
  > *limit* : 반환할 배열의 최대 길이입니다.
  ```js
  > 'a, b,c, d'.split(',')          // 문자열
  //[ 'a', ' b', 'c', ' d' ]
  > 'test'.split()                  // 구분자 없음
  // [ 'test' ]
  ```

  - substr(start[,count])


  - toLowerCase() : 원래 문자열의 문자를 모두 소문자로 바꾼 새 문자열을 반환합니다.
  ```js
  > 'HELLO'.toLowerCase()
  // 'hello'
  ```

  - toUpperCase() : 원래 문자열의 문자를 모두 대문자로 바꾼 새 문자열을 반환합니다.
   ```js
   > 'hello'.toUpperCase()
   // 'HELLO'
   ```

  - trim() : 문자열의 앞뒤 공백을 제거합니다.
 ```js
 > var str = '  Mango   ';
 > var newStr = str.trim();
 // 'Mango'
 ```

## 숫자 (Number)
  - Number()
  - inNaN()
  - parseInt()
  - parseFloat()
  - .toFixed()
  - .toString()


## 배열 (Array)
  - length :배열 요소의 숫자를 반환. 배열에 삽입하거나 제거할 수 있다.
  ```js
  var arr['a', 'b'];
  arr.length
  //2

  arr[arr.length] = 'c'
  arr
  //['a', 'b', 'c']
  arr.length = 1;
  arr
  ['a']
  ```
  - concat(*arr1*, *arr2*, ...): 수신자의 모든 요소 다음에 *arr1*의 모든 요소, 다음에 arr2의 모든 요소, 이런식으로 이어지는 새 배열을 만듭니다. 매개변수가 배열이 아니면 요소로 추가됩니다.
  ```js
  > var arr = [ 'a', 'b' ];
  > arr.concat('c', ['d', 'e'])
  // [ 'a', 'b', 'c', 'd', 'e' ]
  > arr // concat()을 호출한 배열은 바뀌지 않습니다.
  //[ 'a', 'b' ]
  ```

  - indexOf(*searchValue*, *startIndex*) : *startIndex*에서 시작해 *searchValue*를 찾습니다. 찾은 것이 있으면 첫번째 인덱스를 없으면 -1을 반환합니다. *startIndex*가 음수면 배열 길이를 더하고, 생략하면 전체 배열을 검색합니다.
   ```js
   >[ 3, 1, 17 ,1, 4 ].indexOf(1)
   //1
   > [3, 1, 17, 1, 4 ].indexOf(1, 2)
   //3
   ```

  - join(*separator*) : 배열 요소 전체에 toString()을 적용해 문자열로 바꾸고 그 사이에 *separator*를 끼워 넣어 만든 문자열에 반환합니다. *separator*를 생략하면 기본값은 ','입니다.
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

  - pop() : 배열에서 마지막 요소를 제거하고 그 요소를 반환합니다.
  ```js
  > var arr = [ 'a', 'b' ];
  > arr.pop()
  //'b'
  > arr
  //[ 'a' ]
  ```

  - push() : 배열에 지정된 요소를 추가하고 새 길이를 반환합니다.
  ```js
  > var arr = [ 'a', 'b' ];
  > arr push('c', 'd')
  //4
  > arr
  // [ 'a', 'b', 'c', 'd' ]
  ```

  - reverse() : 배열을 역정렬해서 반환합니다.
  ```js
  > var arr = [ 'a', 'b', 'c' ];
  > arr.reverse()
  //[ 'c', 'b', 'a']
  > arr // 거꾸로 정렬됨
  //[ 'c', 'b', 'a']
  ```

  - shift() : 인덱스 0에 있는 요소를 제거하고 그 요소를 반환합니다. 이어지는 요소의 인덱스는 1씩 줄어듭니다.
  ```js
  > var arr = [ 'a', 'b' ];
  > arr.shift()
  //'a'
  > arr
  //['b']
  ```
  - slice(*begin*, *end*) : *begin*에서 시작해 *end* 바로 앞까지 복사해 넣은 새 배열을 반환합니다.
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

  - sort() : 배열을 정렬해서 반환합니다.
  ```js
  > var arr = [ 'banana', 'apple', 'pear', 'orange'];
  > arr.sort()
  //[ 'apple', 'banana', 'orange', 'pear']
  > arr // 정렬됨
  //[ 'apple', 'banana', 'orange', 'pear']
  ```
  > 정렬할 때는 값을 문자열로 비교하므로 숫자는 정확히 정렬되지 않을 수 있습니다.

  - splice( *start*, *deleteCount*, *elem1*, *elem2*, ...) : *start* 에서 시작해 *deleteCount* 만큼 제거한 후 지정된 요소를 삽입합니다. ## *start* 위치에 있는 요소를 *elem1*으로, 그 다음 요소를 *elem2*로, 이런 식으로 *deleteCount* 만큼 교체합니다. 이 메서드는 제거된 요소를 반환합니다.
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

  - unshift() : 지정된 요소를 배열 맨 앞에 추가하고 새 길이를 반환합니다.
  ```js
  > var arr = ['c', 'd'];
  > arr.unshift('a', 'b')
  //4
  > arr
  //['a', 'b', 'c', 'd']
  ```