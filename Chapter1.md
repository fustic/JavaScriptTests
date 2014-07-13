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
  
### Тема 3. Свойства элементов дерева
1. Какие из приведенных свойств будут присутствовать у объекта `document`
  1. previousSibling
  2. previousElementSibling
  3. firstChild
  4. lastElementChild
  5. nextChild
  
  *Правильные ответы:* **1, 3, 4**

2. Какие из приведенных свойств будут присутствовать у объекта `document`
  1. nextSibling
  2. nextElementSibling
  3. lastChild
  4. firstElementChild
  5. prevChild
  
  *Правильные ответы:* **1, 3, 4**
  
3. Какие из приведенных свойств будут присутствовать у объекта `document.firstElementChild`
  1. nextSibling
  2. nextElementSibling
  3. lastChild
  4. firstElementChild
  5. prevChild
  
  *Правильные ответы:* **1, 2, 3, 4**
  
4. Какие из приведенных свойств будут присутствовать у объекта `document.firstElementChild`
  1. previousSibling
  2. previousElementSibling
  3. firstChild
  4. lastElementChild
  5. nextChild
  
  *Правильные ответы:* **1, 2, 3, 4**

5. Какие из приведенных свойств будут присутствовать у объекта `document.lastElementChild`
  1. previousSibling
  2. previousElementSibling
  3. nextSibling
  4. nextElementSibling
  5. firstSibling
  
  *Правильные ответы:* **1, 2, 3, 4**
  
### Тема 4. Метод `document.write()`
1. Какие из утверждений о методе `document.write()` верны
  1. Это один из наиболее быстрых способ вставки на страницу текста, потому что он не модифицирует DOM
  2. Выполнение этого метода блокирует отрисовку всей страницы
  3. Такого метода не существует
  4. Параметр переданный в метод подвергается проверке структуры тегов перед вставкой и при возникновении ошибки метод сгенерирует ошибку
  5. Вызов метода в обработчике события onload
    
    ```javascript
    document.onload = function () {
      document.write('<h1>Mail.ru</h1>');
    };
    ```
    приведет к уничтожению текущего документа и всех содержащихся в нем сценариев
  
  *Правильные ответы:* **1, 2, 5**
  
2. Какие из утверждений о методе `document.writeln()` верны
  1. Это один из наиболее быстрых способ вставки на страницу текста, потому что он не модифицирует DOM
  2. Выполнение этого метода блокирует отрисовку всей страницы
  3. Такого метода не существует
  4. Параметр переданный в метод подвергается проверке структуры тегов перед вставкой и при возникновении ошибки метод сгенерирует ошибку
  5. Вызов метода в обработчике события onload
    
    ```javascript
    document.onload = function () {
      document.write('<h1>Mail.ru</h1>');
    };
    ```
    приведет к уничтожению текущего документа и всех содержащихся в нем сценариев
        
  *Правильные ответы:* **1, 2, 5**
          
3. Какие из утверждений о методе `document.write()` верны
  1. Это один из наиболее быстрых способ вставки на страницу текста, потому что он не модифицирует DOM
  2. Выполнение этого метода не блокирует отрисовку всей страницы, что позволяет асинхронно вставлять скрипты со сторонних ресурсов 
  3. Такого метода не существует
  4. Параметр переданный в метод не подвергается проверке структуры тегов
  5. Вызов метода в обработчике события onload
    
    ```javascript
    document.onload = function () {
      document.write('<h1>Mail.ru</h1>');
    };
    ```
    приведет к добавлению тега `h1` последним элементом в `body`
  
  *Правильные ответы:* **1, 4**          
  
4. Какие из утверждений о методе `document.writeln()` верны
  1. Это один из наиболее быстрых способ вставки на страницу текста, потому что он не модифицирует DOM
  2. Выполнение этого метода не блокирует отрисовку всей страницы, что позволяет асинхронно вставлять скрипты со сторонних ресурсов 
  3. Такого метода не существует
  4. Параметр переданный в метод не подвергается проверке структуры тегов
  5. Вызов метода в обработчике события onload
    
    ```javascript
    document.onload = function () {
      document.write('<h1>Mail.ru</h1>');
    };
    ```
    приведет к добавлению тега `h1` последним элементом в `body`
  
  *Правильные ответы:* **1, 4**          
  
5. Какие из утверждений о методе `document.write()` верны
  1. Это один из наиболее быстрых способ вставки на страницу текста, потому что он не модифицирует DOM
  2. В метод может быть передано не ограниченное число аргументов и они будут вставлены в DOM последовательно 
  3. В результате вызова метода в обработчике события onload
    
    ```javascript
    document.onload = function () {
     document.write('<h1>Mail.ru</h1>');
     document.write('<h2>The best friend ever</h2>');
    };
    ```
    `body` будет содержать единственный элемент `h2`
  4. Browser валидирирует переданные аргументы и не позволяет вставлять `script` на страницу
  5. Вызов метода в обработчике события onload
    
    ```javascript
    document.onload = function () {
      document.write('<h1>Mail.ru</h1>');
    };
    ```
    приведет к уничтожению текущего документа и всех содержащихся в нем сценариев
  
  *Правильные ответы:* **1, 2, 5**          
  
