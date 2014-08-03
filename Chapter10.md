## Глава 10. Интерфейсы HTML5
### Тема 1. GeoLocation
1. Какие из утверждений верны
  ```javascript
  navigator.geolocation.getCurrentPosition(function success(position) {
    ...
  }, function error(positionError) {
    ...   
  });
  ```
  1. Вы всегда можете получить местоположение пользователя
  2. Пользователь увидит безусловную блокируемую информационную панель с возможностью либо согласиться либо отказать сообщить свое местоположение 
  3. Объект `position` гарантировано будет иметь значения свойств `coords.latitude`, `coords.longitude`, `coords.accuracy`, `coords.speed`
  4. Ф-я `error` может быть вызвана при достижении `timeout`
  5. Местоположение может быть определено по IP-адресу
  
  *Правильные ответы:* **2, 4, 5**

2. Какие из утверждений верны
  ```javascript
  navigator.geolocation.getCurrentPosition(function success(position) {
    ...
  }, function error(positionError) {
    ...   
  });
  ```
  1. Вы можете получить местоположение пользователя только в desktop версии браузера, при специальном разрешение
  2. Пользователь увидит информационную панель с информацией о том, что данный веб-сайт получил местоположение
  3. Объект `position` гарантировано будет иметь значения свойств `coords.latitude`, `coords.longitude`, `coords.accuracy`
  4. Ф-я `error` может быть вызвана при если сеть не работает или нет связи со спутниками
  5. Местоположение может быть определено по подключению к беспроводной сети
  
  *Правильные ответы:* **3, 4, 5**
  
3. Какие из утверждений верны
  ```javascript
  navigator.geolocation.getCurrentPosition(function success(position) {
    ...
  }, function error(positionError) {
    ...   
  }, {
    maximumAge: 75000
  });
  ```
  1. Вы можете получить местоположение пользователя только в мобильной версии браузера, при специальном разрешение
  2. Объект `position` может иметь значение свойства `coords.altitude` (высота над уровнем моря)
  3. Ф-я `error` может быть вызвана если пользователь не дал разрешения на использование местоположения
  4. Местоположение может быть определено GPS оборудование устройства
  5. При повторном вызове метода `getCurrentPosition` через 60 секунд вы получите абсолютно такой же результат
  
  *Правильные ответы:* **2, 3, 4, 5**
    
4. Какие из утверждений верны
  ```javascript
  var positionTimeStamp;
  navigator.geolocation.getCurrentPosition(function success(position) {
    positionTimeStamp = position.timestamp;
    ...
  }, function error(positionError) {
    ...   
  }, {
    enableHighAccuracy: true,
    maximumAge: 75000
  });
  ```
  1. Вы можете получить местоположение пользователя во всех современных браузерах, при специальном разрешение
  2. Объект `position` может иметь значение свойства `coords.speed`
  3. Ф-я `error` может быть вызвана только в 3-х случаях:
    1. пользователь запретил доступ к своему местоположению
    2. если сеть не работает или нет связи со спутниками
    3. если вычисление местоположения заняло времени больше, чем определено `timeout`
  4. Местоположение может быть определено GPS оборудование устройства
  5. При повторном вызове метода `getCurrentPosition` через 60 секунд `positionTimeStamp !== position.timestamp`
  
  *Правильные ответы:* **1, 2, 4**
      
5. Какие из утверждений верны
  ```javascript
  navigator.geolocation.getCurrentPosition(function success(position) {
    ...
  }, function error(positionError) {
    ...   
  }, {
    enableHighAccuracy: true,
    maximumAge: 75000
  });
  ```
  1. Вы можете получить местоположение пользователя как в мобильной так и desktop версии браузера, при специальном разрешение 
  2. Объект `position` гарантированно будет иметь значение свойства `coords.speed`
  3. Ф-я `error` может быть вызвана также при неопределенной ошибке
  4. На мобильном устройстве при вызове `getCurrentPosition` в первую очередь будет произведена попытка получить местоположение GPS обородуванием
  5. При повторном вызове метода `getCurrentPosition` через 60 секунд `positionTimeStamp === position.timestamp`
  
  *Правильные ответы:* **1, 3, 4, 5**      
  
### Тема 2. Web Worker
1. Какие из утверждений верны
  ```javascript
  var worker = new Worker('worker.js');
  ```
  1. `Browser` создаст новый поток объекта `Worker`, загружаемый асинхронно
  2. Если путь к объекту `Worker` вернет 404, то его выполнение будет прекращено без уведомления
  3. Объекты `Worker` могут создавать субобъекты `Worker`
  4. В объекте `Worker` с помощью функции `importScripts()` можно загружать внешние файлы скриптов и библиотек
  5. Объект `Worker` имеет доступ к `window`
  
  *Правильные ответы:* ****      

