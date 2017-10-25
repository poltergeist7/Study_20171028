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
  - charAt(n)
  - charCodeAt(n)
  - concat()
  - indexOf(substr)
  - lastIndexOf(substr)
  - match(reg)
  - replace(reg,rep)
  - search(reg)
  - slice(srt)
  - split(str)
  - substr(start[,count])
  - toLowerCase()
  - toUpperCase()
  - trim()

 ```
 function () {}
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
  ```
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
  - concat()
  - indexOf()
  - join()
  - pop() : 배열에서 마지막 요소를 제거하고 그 요소를 반환합니다.
  ```
  > var arr = [ 'a', 'b' ];
  > arr.pop()
  //'b'
  > arr
  //[ 'a' ]
  ```
  - push() : 배열에 지정되 뇽소를 추가하고 새 길이를 반환합니다.
  ```
  > var arr = [ 'a', 'b' ];
  > arr push('c', 'd')
  //4
  > arr
  // [ 'a', 'b', 'c', 'd' ]
  ```
  - reverse()
  - shift() : 인덱스 0에 있는 요소를 제거하고 그 요소를 반환합니다. 이어지는 요소의 인덱스는 1씩 줄어듭니다.
  ```
  > var arr = [ 'a', 'b' ];
  > arr.shift()
  //'a'
  > arr
  //['b']
  ```
  - slice()
  ```
  > var arr= [ 'a', 'b', 'c' ];
  ```
  - sort()
  - splice( *start*, *deleteCount*, *elem1*, *elem2*, ...) : *start* 에서 시작해 *deleteCount* 만큼 제거한 후 지정된 요소를 삽입합니다. ## *start* 위치에 있는 요소를 elem1으로, 그 다음 요소를 elem2로, 이런 식으로 deleteCount 만큼 교체합니다. 이 메서드는 제거된 요소를 반환합니다.
  ```
  > var arr = [ 'a', 'b', 'c', 'd'];
  > arr.splice(1, 2, 'x');
  //[ 'b', 'c' ]
  > arr
  //[ 'a', 'x', 'd']
  ```
  - unshift() : 지정된 요소를 배열 맨 앞에 추가하고 새 길이를 반환합니다.
  ```
  > var arr = ['c', 'd'];
  > arr.unshift('a', 'b')
  //4
  > arr
  //['a', 'b', 'c', 'd']
  ```