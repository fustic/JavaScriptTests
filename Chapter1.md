## Глава 1. Объект Window и работа с DOM
### Тема 1. Открытие нового окна

1. При выполнении следующего кода, который был инициирован пользователем, т.е. он совершил действие, при этом он первый раз посещает страницу где выполнится этот код

 ```javascript
 window.open("http://mail.ru", "mail.ru");
 ```
  1. Откроется новое окно/вкладка с данным URL
  2. Всплывающее окно будет заблокировано
  3. Откроется новое окно/вкладка с данным URL, но при этом пользователю будет показано предупреждение
  4. Ничего не произойдет
  5. Откроется новое окно/вкладка с данным URL во всез браузерах, кроме IE
  
  *Правильный ответ:* **1**

2. При выполнении следующего кода, который не был инициирован пользователем, т.е. он не совершал действий, при этом он первый раз посещает страницу где выполнится этот код

 ```javascript
 window.open("http://mail.ru", "mail.ru");
 ```
  1. Откроется новое окно/вкладка с данным URL
  2. Всплывающее окно будет заблокировано
  3. Откроется новое окно/вкладка с данным URL, но при этом пользователю будет показано предупреждение
  4. Ничего не произойдет
  5. Откроется новое окно/вкладка с данным URL во всез браузерах, кроме IE
  
  *Правильный ответ:* **2**

3. При выполнении следующего кода, который не был инициирован пользователем, т.е. он не совершал действий, при этом он первый раз посещает страницу где выполнится этот код

 ```javascript
 setTimeout(function() {
   window.open("http://mail.ru", "mail.ru");
 }, 300);
 ```
  1. Откроется новое окно/вкладка с данным URL
  2. Всплывающее окно будет заблокировано
  3. Откроется новое окно/вкладка с данным URL, но при этом пользователю будет показано предупреждение
  4. Ничего не произойдет
  5. Откроется новое окно/вкладка с данным URL во всез браузерах, кроме IE
  
  *Правильный ответ:* **2**

4. При выполнении следующего кода, который был инициирован пользователем, т.е. он совершил действие, при этом он первый раз посещает страницу где выполнится этот код

 ```javascript
  setTimeout(function() {
    window.open("http://mail.ru", "mail.ru");
  }, 300);
  ```
  1. Откроется новое окно/вкладка с данным URL
  2. Всплывающее окно будет заблокировано
  3. Откроется новое окно/вкладка с данным URL, но при этом пользователю будет показано предупреждение
  4. Ничего не произойдет
  5. Откроется новое окно/вкладка с данным URL во всез браузерах, кроме IE
  
  *Правильный ответ:* **5**

5. При выполнении следующего кода, который был инициирован пользователем, т.е. он совершил действие, при этом он первый раз посещает страницу где выполнится этот код

 ```javascript
  setTimeout(function() {
    window.open("http://mail.ru", "mail.ru");
  }, 1500);
  ```
  1. Откроется новое окно/вкладка с данным URL
  2. Всплывающее окно будет заблокировано
  3. Откроется новое окно/вкладка с данным URL, но при этом пользователю будет показано предупреждение
  4. Ничего не произойдет
  5. Откроется новое окно/вкладка с данным URL во всез браузерах, кроме IE
  
  *Правильный ответ:* **3**
  
### Тема 2. Ограничение "Same Origin"
1. Ваш скрипт загружен на странице с адресом http://www.mail.ru, также вы вставили `iframe` c погодой от mail.ru
  ```html
  <iframe src="http://pogoda.mail.ru/" name="pogoda.mail.ru" id="pogodaMailRu"></iframe>
  ```
  ```javascript
  var iframe = document.querySelector('#pogodaMailRu');
  iframe.onload = function iframeOnLoad() {};
  ```
  Какие из следующих утверждений верны:
  1. Browser будет считать, что они из одного источника
  2. Внутри функции iframeOnLoad вы сможете получить доступ к `document` на чтение
   
    ```javascript
    console.log(iframe.contentWindow.document)
    ```
  3. Внутри функции iframeOnLoad вы сможете получить доступ к `location` на чтение
   
    ```javascript
    console.log(iframe.contentWindow.location.href)
    ```
  4. Внутри функции iframeOnLoad вы сможете получить доступ к `location` на запись
   
    ```javascript
    iframe.contentWindow.location = 'http://auto.mail.ru';
    ```
  5. "Общение" между окнами с разных источников возможно через postMessage 
  
  *Правильные ответы:* **4, 5**
 