2. Какие из утверждений верны
  ```javascript
  var worker = new Worker('worker.js');  
  ```
  1. Прекратить работу объекта `Worker` можно вызвав метод `worker.terminate()`
  2. Объекты `Worker` не могут создавать субобъекты `Worker`
  3. Нет возможности обработать возниконовение ошибки в `worker` 
  4. Взаимодействовать с `worker` можно методом `postMessage()`
    `worker.postMessage('Hello World'); // Отправить данные в worker.` 
  5. Объект `Worker` имеет доступ к `ApplicationCache`
  
  *Правильные ответы:* **1, 4, 5**      

3. Какие из утверждений верны
  ```javascript
  var worker = new Worker('worker.js');
  ```
  1. `Browser` создаст новый поток объекта `Worker`, загружаемый синхронно
  2. Прекратить работу объекта `Worker` можно вызвав метод `close()` внутри `worker`
  3. Обработать ошибки выполения в `worker` можно подписавшись на событие `error`
     `worker.addEventListener('error', function onError() {}, false);`
  4. Метод `worker.postMessage()` принимает только `string`
  5. Объект `Worker` имеет доступ к `navigator`
  
  *Правильные ответы:* **2, 3, 5**      
  
4. Какие из утверждений верны
  ```javascript
  var worker = new Worker('worker.js');
  ```
  1. Сообщения от `worker` можно получать подписавшись на событие `message`
    `worker.addEventListener('message', function onMessage(e) {}, false);`
  2. Если путь к объекту `Worker` вернет 404, то его выполнение будет прекращено без уведомления
  3. В объекте `Worker` не возможно загружать внешние файлы скриптов и библиотек
  4. Метод `worker.postMessage()` принимает только `json`
  5. Объект `Worker` имеет доступ к `XMLHttpRequest`
  
  *Правильные ответы:* **1, 2, 5**      
      
5. Какие из утверждений верны
  ```javascript
  var worker = new Worker('worker.js');
  ```
  1. Объекты `Worker` могут создавать субобъекты `Worker`
  2. Если путь к объекту `Worker` вернет 404, то будет сгенерировано событие `error`
  3. В объекте `Worker` с помощью функции `importScripts()` можно загружать внешние файлы скриптов и библиотек
  4. Метод `worker.postMessage()` принимает `string` и `json`
  5. Объект `Worker` имеет доступ к `document`
  
  *Правильные ответы:* **1, 3, 4**
        
### Тема 3. BlobBuilder
1. Какие из утверждений верны относительно следующего кода
  ```javascript
  var
    blob = new Blob(['mail', 'ru'], {type: 'plain/text'}),
    anotherBlob = blob.slice(1, 5, 'mailRu');
    
  ```
  1. `blob.size === 6`
  2. `blob.size === 2`
  3. `anotherBlob.type === blob.type`
  4. `anotherBlob.size === 4`
  5. `anotherBlob.size = 6; blob.size = 6; anotherBlob.size === blob.size;`
        
  *Правильные ответы:* **1, 4**        
  
2. Какие из утверждений верны относительно следующего кода
  ```javascript
  var
    blob = new Blob(['mail', 'ru'], {type: 'plain/text'}),
    anotherBlob = blob.slice('mailRu');
    
  ```
  1. `blob.size === 6`
  2. `blob.size === 2`
  3. `anotherBlob.type === blob.type`
  4. `anotherBlob.size === 4`
  5. `anotherBlob.size = 6; blob.size = 6; anotherBlob.size === blob.size;`
        
  *Правильные ответы:* **1, 5**        
  
3. Какие из утверждений верны относительно следующего кода
  ```javascript
  var
    blob = new Blob(['<a href="http://mail.ru">MailRu</a>'], {type: 'text/html'}),
    anotherBlob = blob.slice();
    
  ```
  1. `blob.size === 35`
  2. `blob.size === 70`
  3. `anotherBlob.type === blob.type`
  4. `anotherBlob.size === 70`
  5. `anotherBlob.size = 6; blob.size = 6; anotherBlob.size === blob.size;`
        
  *Правильные ответы:* **1, 5**        
  
4. Какие из утверждений верны относительно следующего кода
  ```javascript
  var
    blob = new Blob(['<a href="http://mail.ru">MailRu</a>'], {type: 'text/html'}),
    anotherBlob = blob.slice(0, blob.size, 'mailRu');
    
  ```
  1. `blob.size === 35`
  2. `blob.size === 70`
  3. `anotherBlob.type === blob.type`
  4. `anotherBlob.size === 35`
  5. `anotherBlob.size = 6; blob.size = 6; anotherBlob.size === blob.size;`
        
  *Правильные ответы:* **1, 4, 5**        
  
5. Какие из утверждений верны относительно следующего кода
  ```javascript
  var
    blob = new Blob(['<a href="http://mail.ru">MailRu</a>'], {type: 'text/html'}),
    anotherBlob = blob.slice(0, blob.size, 'text/html');
    
  ```
  1. `blob.size === 35`
  2. `blob.size === 70`
  3. `anotherBlob.type === blob.type`
  4. `anotherBlob.size === 35`
  5. `anotherBlob.size = 6; blob.size = 6; anotherBlob.size === blob.size;`
        
  *Правильные ответы:* **1, 3, 4, 5**
          
          
  
        