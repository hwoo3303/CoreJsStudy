Q) 깊은 복사의 여러 방법을 구현하고 장단점을 기술해주세요.

A) 
1. 커스텀 재귀 함수
```javascript
let copyObjectDeep = (obj) => {
    let result = {};

    if(typeof obj === "object" && target !== null){
        for(let prop in obj){
            result[prop] = copyObjectDeep(target[prop]);
        }
    } else{
        result = target;
    }

    return result;
}
```

2. JSON객체의 함수 활용
```javascript
const obj1 = {
  a: 1,
  b: "string",
  c: {
    name: "Leon",
    age: "29"
  }
};

const obj2 = JSON.parse(JSON.stringify(obj1));
```

3. 라이브러리 사용
```javascript
const original = { a: { b: 2 } };
// cloneDeep 함수는 lodash 라이브러리에 구현된 함수
let copy = _.cloneDeep(original);
copy.a.b = 100;
console.log(original.a.b); //2 출력
```

[성능비교](http://jsben.ch/2KRm3)

![image](https://user-images.githubusercontent.com/15838144/168521653-7a3fc8fb-fe87-47e7-a82a-eb996dd100eb.png)

장단점
1. 커스텀 함수
    - 장점 : 타 방법 대비 뛰어난 성능
    - 단점 : 직접 구현해야되는 번거로움이 있음
2. JSON객체 함수
    - 장점 : 라이브러리 사용 없이 편리하게 사용 가능
    - 단점 : 객체의 키값이
4. 라이브러리 사용



