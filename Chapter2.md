## Глава 2. Обработка событий
### Тема 1. Назначение обработчика событий
1. Чему будет равна переменная `counter` после клика на кнопку

  ```html
  <button id="my-button">Click me</button>
  
  <script>
      var
        counter = 0,
        button = document.getElementById('my-button');
      button.onclick = function () {
          counter++;
      };
      button.addEventListener('click', function () {
          counter++;
      }, false);
      button.addEventListener('click', function () {
          counter += 2;
      }, false);
  </script>
  ```
  
  1. Будет ошибка
  2. 1
  3. 2
  4. 3
  5. 4

  *Правильные ответы:* **5**
  
2. Чему будет равна переменная `counter` после клика на кнопку

  ```html
  <button id="my-button">Click me</button>
  
  <script>
      var
        counter = 0,
        button = document.getElementById('my-button');
      button.onclick = function () {
          counter++;
      };
      button.addEventListener('click', function () {
          counter--;
      }, false);
      button.addEventListener('click', function () {
          counter += 2;
      }, false);
  </script>
  ```
  
  1. Будет ошибка
  2. 2
  3. 3
  4. 1
  5. -1
  
  *Правильные ответы:* **2**
  
3. Чему будет равна переменная `counter` после клика на кнопку

  ```html
  <button id="my-button">Click me</button>
  
  <script>
      var
        counter = 0,
        button = document.getElementById('my-button');
      button.onclick = function () {
          counter = 0;
      };
      button.addEventListener('click', function () {
          counter++;
      }, false);
      button.addEventListener('click', function () {
          counter += 2;
      }, false);
  </script>
  ```
  
  1. Будет ошибка
  2. 0
  3. 2
  4. 3
  5. 1
  
  *Правильные ответы:* **4**
  
4. Чему будет равна переменная `counter` после клика на кнопку

  ```html
  <button id="my-button">Click me</button>
  
  <script>
      var
        counter = 0,
        button = document.getElementById('my-button');
      button.onclick = function () {
          counter = 0;
      };
      button.addEventListener('click', function () {
          counter++;
      }, false);
      button.addEventListener('click', function () {
          counter += 2;
      }, false);
      button.addEventListener('click', function () {
          counter += 3;
      }, false);
  </script>
  ```
  
  1. Будет ошибка
  2. 3
  3. 5
  4. 6
  5. 0
  
  *Правильные ответы:* **4**

5. Чему будет равна переменная `counter` после клика на кнопку

  ```html
  <button id="my-button">Click me</button>
  
  <script>
      var
        counter = 0,
        button = document.getElementById('my-button');
      button.onclick = function () {
          counter += 5;
      };
      button.addEventListener('click', function () {
          counter++;
      }, false);
      button.addEventListener('click', function () {
          counter -= 2;
      }, false);
      button.addEventListener('click', function () {
          counter += 3;
      }, false);
  </script>
  ```
  
  1. Будет ошибка
  2. 5
  3. 8
  4. 3
  5. 7
  
  *Правильные ответы:* **5**
  
### Тема 2. Capturing и bubbling.
1. Что будет в консоли после клика на `div`
  
  ```html
  <body>
      <div>This is my div</div>
  
      <script>
          var
            body = document.body,
            div = document.querySelector('div');
  
          body.addEventListener('click', function() {
              console.log('body')
          }, false);
  
          div.addEventListener('click', function() {
              console.log('div')
          }, false)
  
      </script>
  </body>
  ```
  1. div
  2. body
  3. div
     body
  4. body
     div
  5. пустая строка
   
  *Правильные ответы:* **3**

2. Что будет в консоли после клика на `div`
  
  ```html
  <body>
      <div>This is my div</div>
  
      <script>
          var
            body = document.body,
            div = document.querySelector('div');
  
          body.addEventListener('click', function() {
              console.log('body')
          }, true);
  
          div.addEventListener('click', function() {
              console.log('div')
          }, true);
  
      </script>
  </body>
  ```
  1. div
  2. body
  3. div
     body
  4. body
     div
  5. пустая строка
   
  *Правильные ответы:* **4**

3. Что будет в консоли после клика на `div`
  
  ```html
  <body>
      <div>This is my div</div>
  
      <script>
          var
            body = document.body,
            div = document.querySelector('div');
  
          body.addEventListener('click', function() {
              console.log('body')
          }, false);
  
          div.addEventListener('click', function() {
              console.log('div')
          }, true);
  
      </script>
  </body>
  ```
  1. div
  2. body
  3. div
     body
  4. body
     div
  5. пустая строка
   
  *Правильные ответы:* **3**
  
4. Что будет в консоли после клика на `div`
  
  ```html
  <body>
      <div>This is my div</div>
  
      <script>
          var
            body = document.body,
            div = document.querySelector('div');
  
          body.addEventListener('click', function() {
              console.log('body')
          }, true);
  
          div.addEventListener('click', function() {
              console.log('div')
          }, false);
  
      </script>
  </body>
  ```
  1. div
  2. body
  3. div
     body
  4. body
     div
  5. пустая строка
   
  *Правильные ответы:* **4**
    