2. Ваш скрипт загружен на странице с адресом http://mail.ru, также вы вставили `iframe` c погодой от mail.ru
  ```html
  <iframe src="http://pogoda.mail.ru/" name="pogoda.mail.ru" id="pogodaMailRu"></iframe>
  ```
  ```javascript
  var iframe = document.querySelector('#pogodaMailRu');
  iframe.onload = function iframeOnLoad() {};
  ```
  Какие из следующих утверждений верны:
  1. Browser будет считать, что они из одного источника
  2. Внутри функции iframeOnLoad вы сможете получить доступ к `document` на чтение 
  ```javascript
  console.log(iframe.contentWindow.document)
  ```
  3. Внутри функции iframeOnLoad вы сможете получить доступ к `location` на чтение 
  ```javascript
  console.log(iframe.contentWindow.location.href)
  ```
  4. Внутри функции iframeOnLoad вы сможете получить доступ к `location` на запись 
  ```javascript
  iframe.contentWindow.location = 'http://auto.mail.ru';
  ```
  5. "Общение" между окнами с разных источников не возможно через postMessage 
  
  *Правильные ответы:* **1, 2, 3, 4**
 
3. Ваш скрипт загружен на странице с адресом https://mail.ru, также вы вставили `iframe` c погодой от mail.ru
  ```html
  <iframe src="http://pogoda.mail.ru/" name="pogoda.mail.ru" id="pogodaMailRu"></iframe>
  ```
  ```javascript
  var iframe = document.querySelector('#pogodaMailRu');
  iframe.onload = function iframeOnLoad() {};
  ```
  Какие из следующих утверждений верны:
  1. Browser будет считать, что они из одного источника
  2. Внутри функции iframeOnLoad вы сможете получить доступ к `document` на чтение 
  ```javascript
  console.log(iframe.contentWindow.document)
  ```
  3. Внутри функции iframeOnLoad вы сможете получить доступ к `location` на чтение 
  ```javascript
  console.log(iframe.contentWindow.location.href)
  ```
  4. Внутри функции iframeOnLoad вы сможете получить доступ к `location` на запись 
  ```javascript
  iframe.contentWindow.location = 'http://auto.mail.ru';
  ```
  5. "Общение" между окнами с разных источников не возможно через postMessage 
  
  *Правильные ответы:* **4**
 
4. Ваш скрипт загружен на странице с адресом https://mail.ru, также вы вставили `iframe` c погодой от mail.ru
  ```html
  <iframe src="https://pogoda.mail.ru/" name="pogoda.mail.ru" id="pogodaMailRu"></iframe>
  ```
  ```javascript
  var iframe = document.querySelector('#pogodaMailRu');
  iframe.onload = function iframeOnLoad() {};
  ```
  Какие из следующих утверждений верны:
  1. Browser будет считать, что они из одного источника
  2. Внутри функции iframeOnLoad вы сможете получить доступ к `document` на чтение 
  ```javascript
  console.log(iframe.contentWindow.document)
  ```
  3. Внутри функции iframeOnLoad вы сможете получить доступ к `location` на чтение 
  ```javascript
  console.log(iframe.contentWindow.location.href)
  ```
  4. Внутри функции iframeOnLoad вы сможете получить доступ к `location` на запись 
  ```javascript
  iframe.contentWindow.location = 'http://auto.mail.ru';
  ```
  5. "Общение" между окнами с разных источников не возможно через postMessage 
  
  *Правильные ответы:* **1, 2, 3, 4**

5. Ваш скрипт загружен на странице с адресом https://www.mail.ru, также вы вставили `iframe` c погодой от mail.ru
  ```html
  <iframe src="http://www.pogoda.mail.ru/" name="pogoda.mail.ru" id="pogodaMailRu"></iframe>
  ```
  ```javascript
  var iframe = document.querySelector('#pogodaMailRu');
  iframe.onload = function iframeOnLoad() {};
  ```
  Какие из следующих утверждений верны:
  1. Browser будет считать, что они из одного источника
  2. Внутри функции iframeOnLoad вы сможете получить доступ к `document` на чтение 
  ```javascript
  console.log(iframe.contentWindow.document)
  ```
  3. Внутри функции iframeOnLoad вы сможете получить доступ к `location` на чтение 
  ```javascript
  console.log(iframe.contentWindow.location.href)
  ```
  4. Внутри функции iframeOnLoad вы сможете получить доступ к `location` на запись 
  ```javascript
  iframe.contentWindow.location = 'http://auto.mail.ru';
  ```
  5. "Общение" между окнами с разных источников возможно через postMessage 
  
  *Правильные ответы:* **4, 5**
  
