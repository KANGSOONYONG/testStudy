# testStudy 코딩테스트 풀고, 정리하기
### 프로그래머스_x만큼 간격이 있는 n개의 숫자 2022_03_10
문제
```
함수 solution은 정수 x와 자연수 n을 입력 받아, x부터 시작해 x씩 증가하는 숫자를 n개 지니는 리스트를 리턴해야 합니다. 
다음 제한 조건을 보고, 조건을 만족하는 함수, solution을 완성해주세요.
```
작성한 코드
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

문제
``` 
이 문제에는 표준 입력으로 두 개의 정수 n과 m이 주어집니다.
별(*) 문자를 이용해 가로의 길이가 n, 세로의 길이가 m인 직사각형 형태를 출력해보세요.
```
작성한 코드
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
