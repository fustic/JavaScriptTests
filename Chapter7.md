## Глава 7. Работа с данными на клиенте
### Тема 1. Cookies
1. Отметьте верные утверждения
  ```javascript
  var date = new Date( new Date().getTime() + 60 * 1000 );
  document.cookie="myCookie=myValue; path=/; expires="+date.toUTCString();"
  ```
  1. `document.cookie` будут перезаписаны новым значением
  2. будет добавлена новая `cookie` с ключом `myCookie` и значением `myValue`
  3. `cookie` будет установлена на 1 минуту
  4. размер `cookie` ограничен 2 Кбайт
  5. `cookie` будет выставлена на текущий домен 
  
  *Правильные ответы:* **2, 3, 5**

2. Отметьте верные утверждения
  ```javascript
  document.cookie="myCookie=myValue; path=/;"
  ```
  1. `document.cookie` будет дополнена новым значением
  2. будет добавлена новая `cookie` с ключом `myCookie` и значением `myValue`
  3. `cookie` будет установлена на сессию
  4. размер `cookie` ограничен 1 Кбайт
  5. `cookie` не отправляется на сервер при AJAX запросах 
  
  *Правильные ответы:* **1, 2, 3**
  
3. Отметьте верные утверждения
  ```javascript
  document.cookie="myCookie=myValue; path=/; secure=true"
  ```
  1. `document.cookie` будет дополнена новым значением
  2. будет добавлена новая `cookie` с ключом `myCookie` и значением `myValue`
  3. `cookie` будет установлена бессрочно
  4. размер `cookie` ограничен 2 Кбайт
  5. эта `cookie` будет пересылаться только по защищенному каналу  
  
  *Правильные ответы:* **1, 2, 5**
  
4. Отметьте верные утверждения
  ```javascript
  var date = new Date( new Date().getTime() + 60 * 1000 );
  document.cookie="myCookie=myValue; path=/cookie; expires="+date.toUTCString();"
  ```
  1. `document.cookie` будут перезаписаны новым значением
  2. будет добавлена новая `cookie` с ключом `myCookie` и значением `myValue` со сроком действия 60 сек
  3. `cookie` будет выставлена для данного домена и пути /cookie и все что внутри
  4. размер `cookie` ограничен 4 Кбайт
  5. все `cookie` отправляются на сервер только в POST-запросах  
  
  *Правильные ответы:* **2, 3, 4**
  
5. Отметьте верные утверждения
  ```javascript
  var date = new Date( new Date().getTime() + 60 * 1000 );
  document.cookie="myCookie=myValue; path=/cookie; expires="+date.toUTCString(); secure=true;"
  ```
  1. все `cookie` доступны из `JavaScript`
  2. будет добавлена новая `cookie` с ключом `myCookie` и значением `myValue` со сроком действия 60 сек
  3. `cookie` будет выставлена для данного домена и пути /cookie и все что внутри и будет передаваться только по защищенному каналу
  4. размер `cookie` ограничен 4 Кбайт
  5. все `cookie` отправляются на сервер с абсолютно каждым запросом  
  
  *Правильные ответы:* **2, 3, 4, 5**
  
### Тема 2. LocalStorage
1. Какие из утверждений верны
  ```javascript
  localStorage.setItem('title', 'mail.ru');
  ```
  1. Данные установленные в документе с URL `http://mail.ru` будут также доступны в документе с URL `https://mail.ru`
  2. Срок хранения данных не ограничен
  3. `localStorage.getItem('title') === localStorage.title`
  4. После выполнения `setItem` будет сгенерировано событие `storage` во всех вкладках, у которых документ имеет тоже происхождение
  5. `localStorage.removeItem('title')` удалит эту пару ключ-значение

  *Правильные ответы:* **2, 3, 5**
  
2. Какие из утверждений верны
  ```javascript
  localStorage.setItem('title', 'mail.ru');
  ```
  1. Данные установленные в документе с URL `http://mail.ru` не будут также доступны в документе с URL `https://mail.ru`, т.к. документы имеют разное происхождение
  2. Срок хранения данных ограничен 24 часами
  3. `localStorage.getItem('title') === localStorage['title']`
  4. После выполнения `setItem` будет сгенерировано событие `storage` во всех вкладках, у которых документ имеет тоже происхождение, кроме текущей
  5. `localStorage.removeItem()` удалит абсолютно все пары ключ-значение этого домена

  *Правильные ответы:* **1, 3, 4**
  
