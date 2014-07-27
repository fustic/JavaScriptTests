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
  alert(c);  
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
  alert(c);  
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
  alert(c);  
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
  alert(c);  
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
  alert(c);  
  ```
  1. Infinity
  2. 0
  3. NaN
  4. undefined
  5. ReferenceError
  
  *Правильные ответы:* **4**

### Тема 3. Область видимости переменных
1. Результатом выполнения следующего кода будет
  ```javascript
  var foo = 5;
  function bar() {
    var a = f = 5;
  }
  bar();
  alert(foo + a);
  ```
  1. 10
  2. ReferenceError
  3. NaN
  4. undefined
  5. 5
  
  *Правильные ответы:* **2**
    
2. Результатом выполнения следующего кода будет
  ```javascript
  var foo = 5;
  function bar() {
    var a = f = 5;
  }
  bar();
  alert(foo + f);
  ```
  1. 10
  2. ReferenceError
  3. NaN
  4. undefined
  5. 5
  
  *Правильные ответы:* **1**
  
3. Результатом выполнения следующего кода будет
  ```javascript
  var foo = 5;
  function bar() {
    var a = f = 5;
  }
  alert(foo + f);
  ```
  1. 10
  2. ReferenceError
  3. NaN
  4. undefined
  5. 5
  
  *Правильные ответы:* **2**

4. Результатом выполнения следующего кода будет
  ```javascript
  var foo = 5;
  function bar() {
    var a = f = 5;
  }
  alert(foo + bar());
  ```
  1. 10
  2. ReferenceError
  3. NaN
  4. undefined
  5. 5
  
  *Правильные ответы:* **3**

5. Результатом выполнения следующего кода будет
  ```javascript
  var foo = 5;
  function bar() {
    var a = f = 5;
    return f = 10;
  }
  alert(foo + bar());
  ```
  1. 15
  2. ReferenceError
  3. NaN
  4. undefined
  5. 5
  
  *Правильные ответы:* **1**
  
### Тема 4. Область видимости, статические переменные.
1. Результатом выполнения следующего кода будет
  ```javascript
  var mailFunction = (function () {
    var mailUsers = 0;
    return function () {
      return ++mailUsers;
    };
  }());
  alert(mailFunction());
  alert(mailFunction());
  ```
  1. 0
     0
  2. 0
     1
  3. 1
     2
  4. undefined is not a function
  5. 1
     1
  
  *Правильные ответы:* **3**

2. Результатом выполнения следующего кода будет
  ```javascript
  var mailFunction = (function () {
    var mailUsers = 0;
    return function () {
      return ++mailUsers;
    };
  }());
  alert(mailFunction());
  mailFunction.mailUsers = 5;
  alert(mailFunction());
  ```
  1. 1
     6
  2. 0
     1
  3. 1
     2
  4. undefined is not a function
  5. ReferenceError
  
  *Правильные ответы:* **3**

3. Результатом выполнения следующего кода будет
  ```javascript
  var
    mailFunction = (function () {
     var mailUsers = 0;
     return function () {
       return ++mailUsers;
     };
    }()),
    mainAnotherFunction = mailFunction;
  alert(mailFunction());
  alert(mainAnotherFunction());
  ```
  1. 1
     1
  2. 0
     0
  3. 1
     2
  4. undefined is not a function
  5. ReferenceError
  
  *Правильные ответы:* **3**

4. Результатом выполнения следующего кода будет
  ```javascript
  var
    mailFunction = (function () {
     var mailUsers = 0;
     return function () {
       return ++mailUsers;
     };
    }()),
    mainAnotherFunction = mailFunction;
  alert(mailFunction());
  mailFunction.mailUsers = 4;
  alert(mainAnotherFunction());
  ```
  1. 1
     1
  2. 1
     5
  3. 1
     2
  4. undefined is not a function
  5. ReferenceError
  
  *Правильные ответы:* **3**

5. Результатом выполнения следующего кода будет
  ```javascript
  var
    mailFunction = (function () {
     var mailUsers = 0;
     return function () {
       return ++mailUsers;
     };
    }()),
    mainAnotherFunction = mailFunction;
  alert(mailFunction());
  mailFunction.mailUsers = 4;
  alert(+mainAnotherFunction());
  ```
  1. 1
     1
  2. 1
     5
  3. 1
     2
  4. undefined is not a function
  5. ReferenceError
  
  *Правильные ответы:* **3**

### Тема 5. Замыкания
1. Какой из приведенных кусков кода выведет в консоль поочередно 0 и 1 через 1 сек. ?
  1.
  ```javascript
   for (var i = 0; i < 2; i++) {
     setTimeout(function() { alert(i); }, 1000);
   }
   ```
  2.
  ```javascript
   for (var i = 0; i < 2; i++) {
     setTimeout((function(e) { alert(e); })(i), 1000);
   }
   ```
  3.
  ```javascript
   for (var i = 0; i < 2; i++) {
     (function(e) {
       setTimeout(function() {
         alert(e)
       }, 1000);
     })(i);
   }
   ```
  4.
  ```javascript
   for (var i = 0; i < 2; i++) {
     setTimeout(function(k) {
       alert(k)
     }.bind(this, i), 1000);
   }
   ```
  5.
  ```javascript
   for (var i = 0; i < 2; i++) {
     (function(e) {
       setTimeout(function(k) {
          alert(k);
       }.bind(this, e), 1000);
     }(i));
   }
   ```
  *Правильные ответы:* **3, 4, 5**
  
2. Какой из приведенных кусков кода выведет в консоль поочередно 0 и 1 сразу после окончания выполнения цикла?
  1.
  ```javascript
   for (var i = 0; i < 2; i++) {
     setTimeout(function() { alert(i); }, 1000);
   }
   ```
  2.
  ```javascript
   for (var i = 0; i < 2; i++) {
     setTimeout((function(e) { alert(e); })(i), 1000);
   }
   ```
  3.
  ```javascript
   for (var i = 0; i < 2; i++) {
     (function(e) {
       setTimeout(+function() {
         alert(e)
       }(), 1000);
     })(i);
   }
   ```
  4.
  ```javascript
   for (var i = 0; i < 2; i++) {
     setTimeout(function(k) {
       alert(k)
     }.bind(this, i), 1000);
   }
   ```
  5.
  ```javascript
   for (var i = 0; i < 2; i++) {
     (function(e) {
       setTimeout(function(k) {
          alert(k);
       }.bind(this, e), 1000);
     }(i));
   }
   ```
  *Правильные ответы:* **2, 3**
  
3. Какой из приведенных кусков кода выведет в консоль поочередно 1, 2 и 3 через 1 сек. ?
  1.
  ```javascript
   for (var i = 1; i <= 3; i++) {
     setTimeout(function() { alert(i); }, 1000);
   }
   ```
  2.
  ```javascript
   for (var i = 1; i <= 3; i++) {
     setTimeout(function(k) {
       alert(k)
     }.bind(this, i), 1000);
   }
   ```
  3.
  ```javascript
   for (var i = 1; i <= 3; i++) {
     setTimeout((function(e) { alert(e); })(i), 1000);
   }
   ```
  4.
  ```javascript
   for (var i = 1; i <= 3; i++) {
     (function(e) {
       setTimeout(function() {
         alert(e)
       }, 1000);
     })(i);
   }
   ```
  5.
  ```javascript
   for (var i = 1; i <= 3; i++) {
     (function(e) {
       setTimeout(function(k) {
          alert(k);
       }.bind(this, e), 1000);
     }(i));
   }
   ```
  *Правильные ответы:* **2, 4, 5**
  
4. Какой из приведенных кусков кода выведет в консоль поочередно 1, 2, 3 сразу после окончания выполнения цикла?
  1.
  ```javascript
   for (var i = 1; i <= 3; i++) {
     setTimeout(function() { alert(i); }, 1000);
   }
   ```
  2.
  ```javascript
   for (var i = 1; i <= 3; i++) {
     setTimeout((function(e) { alert(e); })(i), 1000);
   }
   ```
  3.
  ```javascript
   for (var i = 1; i <= 3; i++) {
     (function(e) {
       setTimeout(+function() {
         alert(e)
       }(), 1000);
     })(i);
   }
   ```
  4.
  ```javascript
   for (var i = 1; i <= 3; i++) {
     setTimeout(function(k) {
       alert(k)
     }.bind(this, i), 1000);
   }
   ```
  5.
  ```javascript
   for (var i = 1; i <= 3; i++) {
     (function(e) {
       setTimeout(function(k) {
          alert(k);
       }.bind(this, e), 1000);
     }(i));
   }
   ```
  *Правильные ответы:* **2, 3**

5. Какой из приведенных кусков кода выведет в консоль поочередно 1, 2 и 3 через 1 сек. ?
  1.
  ```javascript
   for (var i = 1; i <= 3; i++) {
     setTimeout(function() { alert(i); }, 1000);
   }
   ```
  2.
  ```javascript
   for (var i = 1; i <= 3; i++) {
     setTimeout(function(k) {
       alert(k)
     }.bind(this, i), 1000);
   }
   ```
  3.
  ```javascript
   for (var i = 1; i <= 3; i++) {
     setTimeout((function(e) { alert(e); })(i), 1000);
   }
   ```
  4.
  ```javascript
   for (var i = 1; i <= 3; i++) {
     (function(e) {
       setTimeout(function() {
         alert(e)
       }, 1000);
     })(i);
   }
   ```
  5.
  ```javascript
   for (var i = 1; i <= 3; i++) {
     (function(e) {
       setTimeout(function(k) {
          alert(k);
       }.call(this, e), 1000);
     }(i));
   }
   ```
  *Правильные ответы:* **2, 4**
  
### Тема 6. Контекст
1. Что будет результатом выполнения кода
  ```javascript
  var
    mail = {
      title: 'mailRu',
      tostr: function(title){
        alert(this.title + ' ' + title);
      }
    },
    f = mail.tostr.bind(mail, 'group');
  f();
  ```
  1. undefined group
  2. mailRu group
  3. group undefined
  4. TypeError: undefined is not a function
  5. mailRu group
     TypeError: undefined is not a function
  
  *Правильные ответы:* **2**

2. Что будет результатом выполнения кода
  ```javascript
  var
    mail = {
      title: 'mailRu',
      tostr: function(title){
        alert(this.title + ' ' + title);
      }
    },
    f = mail.tostr.bind(this, 'group');
  f();
  ```
  1. undefined group
  2. mailRu group
  3. group undefined
  4.  group
  5. mailRu group
     TypeError: undefined is not a function
  
  *Правильные ответы:* **1**
  
3. Что будет результатом выполнения кода
  ```javascript
  var
    mail = {
      title: 'mailRu',
      tostr: function(title){
        alert(this.title + ' ' + title);
      }
    },
    f = mail.tostr.call(this, 'group');
  f();
  ```
  1. undefined group
  2. mailRu group
  3. group undefined
  4. group
  5. group
     TypeError: undefined is not a function
  
  *Правильные ответы:* **1**  

4. Что будет результатом выполнения кода
  ```javascript
  var
    mail = {
      title: 'mailRu',
      tostr: function(title){
        alert(this.title + ' ' + title);
      }
    },
    f = mail.tostr.call(mail, 'group');
  f();
  ```
  1. undefined group
  2. mailRu group
  3. group undefined
  4.  group
  5. mailRu group
     TypeError: undefined is not a function
  
  *Правильные ответы:* **2**
    
5. Что будет результатом выполнения кода
  ```javascript
  var
    mail = {
      title: 'mailRu',
      tostr: function(title){
        alert(this.title + ' ' + title);
      }
    },
    f = mail.tostr.bind(mail, 'group');
  f.apply(this);
  ```
  1. undefined group
  2. mailRu group
  3. group undefined
  4.  group
  5. mailRu group
     TypeError: undefined is not a function
  
  *Правильные ответы:* **2**  