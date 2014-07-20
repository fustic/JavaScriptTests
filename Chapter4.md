## Глава 4. Функции, замыкания, аргументы
### Тема 1. Объявление функции
1. В каких из нижеперечисленных примеров кода не будет ошибки?
  ```javascript
  1. mail();
     function mail() {}
  ```
  ```javascript
  2. mail();
     var mail = function() {};
  ```
  ```javascript
  3. var mail = function mymail() {
       mymail();
     };
  ```
  ```javascript
  4. var mail = function mymail() {
       mymail();
     };
     mymail();
  ```
  ```javascript
  5. function mail() {}
     var mymail = mail;
     mail = null;
     mymail();
  ```
  
  *Правильные ответы:* **1, 3, 5**

2. В каких из нижеперечисленных примеров кода будет ошибка?
  ```javascript
  1. function mail() {}
     var mymail = mail;
     mail = null;
     mymail();
     mail();
  ```
  ```javascript
  2. (function () {})()
  ```
  ```javascript
  3. (function () {}())
  ```
  ```javascript
  4. function () {}()
  ```
  ```javascript
  5. var mail = function mymail() {
       mymail();
     };
     mymail();
  ```
  
  *Правильные ответы:* **1, 4, 5**
  
3. В каких из нижеперечисленных примеров кода не будет ошибки?
  ```javascript
  1. (function () {}())
  ```
  ```javascript
  2. +function () {}()
  ```
  ```javascript
  3. function () {}()
  ```
  ```javascript
  4. var mail = function () {}();
  ```
  ```javascript
  5. mail();
     var mail = function() {};
  ```
  
  *Правильные ответы:* **1, 2, 4**
  
4. В каких из нижеперечисленных примеров кода не будет ошибки?
  ```javascript
  1. !function () {}()
  ```
  ```javascript
  2. mymail;
     mymail();
     var mymail = function () {};
  ```
  ```javascript
  3. var mymail = function () {};
     mymail();
  ```
  ```javascript
  4. function () {}()
  ```
  ```javascript
  5. (function () {}())
  ```
  
  *Правильные ответы:* **1, 3, 5**
  
5. В каких из нижеперечисленных примеров кода не будет ошибки?
  ```javascript
  1. ~function () {}()
  ```
  ```javascript
  2. mymail();
     var mymail = function () {};
  ```
  ```javascript
  3. mymail();
     (function () {
       var mymail = function () {}; 
     })();
  ```
  ```javascript
  4. mymail();
     (function mymail() {})();
  ```
  ```javascript
  5. var mymail = function mymail() {}();
  ```
  
  *Правильные ответы:* **1, 5**

### Тема 2. Объявление переменных
1. Что будет в консоли browser?
  ```javascript
  var
    a = 4,
    b = 3;
  if (false) {
     var c = a - b;
  }
  console.log(c);  
  ```
  1. 1
  2. 0 
  3. NaN
  4. undefined
  5. ReferenceError
  
  *Правильные ответы:* **4**

2. Что будет в консоли browser?
  ```javascript
  a = 4;
  var
    b = 3;
  if (false) {
     var c = a - b;
  }
  console.log(c);  
  ```
  1. 1
  2. 0 
  3. NaN
  4. undefined
  5. ReferenceError
  
  *Правильные ответы:* **4**

3. Что будет в консоли browser?
  ```javascript
  var
    a = 4,
    b = a - 1;
  if (false) {
     var c = a * b;
  }
  console.log(c);  
  ```
  1. 12
  2. 0 
  3. NaN
  4. undefined
  5. ReferenceError
  
  *Правильные ответы:* **4**

4. Что будет в консоли browser?
  ```javascript
  var
    a = 4,
    b = a + 1;
  if (false) {
     var c = a / b;
  }
  console.log(c);  
  ```
  1. 4/5
  2. 0 
  3. NaN
  4. undefined
  5. ReferenceError
  
  *Правильные ответы:* **4**

5. Что будет в консоли browser?
  ```javascript
  a = 0;
  var
    b = a + 1;
  if (false) {
     var c = b / a;
  }
  console.log(c);  
  ```
  1. Infinity
  2. 0
  3. NaN
  4. undefined
  5. ReferenceError
  
  *Правильные ответы:* **4**

### Тема 3. Область видимости переменных
1.