3. Какие из утверждений верны
  ```javascript
  localStorage.setItem('title', 'mail.ru');
  ```
  1. Данные установленные в документе с URL `http://mail.ru` будут также доступны в документе с URL `http://www.mail.ru`
  2. Срок хранения данных ограничен текущей сессией
  3. В качестве значения можно устанавливать только строки
  4. После выполнения `setItem` будет сгенерировано событие `storage` во всех вкладках, у которых документ имеет тоже происхождение
  5. `localStorage.clear()` удалит абсолютно все пары ключ-значение этого домена

  *Правильные ответы:* **3, 5**

  
4. Какие из утверждений верны
  ```javascript
  localStorage.setItem('title', {title: 'mail.ru'});
  ```
  1. Данные установленные в документе с URL `http://mail.ru` не будут также доступны в документе с URL `http://www.mail.ru`, т.к. документы имеют разное происхождение
  2. Срок хранения данных ограничен текущей сессией
  3. `localStorage.getItem('title') === '[object Object]'` 
  4. После выполнения `setItem` будет сгенерировано событие `storage` во всех вкладках, у которых документ имеет тоже происхождение, кроме текущей
  5. `localStorage.removeItem()` удалит абсолютно все пары ключ-значение этого домена

  *Правильные ответы:* **1, 3, 4**

5. Какие из утверждений верны
  ```javascript
  var mail = {title: 'mail.ru'};
  localStorage.setItem('mail', mail);
  ```
  1. Данные установленные в документе с URL `http://mail.ru` будут также доступны в документе с URL `http://afisha.mail.ru`
  2. Срок хранения данных не ограничен
  3. `localStorage.getItem('mail').title === mail.title` 
  4. После выполнения `setItem` будет сгенерировано событие `storage` во всех вкладках, у которых документ имеет тоже происхождение, кроме текущей
  5. `localStorage.removeItem('mail')` удалит эту пару ключ-значение

  *Правильные ответы:* **2, 4, 5**

### Тема 3. SessionStorage
1. Какие из утверждений верны
  ```javascript
  sessionStorage.setItem('title', 'mail.ru');
  ```
  1. Данные установленные в документе с URL `http://mail.ru` будут также доступны в документе с URL `https://mail.ru`
  2. Срок хранения данных не ограничен
  3. `sessionStorage.getItem('title') === sessionStorage.title`
  4. После выполнения `setItem` будет сгенерировано событие `storage` во всех вкладках, у которых документ имеет тоже происхождение
  5. `sessionStorage.removeItem('title')` удалит эту пару ключ-значение

  *Правильные ответы:* **3, 5**
  
2. Какие из утверждений верны
  ```javascript
  sessionStorage.setItem('title', 'mail.ru');
  ```
  1. Данные установленные в документе с URL `http://mail.ru` не будут также доступны в документе с URL `https://mail.ru`, т.к. документы имеют разное происхождение
  2. Срок хранения данных ограничен 24 часами
  3. `sessionStorage.getItem('title') === sessionStorage['title']`
  4. После выполнения `setItem` будет сгенерировано событие `storage` во всех вкладках, у которых документ имеет тоже происхождение, кроме текущей
  5. `sessionStorage.removeItem()` удалит абсолютно все пары ключ-значение этого домена

  *Правильные ответы:* **1, 3**
  
3. Какие из утверждений верны
  ```javascript
  sessionStorage.setItem('title', 'mail.ru');
  ```
  1. Данные установленные в документе с URL `http://mail.ru` будут также доступны в документе с URL `http://www.mail.ru`
  2. Срок хранения данных ограничен текущей сессией
  3. В качестве значения можно устанавливать только строки
  4. После выполнения `setItem` будет сгенерировано событие `storage` во всех вкладках, у которых документ имеет тоже происхождение
  5. `sessionStorage.clear()` удалит абсолютно все пары ключ-значение этого домена

  *Правильные ответы:* **2, 3, 5**

  
4. Какие из утверждений верны
  ```javascript
  sessionStorage.setItem('title', {title: 'mail.ru'});
  ```
  1. Данные установленные в документе с URL `http://mail.ru` не будут также доступны в документе с URL `http://www.mail.ru`, т.к. документы имеют разное происхождение
  2. Срок хранения данных ограничен текущей сессией
  3. `sessionStorage.getItem('title') === '[object Object]'` 
  4. После выполнения `setItem` будет сгенерировано событие `storage` во всех вкладках, у которых документ имеет тоже происхождение, кроме текущей
  5. `sessionStorage.removeItem()` удалит абсолютно все пары ключ-значение этого домена

  *Правильные ответы:* **1, 2, 3**