### Тема 5. Селекторы
1. Страница содержит следующий `html` код
  ```html
  <label for="mail-ru-projects">Проекты mail.ru</label>
  <ul class="main-ul" id="mail-ru-projects">
      <li class="li">http://auto.mail.ru/</li>
      <li class="li">http://afisha.mail.ru/</li>
      <li class="li">https://biz.mail.ru/</li>
      <li class="li">https://money.mail.ru/</li>
      <li class="li">http://dobro.mail.ru/</li>
  </ul>
  ```
  Как можно получить первый элемент списка?
  
  ```javascript
  1. document.querySelectorAll('li:first-child')
  ```
  ```javascript
  2. document.querySelector('li:first-child')
  ```    
  ```javascript
  3. document.getElementsByTagName('li')[0]
  ```    
  ```javascript
  4. document.getElementsByTagName('li:first-child')[0]
  ```    
  ```javascript
  5. document.getElementsByClassName('li')[0]
  ```
        
  *Правильные ответы:* **2, 3, 5**

2. Страница содержит следующий `html` код
  ```html
  <label for="mail-ru-projects">Проекты mail.ru</label>
  <ul class="main-ul" id="mail-ru-projects">
      <li class="li">http://auto.mail.ru/</li>
      <li class="li">http://afisha.mail.ru/</li>
      <li class="li">https://biz.mail.ru/</li>
      <li class="li">https://money.mail.ru/</li>
      <li class="li">http://dobro.mail.ru/</li>
  </ul>
  ```
  Как можно получить последний элемент списка?
  
  ```javascript
  1. document.querySelectorAll('li:last-child')
  ```
  ```javascript
  2. document.querySelector('li:last-child')
  ```    
  ```javascript
  3. document.getElementsByTagName('li')[document.getElementsByTagName('li').length - 1]
  ```    
  ```javascript
  4. document.getElementsByTagName('li:last-child')[0]
  ```    
  ```javascript
  5. document.getElementsByClassName('li')[4]
  ```
        
  *Правильные ответы:* **2, 3, 5**

3. Страница содержит следующий `html` код
  ```html
  <label for="mail-ru-projects">Проекты mail.ru</label>
  <ul class="main-ul" id="mail-ru-projects">
      <li class="li">http://auto.mail.ru/</li>
      <li class="li">http://afisha.mail.ru/</li>
      <li class="li">https://biz.mail.ru/</li>
      <li class="li">https://money.mail.ru/</li>
      <li class="li">http://dobro.mail.ru/</li>
  </ul>
  ```
  Что вернет следующий селектор
  ```javascript
  document.querySelectorAll('#mail-ru-projects li.li')
  ```
  1. Произойдет ошибка, потому что селектор не валидный
  2. Массив содержащий все элементы списка
  3. Массив содержащий только первый элемент списка
  4. Массив содержащий только последний элемент списка
  5. Элемент `ul`
        
  *Правильные ответы:* **2**
  
4. Страница содержит следующий `html` код
  ```html
  <label for="mail-ru-projects">Проекты mail.ru</label>
  <ul class="main-ul" id="mail-ru-projects">
      <li class="li">http://auto.mail.ru/</li>
      <li class="li">http://afisha.mail.ru/</li>
      <li class="li">https://biz.mail.ru/</li>
      <li class="li">https://money.mail.ru/</li>
      <li class="li">http://dobro.mail.ru/</li>
  </ul>
  ```
  Что вернет следующий селектор
  ```javascript
  document.querySelector('#mail-ru-projects li.li')
  ```
  1. Произойдет ошибка, потому что селектор не валидный
  2. Массив содержащий все элементы списка
  3. Массив содержащий только один элемент списка
  4. Один элемент списка
  5. Элемент `ul`
        
  *Правильные ответы:* **4**

5. Страница содержит следующий `html` код
  ```html
  <label for="mail-ru-projects">Проекты mail.ru</label>
  <ul class="main-ul" id="mail-ru-projects">
      <li class="li">http://auto.mail.ru/</li>
      <li class="li">http://afisha.mail.ru/</li>
      <li class="li">https://biz.mail.ru/</li>
      <li class="li">https://money.mail.ru/</li>
      <li class="li">http://dobro.mail.ru/</li>
  </ul>
  ```
  Что вернет следующий селектор
  ```javascript
  document.querySelectorAll('#mail-ru-projects li.li:not(:first-child)')
  ```
  1. Произойдет ошибка, потому что селектор не валидный
  2. Массив содержащий все элементы списка
  3. Массив содержащий все элементы списка, кроме первого
  4. Массив содержащий несколько элементов списка
  5. Второй элемент списка
        
  *Правильные ответы:* **3, 4**