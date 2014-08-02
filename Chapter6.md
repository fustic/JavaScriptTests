## Глава 6. Работа с HTTP
### Тема 1. XMLHttpRequest
1. Какие утверждения верны
  ```javascript
  var xhr = new XMLHttpRequest();
  ``
  1. Методом `open` можно создать соединение только либо `GET`, либо `POST` HTTP-методами
  2. Методом `open` можно создать синхронное соединение
  3. Методом `setRequestHeader` можно выставить абсолютно любые заголовки
  4. Событие `readystatechange` происходит несколько раз в процессе отсылки и получения ответа
  5. Методом `abort` можно прервать выполнение запроса
  
  *Правильные ответы:* **2, 4, 5**  
  
2. Какие утверждения верны
  ```javascript
  var xhr = new XMLHttpRequest();
  ``
  1. Методом `open` можно создать соединение `GET`, `POST`, `DELETE`, `PUT` и др. HTTP-методами
  2. Методом `open` можно создать только асинхронное соединение
  3. Методом `setRequestHeader` можно выставить любые заголовки, кроме тех, которые контролирует browser, например, User-Agent или Connection
  4. Событие `readystatechange` происходит только в случае успешного выполнения запроса
  5. Методом `abort` можно прервать выполнение запроса
  
  *Правильные ответы:* **1, 3, 5**

3. Какие утверждения верны
  ```javascript
  var xhr = new XMLHttpRequest();
  ``
  1. В метод `open` можно передать параметры `user, password` — логин и пароль для HTTP-авторизации
  2. Методом `open` можно создать только синхронное соединение
  3. Выставленные заголовки методом `setRequestHeader` нельзя отменить
  4. Событие `readystatechange` происходит только в случае успешного выполнения запроса
  5. Если в ответе нет заголовка `Content-Type: text/xml`, то свойство `responseXML` будет пустым
  
  *Правильные ответы:* **1, 3, 5**
    
4. Какие утверждения верны
  ```javascript
  var xhr = new XMLHttpRequest();
  ``
  1. Метод `open` не отправляет запрос, это необходимо сделать методом `send`
  2. Методом `getAllResponseHeaders` можно получить HTTP-заголовки ответа
  3. При получении статуса 404 от сервера вызовется обработчик события `onerror` 
  4. Максимальное время ожидания ответа от сервера можно выставлять свойством `xhr.timeout = 1000;`
  5. Событие `onabort` будет вызвано при прерывании запроса 
  
  *Правильные ответы:* **1, 2, 4, 5**    