5. Какие из утверждений верны
  ```javascript
  var mail = {title: 'mail.ru'};
  sessionStorage.setItem('mail', mail);
  ```
  1. Данные установленные в документе с URL `http://mail.ru` будут также доступны в документе с URL `http://afisha.mail.ru`
  2. Срок хранения данных не ограничен
  3. `sessionStorage.getItem('mail').title === mail.title` 
  4. После выполнения `setItem` будет сгенерировано событие `storage` только при наличии нескольких фреймов
  5. `sessionStorage.removeItem('mail')` удалит эту пару ключ-значение

  *Правильные ответы:* **4, 5**

### Тема 4. IndexedDB
1. У вас есть код
  ```javascript
  var
    db,
    dbRequest = indexedDB.open('mail.ru', 1),
    person1 = {
      name: 'user one',
      email: 'user1@email.com',
      age: 17,
      created: new Date()
    },
    person2 = {
      name: 'user two',
      email: 'user2@email.com',
      age: 35,
      created: new Date()
    },
    person3 = {
      name: 'user three',
      email: 'user3@email.com',
      age: 42,
      created: new Date()
    };

  dbRequest.onupgradeneeded = function (e) {
    db = dbRequest.result;
    var
      usersStore = db.createObjectStore('users', { keyPath: 'id', autoIncrement: true });

    usersStore.createIndex('name', 'name', {unique: false});
    usersStore.createIndex('email', 'email', {unique: true});
  };

  dbRequest.onsuccess = function () {
    db = dbRequest.result;
    var
      transaction = db.transaction(['users'], 'readwrite'),
      store = transaction.objectStore('users');
    store.put(person1);
    store.add(person2);
    store.add(person3);
    
  };
  ```
  Что будет в результате выполнения?
  ```javascript
  var object = db.transaction(['users'], 'readonly').objectStore('users').get(2);
  object.onsuccess = function (e) {
    var result = e.target.result;
    //...
  };
  ```
  
  1. `result.length > 1`
  2. `result.name === person2.name`
  3. `result.name === person3.name`
  4. `result.id === 2`
  5. `result.id === undefined`
      
  *Правильные ответы:* **2, 4**

2. У вас есть код
  ```javascript
  var
    db,
    dbRequest = indexedDB.open('mail.ru', 1),
    person1 = {
      name: 'user one',
      email: 'user1@email.com',
      age: 17,
      created: new Date()
    },
    person2 = {
      name: 'user two',
      email: 'user2@email.com',
      age: 35,
      created: new Date()
    },
    person3 = {
      name: 'user three',
      email: 'user3@email.com',
      age: 42,
      created: new Date()
    };

  dbRequest.onupgradeneeded = function (e) {
    db = dbRequest.result;
    var
      usersStore = db.createObjectStore('users', { keyPath: 'id', autoIncrement: true });

    usersStore.createIndex('name', 'name', {unique: false});
    usersStore.createIndex('email', 'email', {unique: true});
  };

  dbRequest.onsuccess = function () {
    db = dbRequest.result;
    var
      transaction = db.transaction(['users'], 'readwrite'),
      store = transaction.objectStore('users');
    store.put(person1);
    store.add(person2);
    store.add(person3);
    
  };
  ```
  Что будет в результате выполнения?
  ```javascript
  var object = db.transaction(['users'], 'readwrite').objectStore('users').get(2);
  object.onsuccess = function (e) {
    var result = e.target.result;
    //...
  };
  ```
  
  1. `result.length > 1`
  2. `result.name === person2.name`
  3. `result.name === person3.name`
  4. `result.id === 2`
  5. `result.id === undefined`
      
  *Правильные ответы:* **2, 4**

