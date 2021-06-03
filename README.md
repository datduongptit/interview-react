# interview-react

###### 1. What's the output? Why?
```javascript
(function js(x) {
  const y = (j) => j * x;

  console.log(y(s()));

  function s() {
    return j();
  }

  function j() {
    return x ** x;
  }
})(3);
```
- A: `undefined`
- B: 18
- C: 81
- D: 12


###### 2. What's the output? Whay?
```javascript
const js = { language: "loosely type", label: "difficult" };

const edu = { ...js, level: "PhD" };

const newbie = edu;

delete edu.language;

console.log(Object.keys(newbie).length);
```
- A: 2;
- B: 3;
- C: 4;
- D: 5;

###### 3. What's the output?
```javascript
var candidate = {
  name: "Vuong",
  age: 30,
};

var job = {
  frontend: "Vuejs or Reactjs",
  backend: "PHP and Laravel",
  city: "Auckland",
};

class Combine {
  static get() {
    return Object.assign(candidate, job);
  }

  static count() {
    return Object.keys(this.get()).length;
  }
}

console.log(Combine.count());
```
- A: 5;
- B: 6;
- C: 7;
- D: 8;

###### 4. What's the output? Why?

```javascript
console.log("hello");

setTimeout(() => console.log("world"), 0);

console.log("hi");
```

- A: "hello" -> "world" -> "hi"
- B: "hello" -> "hi" -> "world"
- C: "hi" -> "world" -> "hello"
- D: "hi" -> "hello" -> "world"

###### 5. What's the output?

```javascript
const array = (a) => {
  let length = a.length;
  delete a[length - 1];
  return a.length;
};

console.log(array([1, 2, 3, 4]));

const object = (obj) => {
  let key = Object.keys(obj);
  let length = key.length;
  delete obj[key[length - 1]];

  return Object.keys(obj).length;
};

console.log(object({ 1: 2, 2: 3, 3: 4, 4: 5 }));

const setPropNull = (obj) => {
  let key = Object.keys(obj);
  let length = key.length;
  obj[key[length - 1]] = null;

  return Object.keys(obj).length;
};

console.log(setPropNull({ 1: 2, 2: 3, 3: 4, 4: 5 }));
```

- A: 333
- B: 444
- C: 434
- D: 343

###### 6. What's the output?

```javascript
let promise = new Promise((rs, rj) => {
  setTimeout(() => rs(4), 0);

  Promise.resolve(console.log(3));

  console.log(2);
});

promise
  .then((rs) => {
    console.log(rs ? rs ** rs : rs);
    return rs;
  })
  .then((rs) => console.log(rs == 256 ? rs : rs * rs));
```

- A: 3, 2, 256, 256
- B: 3, 2, 256, 16
- C: 256, 16, 3, 2
- D: 16, 256, 3, 2

###### 7. What's the output?

```javascript
async function f() {
  let promise = new Promise((resolve, reject) => {
    setTimeout(() => resolve("done!"), 0);
  });

  setTimeout(() => console.log("world"), 0);

  console.log(await promise);

  console.log("hello");
}

f(setTimeout(() => console.log("kiora"), 0));
```

- A: ReferenceError
- B: done, hello, world
- C: hello, done, world
- D: kiora, done, hello, world

###### 8. What's the output?

```javascript
const coderfarm = [1, 2, 3, 4, 5];

const [top, ...bottom] = (function (a) {
  let result = a;

  a.unshift(new Array(3));

  return result;
})(coderfarm);

console.log(top.length + bottom.length);
```

- A: 8
- B: 9
- C: 10
- D: 11

###### 9. What's the output?

```javascript
let age = { number: 10 };

const getAge = (flag) => {
  flag ? delete age.number : delete age;
  return age.number++;
};

console.log(getAge(false));

console.log(age.number);

console.log(getAge(true));

console.log(age.number);
```

- A: 10 - 10 - NaN - NaN
- B: 10 - 10 - undefined - undefined
- C: 10 - 11 - undefined - undefined
- D: 10 - 11 - NaN - NaN

###### 10. What's the output?

```javascript
const a = { name: "hoccoban.com" };
const b = { name: "youtube.com/hoccoban" };

const first = { ...a }.name.length;
const second = { ...a, ...b }.name.length;
const third = { ...a, ...b, name: "hello" }.name.length;

console.log(first + second + third);
```

- A: 12
- B: 37
- C: 5
- D: 20

###### 11. What's the output?

```javascript
const result = ["ronaldo", "messi", "neymar", "Ronaldo", "LuKaKUUUU"].sort();

console.log(result);
```

- A: ["LuKaKUUUU", "Ronaldo", "messi", "neymar", "ronaldo"]
- B: ["LuKaKUUUU", "messi", "neymar", "Ronaldo","ronaldo"]
- C: ["LuKaKUUUU", "messi", "neymar", "ronaldo", "Ronaldo"]
- D: ["messi", "neymar", "ronaldo", "Ronaldo", "LuKaKUUUU"]

###### 12. What's the output?

```javascript
const js = [9, 10];

function mutate(a, b){
    a.push(b);
}

mutate(js, 1);
console.log(js);

```

- A: [9, 10]
- B: [9, 10, 1]
- C: [1, 9, 10]
- D: ReferenceError 

###### 13. What's the output?

```javascript
let x = {};
let y = {};
let z = x;

console.log(x == y);
console.log(x === y);
console.log(x == z);
console.log(x === z);
```

- A: true true true true;
- B: false false false false;
- C: true true false false;
- D: false false true true;