5. Какие утверждения верны
  ```javascript
  var xhr = new XMLHttpRequest();
  ``
  1. В метод `open` можно передать параметры `user, password` — логин и пароль для HTTP-авторизации
  2. Событие `onloadend` будет вызвано после любого завершения запроса, после событий `load, error, timeout, abort`
  3. Событие `readystatechange` происходит только в случае успешного выполнения запроса
  4. Методом `setRequestHeader` можно выставить любые заголовки, кроме тех, которые контролирует browser, например, User-Agent или Connection
  5. При получении статуса 404 от сервера вызовется обработчик события `onerror`
  
  *Правильные ответы:* **1, 2, 4**  
  
### Тема 2. JSONP
1. Какие из утверждений верны
  1. `JSONP` расшифровывается как `JavaScript Object Notation with Padding`
  2. В `JSONP` запросе не обязательно передавать имя функции (`callback function`)
  3. Основным преимуществом `JSONP` запросов является кросс-браузерность и возможность обратиться к любому домену
  4. Одновременно возможен только 1 `JSONP` запрос на определенный домен
  5. В ответ на `JSONP` запрос сервер возвращает данные в формате `JSON` 
  
  *Правильные ответы:* **1, 2, 3**
      
2. Какие из утверждений верны
  1. На текущий момент единственным правильным MIME-типом для `JSONP` является `application/javascript`
  2. В `JSONP` запросе обязательно передавать имя функции (`callback function`), иначе невозможно получить данные от сервера
  3. Одновременно возможны несколько `JSONP` запросов на определенный домен
  4. В ответ на `JSONP` запрос сервер возвращает `JavaScript`, который будет выполнен
  5. `JSONP` запросы никак не подвержены опасности подделки межсайтовых запросов (`CSRF` или `XSRF`)
  
  *Правильные ответы:* **1, 3, 4**

3. Какие из утверждений верны
  1. `JSONP` работает через добавление тега `script` в страницу с определенным `URL`
  2. `JSONP` запросы подвержены опасности подделки межсайтовых запросов (`CSRF` или `XSRF`)
  3. Можно сказать, что `JSONP` запросы обходят политику ограничения домена путём вставки элемента `script` 
  4. В ответ на `JSONP` запрос сервер возвращает `JavaScript`, который будет выполнен
  5. В `JSONP` запросе обязательно передавать имя функции (`callback function`), иначе невозможно получить данные от сервера
  
  *Правильные ответы:* **1, 2, 3, 4**

4. Какие из утверждений верны
  1. В ответ на `JSONP` запрос сервер возвращает `JavaScript`, который будет выполнен
  2. `JSONP` запросы никак не подвержены опасности подделки межсайтовых запросов (`CSRF` или `XSRF`)
  3. В ответ на `JSONP` запрос сервер возвращает данные в формате `XML`
  4. Основным преимуществом `JSONP` запросов является кросс-браузерность и возможность обратиться к любому домену
  5. В `JSONP` запросе обязательно передавать имя функции (`callback function`), иначе невозможно получить данные от сервера 
  
  *Правильные ответы:* **1, 4**

5. Какие из утверждений верны
  1. В ответ на `JSONP` запрос сервер возвращает данные в формате `JSON`
  2. `JSONP` имеет смысл использовать, когда политикой безопасности запрещен к выполнению `XMLHttpRequest`
  3. Следует делать `JSONP` запросы только к доверенному серверу, потому что выполнится любой `JavaScript` код, отправленный удаленным сервером
  4. `JSONP` работает через добавление тега `script` в страницу с определенным `URL`
  5. Одновременно возможен только 1 `JSONP` запрос на определенный домен
  
  *Правильные ответы:* **2, 3, 4**

### Тема 3. WebSockets
1. Какие из утверждений верны
  ```javascript
  var socket = new WebSocket("ws://mail.ru/ws");
  ```
  1. Протокол WebSocket работает над HTTP
  2. Соединение WebSocket можно открыть по протоколу WS
  3. Методом `socket.send()` можно отправлять только строки
  4. Через параметр конструктора можно выставить заголовок `Sec-WebSocket-Extensions: deflate-frame`
  5. Коды закрытия event.code идентичны HTTP-кодам
    ```javascript
    socket.onclose = function (event) {
      alert(event.code);
    }
    ```
  *Правильные ответы:* **1, 2, 4**

2. Какие из утверждений верны
  ```javascript
  var socket = new WebSocket("ws://mail.ru/ws");
  ```
  1. Протокол WebSocket работает только над HTTP
  2. Соединение WebSocket можно открыть по протоколу WSS
  3. Методом `socket.send()` можно отправлять только бинарные данные
  4. Через параметр конструктора можно выставить заголовок `Sec-WebSocket-Protocol: wamp`
  5. Коды закрытия event.code, в отличии от HTTP-кодов состоят из 4-х цифр
  ```javascript
  socket.onclose = function (event) {
    alert(event.code);
  }
  ```
  
  *Правильные ответы:* **2, 4, 5**

3. Какие из утверждений верны
  ```javascript
  var socket = new WebSocket("wss://mail.ru/ws");
  ```
  1. Протокол WebSocket работает только над HTTPS
  2. Соединение WebSocket можно открыть как по WS, так и по WSS протоколу
  3. Методом `socket.send()` можно отправлять любые данные
  4. WebSocket, в отличии от HTTP не имеет ограничение на время жизни в неактивном состоянии
  5. WebSocket поддерживается в Internet Explorer 9+
  *Правильные ответы:* **2, 3, 4**

4. Какие из утверждений верны
  ```javascript
  var socket = new WebSocket("wss://mail.ru/ws");
  ```
  1. Протокол WebSocket работает как над HTTP, так и над HTTPS
  2. Методом `socket.send(form.elements[0].file)` можно отправлять файлы
  3. Через параметр конструктора можно выставить заголовок `Sec-WebSocket-Extensions: deflate-frame`
  4. WebSocket соединение может закрыть только сервер
  5. Коды закрытия event.code идентичны HTTP-кодам
    ```javascript
    socket.onclose = function (event) {
      alert(event.code);
    }
    ```
  *Правильные ответы:* **1, 2, 3**

5. Какие из утверждений верны
  ```javascript
  var socket = new WebSocket("wss://mail.ru/ws");
  ```
  1. Методом `socket.send('Mail.ru')` можно отправлять строки
  2. Через параметр конструктора можно выставить заголовок `Sec-WebSocket-Protocol: soap`
  3. Сообщения от сервера будут вызывать событие onmessage
    ```javascript
    socket.onmessage = function(event) {
      alert(event.data);
    };
    ```
  4. WebSocket как и HTTP имеет ограничение на время жизни в неактивном состоянии
  5. WebSocket соединение можно закрыть методом `socket.close()`
  *Правильные ответы:* **1, 2, 3, 5**

    