3. У вас есть код
  ```javascript
  var
    db,
    dbRequest = indexedDB.open('mail.ru', 1),
    person1 = {
      name: 'user one',
      email: 'user1@email.com',
      age: 17,
      created: new Date()
    },
    person2 = {
      name: 'user two',
      email: 'user2@email.com',
      age: 35,
      created: new Date()
    },
    person3 = {
      name: 'user three',
      email: 'user3@email.com',
      age: 42,
      created: new Date()
    },
    person4 = {
        name: 'user one',
        email: 'user4@email.com',
        age: 50,
        created: new Date()
    };

  dbRequest.onupgradeneeded = function (e) {
    db = dbRequest.result;
    var
      usersStore = db.createObjectStore('users', { keyPath: 'id', autoIncrement: true });

    usersStore.createIndex('name', 'name', {unique: false});
    usersStore.createIndex('email', 'email', {unique: true});
    usersStore.createIndex('age', 'age', {unique: false});
  };

  dbRequest.onsuccess = function () {
    db = dbRequest.result;
    var
      transaction = db.transaction(['users'], 'readwrite'),
      store = transaction.objectStore('users');
    store.put(person1);
    store.add(person2);
    store.add(person3);
    store.add(person4);
    
  };
  ```
  Что будет в результате выполнения?
  ```javascript
  var object = db.transaction(['users'], 'readwrite').objectStore('users').index('name').get('user one');
  object.onsuccess = function (e) {
    var result = e.target.result;
    //...
  };
  ```
  
  1. `result.length > 1`
  2. `result.name === person1.name`
  3. `result.name === person4.name`
  4. `result.id === 1`
  5. `result.id === 4`
      
  *Правильные ответы:* **2, 3, 4**

4. У вас есть код
  ```javascript
  var
    db,
    dbRequest = indexedDB.open('mail.ru', 1),
    person1 = {
      name: 'user one',
      email: 'user1@email.com',
      age: 17,
      created: new Date()
    },
    person2 = {
      name: 'user two',
      email: 'user2@email.com',
      age: 35,
      created: new Date()
    },
    person3 = {
      name: 'user three',
      email: 'user3@email.com',
      age: 42,
      created: new Date()
    },
    person4 = {
        name: 'user one',
        email: 'user4@email.com',
        age: 50,
        created: new Date()
    };

  dbRequest.onupgradeneeded = function (e) {
    db = dbRequest.result;
    var
      usersStore = db.createObjectStore('users', { keyPath: 'id', autoIncrement: true });

    usersStore.createIndex('name', 'name', {unique: false});
    usersStore.createIndex('email', 'email', {unique: true});
  };

  dbRequest.onsuccess = function () {
    db = dbRequest.result;
    var
      transaction = db.transaction(['users'], 'readwrite'),
      store = transaction.objectStore('users');
    store.put(person1);
    store.add(person2);
    store.add(person3);
    store.add(person4);
    
  };
  ```
  Что будет в результате выполнения?
  ```javascript
  db.transaction(['users'], 'readwrite').objectStore('users').openCursor().onsuccess = function(e) {
    var
      cursor = e.target.result,
      value = cursor.value;
    
    //...
  };
  ```
  
  1. `typeof cursor.continue === 'function'`
  2. `value.name === person1.name`
  3. `value.name === person4.name`
  4. `value.id === 1`
  5. `value.id === 4`
      
  *Правильные ответы:* **1, 2, 3, 4**

4. У вас есть код
  ```javascript
  var
    db,
    dbRequest = indexedDB.open('mail.ru', 1),
    person1 = {
      name: 'user one',
      email: 'user1@email.com',
      age: 17,
      created: new Date()
    },
    person2 = {
      name: 'user two',
      email: 'user2@email.com',
      age: 35,
      created: new Date()
    },
    person3 = {
      name: 'user three',
      email: 'user3@email.com',
      age: 42,
      created: new Date()
    },
    person4 = {
        name: 'user one',
        email: 'user4@email.com',
        age: 50,
        created: new Date()
    };

  dbRequest.onupgradeneeded = function (e) {
    db = dbRequest.result;
    var
      usersStore = db.createObjectStore('users', { keyPath: 'id', autoIncrement: true });

    usersStore.createIndex('name', 'name', {unique: false});
    usersStore.createIndex('email', 'email', {unique: true});
  };

  dbRequest.onsuccess = function () {
    db = dbRequest.result;
    var
      transaction = db.transaction(['users'], 'readwrite'),
      store = transaction.objectStore('users');
    store.put(person1);
    store.add(person2);
    store.add(person3);
    store.add(person4);
    
  };
  ```
  Что будет в результате выполнения?
  ```javascript
  db.transaction(['users'], 'readwrite').objectStore('users').index('age').openCursor(IDBKeyRange.lowerBound(35)).onsuccess = function (e) {
    var
      cursor = e.target.result,
      value = cursor.value;
    
    //...
  };
  ```
  
  1. `typeof cursor.continue === 'function'`
  2. `value.name === person1.name`
  3. `value.name === person2.name`
  4. `value.name === person3.name`
  5. `value.age === 35`
      
  *Правильные ответы:* **1, 3, 5**

