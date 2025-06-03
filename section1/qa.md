## 고차함수 작동 원리

### forEach
```js
function forEach(predicate, thisArg){ //predicate == 콜백함수수
    for(let i=0; i<a.length; i++){
        predicate(a[i], i);
    }
}

a.forEach((value, index) => {
    console.log(this); // this == [1,2]
}, [1,2]);
```

### map 
```js
function map(predicate, thisArg){
    let list = [];
    for(let i=0; i<a.length; i++){
        list.push(predicate(a[1], i));
    }

    return list;
}

const map1 = array1.map((x) => x * 2);

let map2 = a.map((value,index) =>> {
    return value*value;
});

let map3 = a.map((value,index) =>> {
    if(v%2 == 0) return v;
}); // 원본 배열과 똑같은 길이의 배열이 추출된다. 즉 return 못받은 원소는 undefined가 된다. 
```


### filter
```js
function map(predicate, thisArg){
    let list = [];
    for(let i=0; i<a.length; i++){
        if(predicate(a[i], i)) list.push(a[1]);
    }

    return list;
}

let newMap = a.filter((value,index) =>> {
    if(v%2 == 0) return v;
}); // 새로운 배열 추출
```


### reduce
```js
function reduce(predicate, val){ // val => 초기값
    let result = val;
    for(let i=0; i<a.length; i++){
        result = predicate(result, a[i]);
    }
    return result;
}

answer = a.reduce((acc, v) => {
    return acc+v;
}, 0); // 0 => 초기값 세팅
```