5. Что будет в консоли после клика на `div`
  
  ```html
  <body>
      <div>This is my div</div>
  
      <script>
          var
            body = document.body,
            div = document.querySelector('div');
  
            body.addEventListener('click', function(e) {
                e.stopPropagation();
                console.log('body')
            }, false);
    
            div.addEventListener('click', function(e) {
                e.stopPropagation();
                console.log('div')
            }, false);
  
      </script>
  </body>
  ```
  1. div
  2. body
  3. div
     body
  4. body
     div
  5. пустая строка
   
  *Правильные ответы:* **1**

              
### Тема 3. События мыши
1. Отметьте события мыши на которые можно подписаться
  1. mousedown
  2. mousein
  3. mouseout
  4. mouseup
  5. dblclick

  *Правильные ответы:* **1, 3, 4, 5**
  
2. Отметьте события мыши на которые можно подписаться
   1. mousedown
   2. mousein
   3. mouseexit
   4. click
   5. contextmenu
 
   *Правильные ответы:* **1, 4, 5**

3. Отметьте неотменяемые события мыши на которые можно подписаться
   1. mousedown
   2. mouseup
   3. contextmenu
   4. click
   5. dblclick
 
   *Правильные ответы:* **1, 2, 4, 5**

4. Отметьте неотменяемые события мыши на которые можно подписаться
   1. mousedown
   2. mousemove
   3. contextmenu
   4. mouseover
   5. mouseout
 
   *Правильные ответы:* **1, 2, 4, 5**

5. Отметьте события мыши на которые можно подписаться
   1. trplclick
   2. mousemove
   3. contextmenu
   4. mouseup
   5. mouseout
 
   *Правильные ответы:* **2, 3, 4, 5**

### Тема 4. События мыши: порядок срабатывания

1. Какие события будут зафиксированы в консоли browser при клике левой кнопкой мыши
  
  ```javascript
  document.addEventListener('click', function (e) {
      e.stopPropagation();
      e.preventDefault();
      console.log('click');
  }, false);
  document.addEventListener('mouseup', function (e) {
      e.stopPropagation();
      e.preventDefault();
      console.log('mouseup');
  }, false);
  document.addEventListener('mousedown', function (e) {
      e.stopPropagation();
      e.preventDefault();
      console.log('mousedown');
  }, false);
  ```
  
  1. click
  2. mousedown
  3. click, mouseup, mousedown
  4. mousedown, mouseup, click
  5. mouseup
  
  *Правильные ответы:* **4**  
  
2. Какие события будут зафиксированы в консоли browser при клике правой кнопкой мыши
  
  ```javascript
  document.addEventListener('contextmenu', function (e) {
      e.stopPropagation();
      e.preventDefault();
      console.log('contextmenu');
  }, false);
  document.addEventListener('mouseup', function (e) {
      e.stopPropagation();
      e.preventDefault();
      console.log('mouseup');
  }, false);
  document.addEventListener('mousedown', function (e) {
      e.stopPropagation();
      e.preventDefault();
      console.log('mousedown');
  }, false);
  ```
  
  1. contextmenu
  2. mousedown
  3. contextmenu, mouseup, mousedown
  4. mousedown, mouseup, contextmenu
  5. mousedown, contextmenu, mouseup
  
  *Правильные ответы:* **5**
  
3. Какие события будут зафиксированы в консоли browser при клике левой кнопкой мыши
  
  ```javascript
  document.addEventListener('contextmenu', function (e) {
      e.stopPropagation();
      e.preventDefault();
      console.log('contextmenu');
  }, false);
  document.addEventListener('mouseup', function (e) {
      e.stopPropagation();
      e.preventDefault();
      console.log('mouseup');
  }, false);
  document.addEventListener('mousedown', function (e) {
      e.stopPropagation();
      e.preventDefault();
      console.log('mousedown');
  }, false);
  ```
  
  1. contextmenu
  2. mousedown, mouseup
  3. contextmenu, mouseup, mousedown
  4. mousedown, mouseup, contextmenu
  5. mousedown, contextmenu, mouseup
  
  *Правильные ответы:* **2**
  
4. Какие события будут зафиксированы в консоли browser при клике левой кнопкой мыши
  
  ```javascript
  document.addEventListener('mouseup', function (e) {
      e.stopPropagation();
      e.preventDefault();
      console.log('mouseup');
  }, false);
  document.addEventListener('mouseup', function (e) {
      e.stopPropagation();
      e.preventDefault();
      console.log('mouseup');
  }, false);
  document.addEventListener('mousedown', function (e) {
      e.stopPropagation();
      e.preventDefault();
      console.log('mousedown');
  }, false);
  ```
  
  1. mousedown
  2. mousedown, mouseup
  3. mouseup, mouseup, mousedown
  4. mousedown, mouseup, mouseup
  5. mouseup, mousedown, mouseup
  
  *Правильные ответы:* **4**
  
5. Какие события будут зафиксированы в консоли browser при клике левой кнопкой мыши
  
  ```javascript
  document.addEventListener('click', function (e) {
      e.stopPropagation();
      e.preventDefault();
      console.log('click');
  }, false);
  document.addEventListener('mouseup', function (e) {
      e.stopPropagation();
      e.preventDefault();
      console.log('mouseup');
  }, false);
  document.addEventListener('dbclick', function (e) {
      e.stopPropagation();
      e.preventDefault();
      console.log('dbclick');
  }, false);
  ```
  
  1. dbclick
  2. mouseup, click
  3. click, mouseup, dbclick
  4. dbclick, mouseup, click
  5. click
  
  *Правильные ответы:* **2**
  