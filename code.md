# testStudy 코딩테스트 풀고, 정리하기
### 프로그래머스_하샤드 수 2022_03_20
* 문제
```
양의 정수 x가 하샤드 수이려면 x의 자릿수의 합으로 x가 나누어져야 합니다. 
예를 들어 18의 자릿수 합은 1+8=9이고, 18은 9로 나누어 떨어지므로 18은 하샤드 수입니다. 
자연수 x를 입력받아 x가 하샤드 수인지 아닌지 검사하는 함수, solution을 완성해주세요.
```
* 작성한 코드
```
function solution(x) {
    let getNum = x.toString().split('');
    let result = 0;
    
    for (let i = 0; i < getNum.length; i++){
        result += Number(getNum[i]);
    }
    
    if(x % result === 0) {
        return true;
    } else {
        return false;
    }
}
```
주어진 수를 문자열로 만든 후, split 메소드를 사용하면 각 자리수가 배열로 반환됩니다. <br>
해왔던 것처럼 result에 getNum 배열의 값들을 더해줍니다. <br>
주어진 수를 result로 나누었을 때 몫이 0이면 하샤드 수가 되니, if문 조건으로 만들어줍니다. <br>
``` 
조건문을 아래와 같이 삼항 조건 연산자로 작성해주면 더 깔끔한 코드가 될 것 같습니다.
return x % result === 0 ? true : false;
```

---


### 프로그래머스_평균 구하기 2022_03_20
* 문제
```
정수를 담고 있는 배열 arr의 평균값을 return하는 함수, solution을 완성해보세요.
```
* 작성한 코드
```
function solution(arr) {
    let result = 0;
    for (let i = 0; i < arr.length; i++){
        result += arr[i]
    }
    return result / arr.length;
}
```

반복문에서 수를 더하기 위해 result를 0으로 선언함 ``` let result = 0; ``` <br>
더해진 값들을 arr 갯수로 나누어 평균값을 만들어주는 것이 중요함 ``` result / arr.length ```

---

### 프로그래머스_핸드폰 번호 가리기 2022_03_18
* 문제
```
모바일은 개인정보 보호를 위해 고지서를 보낼 때 고객들의 전화번호의 일부를 가립니다.
전화번호가 문자열 phone_number로 주어졌을 때, 전화번호의 뒷 4자리를 제외한 나머지 숫자를 전부 *으로 가린 문자열을 리턴하는 함수, solution을 완성해주세요.
```
* 작성한 코드
```
function solution(phone_number) {
    if(phone_number.length > 0) {
        let getLastNum = phone_number.substr(-4, 4);
        let star = '*'.repeat(phone_number.length -4 );
        let answer = star + getLastNum;
        return answer;
    }
}
```
내가 작성한 코드는 주어진 핸드폰 번호에서 뒷번호 4개를 가져온 후, 나머지 부분은 * 를 만들어주어 붙여주었다. <br>
너무 1차원적으로 작성한 코드라고 생각이 들어서 다른 분들의 코드를 본 후, 공부할만한 정도의 답변을 가져와봄 ( _ , JoonSukCho님)
``` 
function solution(phone_number) {
   let result = []

   for(let i = 0; i < phone_number.length; i++){
      if(i < phone_number.length-4){
          result.push('*')
      } else {
          result.push(phone_number[i])
      }
   }
   return result.join('')
}
```
result라는 빈 array를 만든 후, for문과 if문을 이용하여 result에 push 해주었음. <br> (만약 11자리의 번호가 들어왔다면 인덱스 0 ~ 6의 숫자들은 첫 번째 조건을 만족하여 * 로 들어가고, 인덱스 7 ~ 10의 숫자들은 조건을 만족하지 못하여 핸드폰 번호가 array에 차례로 push된다.

이후에 완성된 result를 join을 사용하여 하나의 값으로 만들어주면 된다. <br>
``` 
join() : Array.join()은 배열의 원소들을 연결하여 하나의 값으로 만듭니다.
출처 : https://www.codingfactory.net/10450
```

---

### 프로그래머스_x만큼 간격이 있는 n개의 숫자 2022_03_10
* 문제
```
함수 solution은 정수 x와 자연수 n을 입력 받아, x부터 시작해 x씩 증가하는 숫자를 n개 지니는 리스트를 리턴해야 합니다. 
다음 제한 조건을 보고, 조건을 만족하는 함수, solution을 완성해주세요.
```
* 작성한 코드
```
function solution(x, n) {
    var answer = [];
    let result = 0;
    let Num = x;
    for(let i = 0; i < n; i++){
        result += Num
        answer.push(result)
    }
    return answer;
}
```
처음에 ``` let result = "" ``` 으로 작성하여서 숫자가 더해지지 않고, 밑에 별찍기 문제처럼 "22" "222" 이런식의 결과가 나왔음
그래서 문자열을 숫자로 바꾸어주는 Number() 함수 이용하여 문제 풀려했는데 해결 못하였음 

``` let result = 0; ```으로 하니 함수가 필요없어짐 


---

### 프로그래머스_직사각형 별찍기 2022_03_10

* 문제
``` 
이 문제에는 표준 입력으로 두 개의 정수 n과 m이 주어집니다.
별(*) 문자를 이용해 가로의 길이가 n, 세로의 길이가 m인 직사각형 형태를 출력해보세요.
```
* 작성한 코드
```process.stdin.setEncoding('utf8');
process.stdin.on('data', data => {
    const n = data.split(" ");
    const a = Number(n[0]), b = Number(n[1]);
    var x = ""
    var y = "*"
        for(let j = 0; j<a; j++){
            x += y;
        }
        for(let i = 0; i<b; i++){
            console.log(x);
        }
});
```
사실 줄바꿈 \n 을 사용하고 싶었으나, ''을 넣어야 한다는 생각을 못함. 그래서 그냥 단순하게 반복문 for을 두 번 사용함

``` result += '\n'``` 다음부턴 이런 방식으로 사용하기

다른 분들의 풀이를 보니 repeat 메소드가 사용이 되었고, 검색해보니 "문자열을 주어진 횟수만큼 반복해 붙인 새로운 문자열을 반환합니다." 라고 한다. (아래와 같이 사용된다고 한다.  ```따라서 '*'.repeat(5)를 해주면 *****가 되는 것임```
```
'abc'.repeat(1);    // 'abc'
'abc'.repeat(2);    // 'abcabc'
```
